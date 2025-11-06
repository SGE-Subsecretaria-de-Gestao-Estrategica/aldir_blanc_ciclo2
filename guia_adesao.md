# [Em Construção] Guia Prático: Adoção do Padrão de Dados PNAB (SNIIC Ciclo 2)

Este guia destina-se aos gestores e equipes técnicas dos Entes Federados (Estados, DF e Municípios) responsáveis pela execução da Política Nacional Aldir Blanc (PNAB).

O objetivo é fornecer diretrizes práticas para a adoção e implementação do **Padrão SNIIC para Coleta de Dados - PNAB Ciclo 2**, garantindo que os dados coletados sejam compatíveis, consistentes e aptos para o envio ao Ministério da Cultura (MinC).

## 1. Compreendendo o Padrão de Coleta (O "Quê?")

Antes de implementar, é crucial entender o que o Padrão de Coleta do Ciclo 2 exige.

### O Modelo Conceitual
O padrão não exige que seu sistema interno seja idêntico ao nosso, mas sim que os **dados que você coleta** sejam compatíveis. O foco é a **coleta de dados**, não a arquitetura do seu banco de dados.

Para entender a lógica completa, consulte a [Modelagem Entidade-Relacionamento da PNAB (mer_pnab.md)](mer_pnab.md).

### As Duas Fases da Coleta (O "Quando?")
O padrão de coleta é dividido em dois momentos cruciais que refletem o ciclo de vida do fomento:

1.  **FASE 1: INSCRIÇÃO**
    * **O que é:** Dados coletados dos proponentes no momento em que eles se inscrevem no seu edital.
    * **Entidades envolvidas:**
        * `Agente Individual` (Pessoa Física ou MEI)
        * `Pessoa Jurídica` (com ou sem fins lucrativos)
        * `Coletivo Informal` (sem CNPJ)
        * `Proposta de Ação Cultural`
        * `Proposta de Subsídio`
        * `Proposta de Bolsa`
        * `Proposta de Premiação`

2.  **FASE 2: RELATÓRIO DE EXECUÇÃO**
    * **O que é:** Dados coletados *após* a execução do projeto, quando o agente cultural envia seu relatório de objeto.
    * **Entidades envolvidas:**
        * `Ação Realizada` (o que foi feito, datas, valores, pessoas pagas)
        * `Entrega` (os produtos/serviços gerados, público alcançado)

### Os Dicionários de Dados (As "Regras")
Os dicionários são o coração do padrão. Eles definem **exatamente** o que deve ser coletado. Cada dicionário (ex: `dicionario-fase-1.md`) possui 4 colunas:

* **Atributo / Descrição:** O que é o dado (ex: "Nome completo"). Use isso como o "rótulo do campo" no seu formulário.
* **Finalidade:** Por que este dado é importante. Use isso para criar textos de ajuda ("?") para o proponente.
* **Nome formatado:** O nome técnico do campo (ex: `nome_completo`). Este é o nome que seu sistema deve usar na exportação (ex: cabeçalho da coluna no CSV ou chave no JSON).
* **Valores possíveis:** A regra do campo. Define o tipo (ex: `Data (dd/mm/aaaa)`) ou o link para uma lista de valores.

