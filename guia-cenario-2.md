[< Voltar ao Guia de Implementação](guia-implementacao.md) | [Ir para o Padrão SNIIC (README)](README.md)

# Guia de Implementação - Cenário 2: Ajuste de Sistema Existente

Este guia detalha o plano de ação para Entes Federativos que **já possuem um sistema** (software próprio ou contratado) para gestão de editais e inscrições.

### Perfil do Ente
Este cenário é comum em estados ou grandes municípios que já investiram em tecnologia e possuem sistemas de gestão de editais (próprios ou contratados) em plena operação.

### Vantagens e Desafios
* **Vantagens:**
    * Aproveita o investimento financeiro e técnico já realizado.
    * Mantém a autonomia de gestão do ente e a interface já conhecida pelos agentes culturais locais.
* **Desafios / Pontos de Atenção:**
    * Este é, potencialmente, o cenário mais complexo tecnicamente, pois exige uma análise de impacto e desenvolvimento (seja da equipe própria ou da empresa fornecedora).
    * O **maior risco** é a compatibilidade das **Listas de Valores**. O sistema deve ser ajustado para usar *exatamente* os vocabulários do Padrão SNIIC.
    * É fundamental garantir a **rastreabilidade** (criação de chaves de ligação) entre Agentes, Propostas e Ações Realizadas.

### Guia Passo-a-Passo
A adaptação de um sistema existente exige um planejamento técnico detalhado.

#### Passo 1: Orientação para o Mapeamento (DE-PARA)
Em vez de preencher uma tabela, o primeiro passo é um **diagnóstico interno**. Sua equipe técnica (própria ou contratada) deve analisar os dicionários do Padrão SNIIC ([`dicionario-fase-1.md`](dicionario-fase-1.md) e [`dicionario-fase-2.md`](dicionario-fase-2.md)) e compará-los com o banco de dados e os formulários do seu sistema atual.

O objetivo é responder a três perguntas para *cada* atributo do Padrão SNIIC:

1.  **Temos este dado? (Correspondência Direta)**
    * *Exemplo:* O Padrão pede `nome_completo`. Seu sistema tem o campo `proponente_nome`. Isso é uma correspondência direta.

2.  **Temos este dado, mas com valores diferentes? (Necessidade de Tradução)**
    * *Exemplo:* O Padrão pede `segmento_cultural` (com a [Lista 8](listas-de-valores.md#8-segmento-cultural)). Seu sistema tem `area_cultura` (com "Artes Cênicas", "Música Popular"). Isso exigirá uma "tradução" dos seus valores para os nossos.

3.  **Não temos este dado? (Lacuna)**
    * *Exemplo:* O Padrão pede `pauta_tematica_principal`. Seu sistema não coleta isso. Esta é uma **lacuna** que precisará ser criada no seu banco de dados e no seu formulário.

O resultado deste passo é um **documento de diagnóstico** interno que lista todas as "Traduções" e "Lacunas" necessárias.

#### Passo 2: Adequação dos Vocabulários (Listas de Valores)
Este é o ponto mais crítico para a qualidade dos dados. Todos os campos do seu sistema que correspondem a uma Lista de Valores (ex: Gênero, Segmento Cultural, Tipos de Entrega) devem ser 100% compatíveis com o Padrão SNIIC.

**Listas de Valores em CSV/JSON**
Para facilitar a importação para o seu banco de dados, este repositório disponibilizará o arquivo [`listas-de-valores.md`](listas-de-valores.md) também em formatos estruturados (`.csv` e `.json`).

**Ponto de Atenção: O Risco do Mapeamento (DE-PARA) de Termos Complexos**

É fundamental considerar o risco ao mapear termos complexos da cultura (como Segmentos, Pautas Temáticas ou Tipos de Entrega).

* **Risco:** Um mapeamento automático (ex: `DE` "Artes Cênicas" `PARA` "Teatro") pode ser impreciso, pois "Artes Cênicas" pode incluir "Circo" ou "Dança" (que são categorias separadas no Padrão SNIIC).
* **Recomendação:** A menos que o ente federativo tenha **certeza absoluta** da compatibilidade 1-para-1 entre seus termos e os do Padrão SNIIC, **não faça um DE-PARA automático.** A melhor abordagem é **envolver o usuário (agente cultural)**:
    * **Para novos cadastros:** O formulário de inscrição deve usar *apenas* as novas listas do SNIIC.
    * **Para agentes já cadastrados:** O sistema deve solicitar que os agentes **atualizem seu cadastro** no próximo login, reclassificando-se dentro das novas categorias do Padrão SNIIC. Isso garante a integridade e a precisão semântica dos dados.
     * Um bom momento é o cadastro em editais (Revisar)

#### Passo 3: Desenvolvimento (Front-End e Back-End)
Com o diagnóstico do Passo 1 em mãos, sua equipe de TI deverá:
1.  **Back-end:** Criar as colunas que foram identificadas como **Lacunas** no banco de dados. Implementar as novas tabelas de domínio com as Listas de Valores (Passo 2).
2.  **Front-end:** Adicionar os novos campos e as listas de valores atualizadas nos formulários de inscrição e de relatório de execução, incluindo o fluxo de atualização cadastral para agentes antigos (conforme Passo 2).

#### Passo 4: Módulo de Exportação
O Módulo de Exportação é a funcionalidade do seu sistema que irá gerar o arquivo (CSV, JSON, etc.) a ser enviado ao MinC. Este módulo é a entrega final e deve ter atenção especial, garantindo quatro pontos:

1.  **Nomeação Correta (Cabeçalhos):** O arquivo gerado (ex: um .CSV) **deve** usar os `Nomes formatados` dos dicionários como cabeçalhos das colunas (ex: `nome_completo`, e não `NomeDoProponente`).
2.  **Tradução de Dados (Se aplicável):** Se você optou por um DE-PARA automático (mesmo com os riscos), é neste módulo que a "tradução" de valores deve ocorrer (ex: `IF seu_sistema.area_cultura = 'Artes circenses' THEN 'Circo'`).
3.  **Rastreabilidade (Joins):** O módulo deve garantir a rastreabilidade unindo os dados corretamente. Por exemplo, o arquivo de `Propostas` deve conter o `id_agente` (CPF/CNPJ) que a submeteu; o arquivo de `Ação Realizada` deve conter o `id_proposta` que a originou. (Nota: esta rastreabilidade será detalhada nos próximos "Pontos Críticos").
4.  **Formato e Validação:** O arquivo deve ser gerado em um formato válido (CSV UTF-8 ou JSON) e os tipos de dados devem estar corretos (ex: datas no formato `dd/mm/aaaa`).

### Modelos e Exemplos (Disponibilizados em Breve)
* *Exemplo de Tabela DE-PARA (Planilha de Mapeamento).*
* *Arquivos .CSV e .JSON das Listas de Valores.*
* *Exemplo de código para exportação em CSV (Python/PHP).*
* *Exemplo de código para exportação em JSON (JavaScript/Python).*