### As Listas de Valores (Os "Vocabulários")
Para que os dados sejam comparáveis, certos campos *devem* usar valores padronizados. Por exemplo, o campo `segmento_cultural_principal` deve usar os valores da [Lista 8. Segmento Cultural](listas-de-valores.md#8-segmento-cultural).

Qualquer implementação deve **obrigatoriamente** usar os valores exatos fornecidos no arquivo [listas-de-valores.md](listas-de-valores.md).

---

## 2. Diretrizes Práticas de Implementação (O "Como?")

Seja qual for a tecnologia que seu ente utiliza, o objetivo final é o mesmo: **produzir um conjunto de dados (planilhas ou arquivos) que esteja 100% compatível com os dicionários e listas de valores.**

Abaixo, detalhamos os 3 cenários de implementação:

### 🗺️ Cenário 1: "Eu já tenho um sistema de inscrições" (Ajuste de Sistema)

Este cenário é para entes que já possuem um software (próprio ou contratado) de gestão de editais.

**Plano de Ação:**

1.  **Mapeamento (DE-PARA):** Sua equipe técnica deve fazer um mapeamento campo a campo.
    * *Exemplo:* O campo `Nome do Proponente` no seu sistema deve ser mapeado para o nosso `nome_completo`.
2.  **Identificar Lacunas:** Verifique quais atributos dos nossos dicionários **não existem** no seu sistema. Eles precisarão ser criados.
    * *Exemplo:* "Seu sistema coleta `Cor/Raça`? Coleta `Pautas Temáticas`?"
3.  **Adequar Listas de Valores:** Este é o ponto mais crítico. Se o seu sistema tem um campo "Segmento Cultural" com valores diferentes dos nossos, ele deve ser **atualizado** para usar *exclusivamente* os valores da [Lista 8. Segmento Cultural](listas-de-valores.md#8-segmento-cultural).
4.  **Validar Tipos de Dados:** Garanta que os tipos são compatíveis. Se o dicionário pede `Data (dd/mm/aaaa)`, seu campo não pode aceitar texto livre.
5.  **Desenvolver o Módulo de Exportação:** Seu sistema deve ser capaz de gerar um arquivo (CSV, JSON, etc.) onde os cabeçalhos/chaves sejam os `Nomes formatados` dos nossos dicionários.

### 📊 Cenário 2: "Vou usar Planilhas ou Formulários Online" (Implementação Simplificada)

Este cenário é ideal para entes com menor volume de inscrições ou sem equipe de TI dedicada.

**Plano de Ação (Recomendado: Usar Formulários Online):**

1.  **Use Formulários (Google Forms, Microsoft Forms, etc.):** Esta é a forma mais fácil de garantir a qualidade dos dados.
2.  **Crie os Campos:** Crie uma pergunta para cada `Atributo / Descrição` do dicionário (ex: para a Fase 1, crie um formulário para "Agente Individual", outro para "Proposta de Ação Cultural", etc.).
3.  **Use Listas Suspensas:** Para cada campo que aponta para uma Lista de Valores (ex: `segmento_cultural_principal`), use a opção "Lista Suspensa" ou "Múltipla Escolha" e copie/cole *exatamente* os valores da nossa [listas-de-valores.md](listas-de-valores.md).
4.  **Use Validação de Dados:** Use as regras de validação do formulário para garantir que CPF/CNPJ contenham apenas números ou que o e-mail seja válido.
5.  **Exporte a Planilha:** A resposta do formulário é uma planilha. Você só precisará renomear os cabeçalhos das colunas para que correspondam aos `Nomes formatados` definidos nos dicionários.

**Plano de Ação (Se usar Planilhas diretamente):**

1.  **Crie Planilhas-Modelo:** Crie arquivos (Excel, Google Sheets) para cada entidade (Agente Individual, Proposta de Ação, etc.).
2.  **Use os `Nomes Formatados`:** Os cabeçalhos das colunas da sua planilha DEVEM ser os `Nomes formatados` (ex: `cpf`, `nome_completo`, `data_nascimento`).
3.  **Use Validação de Dados:** No Excel ou Google Sheets, use a ferramenta "Validação de Dados" para criar listas suspensas nas células, baseando-se nas [listas-de-valores.md](listas-de-valores.md). Isso evita erros de digitação.

### 💻 Cenário 3: "Vou construir ou contratar um novo sistema" (Implementação Completa)

Este cenário é para entes que irão desenvolver um software do zero ou licitar um novo.

**Plano de Ação:**

1.  **Use os Dicionários como Requisito:** Os arquivos `dicionario-fase-1.md` e `dicionario-fase-2.md` **são os requisitos técnicos** para o banco de dados e para os formulários de front-end.
2.  **Banco de Dados:** Use os `Nomes formatados` como nomes das colunas no seu banco de dados (ex: `CREATE TABLE AgenteIndividual (cpf VARCHAR(11), nome_completo VARCHAR(100), ...)`).
3.  **Front-End (Telas de Inscrição):**
    * **Rótulo do Campo:** Use o `Atributo / Descrição` (ex: "Nome artístico ou Nome Social").
    * **Texto de Ajuda:** Use a `Finalidade` (ex: "Assegurar o respeito à identidade de gênero...").
    * **Validação:** Use os `Valores possíveis` (ex: `Texto Curto (até 100 caracteres)`, `Data (dd/mm/aaaa)`).
4.  **Listas de Valores:** O sistema deve popular os campos de seleção (dropdowns) buscando os dados *exatos* do arquivo [listas-de-valores.md](listas-de-valores.md).
5.  **API e Exportação:** O sistema deve, nativamente, ser capaz de exportar os dados da Fase 1 e Fase 2 seguindo 100% o Padrão SNIIC.

---

## 3. Envio dos Dados ao MinC

Conforme descrito no `README.md` deste repositório, as informações deverão ser enviadas ao MinC através da plataforma Cult.BR.

Independentemente do cenário de implementação (Sistema Próprio, Planilha ou Novo Sistema), o resultado do seu trabalho deve ser um conjunto de dados estruturado que siga este padrão. Preparar seus formulários e sistemas *agora* garantirá um envio de dados rápido e sem inconsistências no futuro.

---

## 4. Recursos (Links Essenciais)

* [**`mer_pnab.md`**](mer_pnab.md): O Modelo Conceitual, para entender o fluxo completo.
* [**`dicionario-fase-1.md`**](dicionario-fase-1.md): Dicionários para coleta na Inscrição (Agentes e Propostas).
* [**`dicionario-fase-2.md`**](dicionario-fase-2.md): Dicionários para coleta no Relatório (Ação Realizada e Entregas).
* [**`listas-de-valores.md`**](listas-de-valores.md): Os vocabulários controlados obrigatórios.
