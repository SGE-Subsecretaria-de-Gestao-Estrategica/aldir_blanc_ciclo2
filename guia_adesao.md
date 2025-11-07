# [Em construção/Validação] Guia Prático: Adoção do Padrão de Dados PNAB (SNIIC Ciclo 2)

Este guia destina-se aos gestores e equipes técnicas dos Entes Federativos (Estados, DF e Municípios) responsáveis pela execução da Política Nacional Aldir Blanc (PNAB).

O objetivo é fornecer diretrizes práticas para a adoção e implementação do **Padrão SNIIC para Coleta de Dados - PNAB Ciclo 2**, garantindo que os dados coletados sejam compatíveis, consistentes e aptos para o envio ao Ministério da Cultura (MinC).

## 1. Compreendendo o Padrão de Coleta e o fluxo de ações necessárias. 

Antes de implementar, é crucial entender o que o Padrão de Coleta do Ciclo 2 exige. O padrão não exige que os diferentes softwares do ecossistema PNAB sejam idênticos, mas sim que os **dados coletados** sejam compatíveis. O foco é a **coleta de dados**, não a arquitetura do seu sistema.
Para entender a lógica completa e o mapeamento do fluxo de informações da PNAB, consulte a nossa [Modelagem Entidade-Relacionamento (mer_pnab.md)](mer_pnab.md).

### As Duas Fases da Coleta
O padrão de coleta é dividido em dois momentos cruciais que refletem o ciclo de vida do fomento:

1.  **FASE 1: INSCRIÇÃO**
    * **O que é:** Dados coletados dos proponentes no momento em que eles se inscrevem no seu edital.
    * **Entidades envolvidas:**
        * `Agente Individual` (Pessoa Física ou MEI)
        * `Pessoa Jurídica` (com ou sem fins lucrativos)
        * `Coletivo Informal` 
        * `Proposta de Ação Cultural`
        * `Proposta de Subsídio`
        * `Proposta de Bolsa`
        * `Proposta de Premiação`

2.  **FASE 2: RELATÓRIO DE EXECUÇÃO**
    * **O que é:** Dados coletados *após* a execução do projeto, quando o agente cultural envia seu relatório de objeto.
    * **Entidades envolvidas:**
        * `Ação Realizada` (o que foi feito, datas, valores, pessoas pagas)
        * `Entrega` (os produtos/serviços gerados, público alcançado)

### Os Dicionários de Dados

Os dicionários de dados são o componente do Padrão que estabelece as diretrizes para a consistência semântica da informação, ou seja, para o seu significado unívoco em todo o ecossistema de soluções digitais relacionados à PNAB. Eles definem **exatamente** o que deve ser coletado. Cada dicionário PNAB (ex: [Agente Individual](dicionario-fase-1.md)) possui 4 colunas:

* **Atributo / Descrição:** Apresenta o nome do atributo e, abaixo, uma breve descrição do que ele representa. Use isso como o "rótulo do campo" em seus formulários.
* **Finalidade:** Explica a motivação para a coleta do dado no contexto da PNAB, orientando seu uso e importância.
* **Nome formatado:** Define o nome técnico do campo, sugerido para a implementação em sistemas e bancos de dados. Este é o nome que seu sistema deve usar na exportação (ex: cabeçalho da coluna no CSV ou chave no JSON).
* **Valores possíveis:** Especifica o tipo de dado esperado (ex: `Data (dd/mm/aaaa)) ou referencia uma lista de valores padronizada.
  

### As Listas de Valores (Os "Vocabulários")

As listas de valores possíveis são um componente essencial do Padrão de Dados da PNAB. Elas funcionam como vocabulários padronizados que garantem a consistência na classificação das informações, eliminando ambiguidades e permitindo que os dados coletados em todo o território nacional sejam comparáveis e agregáveis.

Para que os dados sejam comparáveis, certos campos *devem* usar valores padronizados. Por exemplo, o campo `segmento_cultural` deve usar os valores da [Lista 8. Segmento Cultural](listas-de-valores.md#8-segmento-cultural).

Qualquer implementação deve **obrigatoriamente** usar os valores exatos fornecidos no arquivo [listas-de-valores.md](listas-de-valores.md).

---

## 2. Diretrizes Práticas de Implementação

Seja qual for a tecnologia que seu ente utiliza, o objetivo final é o mesmo: **produzir um conjunto de dados (planilhas, arquivos ou comunicação via API) que esteja 100% compatível com os dicionários e listas de valores.**

Para auxiliar nesse processo, mapeamos quatro cenários principais de implementação. Cada cenário possui um plano de ação sugerido, desde o mais simples (uso de planilhas) até o mais robusto (aderência a sistemas existentes ou federais).

* **Cenário 1:** Aderir à plataforma federal Mapa da Cultura (solução integrada).
* **Cenário 2:** Ajustar um sistema de gestão de editais já existente.
* **Cenário 3:** Usar planilhas ou formulários online (implementação simplificada).
* **Cenário 4:** Construir ou contratar um sistema novo.

Abaixo, detalhamos o plano de ação para cada um:

### Cenário 1: "Vou aderir a uma plataforma federal" (Adesão ao Mapa da Cultura)

> **[Cenário ainda em verificação]**

Este cenário prevê a utilização da plataforma Mapa da Cultura (https://mapa.cultura.gov.br/) como ferramenta oficial do ente federativo para a gestão de seus editais. A plataforma já estará aderente ao Padrão SNIIC Ciclo 2, com os dicionários e listas de valores implementados nativamente. A exportação de dados para o MinC será facilitada, pois o sistema já gerará os relatórios no formato correto exigido pelo Padrão.

---

### Cenário 2: "Eu já tenho um sistema para gestão de Editais" (Ajuste de Sistema)

Este cenário é para entes que já possuem um software (próprio ou contratado) e devem ajustar bancos de dados existentes para garantir o envio consistente das informações.  

**Plano de Ação:**

1.  **Mapeamento (DE-PARA):** Sua equipe técnica deve fazer um mapeamento campo a campo (DE: seu sistema, PARA: Padrão SNIIC).
    * *Exemplo:* O campo `Nome do Proponente` no seu sistema deve ser mapeado para o nosso `nome_completo`.   
2.  **Identificar Lacunas:** Verifique quais atributos dos nossos dicionários **não existem** no seu sistema. Eles precisarão ser criados.
    * *Exemplo:* "Seu sistema coleta `Cor/Raça`? Coleta `Pautas Temáticas`?"
3.  **Adequar Listas de Valores:** Este é o ponto mais crítico. Se o seu sistema tem um campo "Segmento Cultural" com valores diferentes dos nossos, ele deve ser **atualizado** para usar *exclusivamente* os valores da [Lista 8. Segmento Cultural](listas-de-valores.md#8-segmento-cultural).
4.  **Validar Tipos de Dados:** Garanta que os tipos são compatíveis. Se o dicionário pede `Data (dd/mm/aaaa)`, seu campo não pode aceitar texto livre.
5.  **Desenvolver o Módulo de Exportação:** Seu sistema deve ser capaz de gerar um arquivo (CSV, JSON, etc.) onde os cabeçalhos/chaves sejam os `Nomes formatados` dos nossos dicionários.
    * _Exemplos de código para exportação em CSV (Python/PHP) e JSON (JavaScript/Python) serão disponibilizados em breve._

### Cenário 3: "Vou usar Planilhas ou Formulários Online" (Implementação Simplificada)

Este cenário é ideal para entes com menor volume de inscrições ou sem equipe de TI dedicada.

**Plano de Ação (Recomendado: Usar Formulários Online):**

1.  **Use Formulários (Google Forms, Microsoft Forms, etc.):** Esta é a forma mais fácil de garantir a qualidade dos dados.
    * _Um link para um Modelo de Google Forms pré-configurado, espelhando os dicionários, será disponibilizado em breve._
2.  **Crie os Campos:** Crie uma pergunta para cada `Atributo / Descrição` do dicionário (ex: para a Fase 1, crie um formulário para "Agente Individual", outro para "Proposta de Ação Cultural", etc.).
3.  **Use Listas Suspensas:** Para cada campo que aponta para uma Lista de Valores (ex: `segmento_cultural_principal`), use a opção "Lista Suspensa" ou "Múltipla Escolha" e copie/cole *exatamente* os valores da nossa [listas-de-valores.md](listas-de-valores.md).
4.  **Use Validação de Dados:** Use as regras de validação do formulário para garantir que CPF/CNPJ contenham apenas números ou que o e-mail seja válido.
5.  **Exporte a Planilha:** A resposta do formulário é uma planilha. Você só precisará renomear os cabeçalhos das colunas para que correspondam aos `Nomes formatados` definidos nos dicionários.

**Plano de Ação (Se usar Planilhas diretamente):**

1.  **Crie Planilhas-Modelo:** Crie arquivos (Excel, Google Sheets) para cada entidade (Agente Individual, Proposta de Ação, etc.).
    * _Um arquivo .xlsx (Excel) com as colunas, validações de dados e listas suspensas pré-configuradas será disponibilizado em breve._
2.  **Use os `Nomes Formatados`:** Os cabeçalhos das colunas da sua planilha DEVEM ser os `Nomes formatados` (ex: `cpf`, `nome_completo`, `data_nascimento`).
3.  **Use Validação de Dados:** No Excel ou Google Sheets, use a ferramenta "Validação de Dados" para criar listas suspensas nas células, baseando-se nas [listas-de-valores.md](listas-de-valores.md). Isso evita erros de digitação.

### Cenário 4: "Vou construir ou contratar um novo sistema" (Implementação Completa)

Este cenário é para entes que irão desenvolver um software do zero ou licitar um novo.

**Plano de Ação:**

1.  **Use os Dicionários como Requisito:** Os arquivos `dicionario-fase-1.md` e `dicionario-fase-2.md` **são os requisitos técnicos** para o banco de dados e para os formulários de front-end.
2.  **Banco de Dados:** Use os `Nomes formatados` como nomes das colunas no seu banco de dados.
    * _Um script SQL `CREATE TABLE` de exemplo (PostgreSQL/MySQL) será disponibilizado em breve._
3.  **Front-End (Telas de Inscrição):**
    * **Rótulo do Campo:** Use o `Atributo / Descrição` (ex: "Nome artístico ou Nome Social").
    * **Texto de Ajuda:** Use a `Finalidade` (ex: "Assegurar o respeito à identidade de gênero...").
    * **Validação:** Use os `Valores possíveis` (ex: `Texto Curto (até 100 caracteres)`, `Data (dd/mm/aaaa)`).
4.  **Listas de Valores:** O sistema deve popular os campos de seleção (dropdowns) buscando os dados *exatos* do arquivo [listas-de-valores.md](listas-de-valores.md).
5.  **API e Exportação:** O sistema deve, nativamente, ser capaz de exportar os dados da Fase 1 e Fase 2 seguindo 100% o Padrão SNIIC.
    * _Um exemplo de estrutura de API/JSON para envio ao MinC será disponibilizado em breve._



## 3. Envio dos Dados ao MinC

Conforme descrito no [Padrão SNIIC para Coleta de Dados - PNAB Ciclo 2](readme.md), as informações deverão ser enviadas ao MinC através da plataforma Cult.BR.
Independentemente do cenário de implementação (Sistema Próprio, Planilha ou Novo Sistema), o resultado do seu trabalho deve ser um conjunto de dados estruturado que siga este padrão. 

---

## 4. Recursos (Links Essenciais)

* [**`mer_pnab.md`**](mer_pnab.md): O Modelo Conceitual, para entender o fluxo completo.
* [**`dicionario-fase-1.md`**](dicionario-fase-1.md): Dicionários para coleta na Inscrição (Agentes e Propostas).
* [**`dicionario-fase-2.md`**](dicionario-fase-2.md): Dicionários para coleta no Relatório (Ação Realizada e Entregas).
* [**`listas-de-valores.md`**](listas-de-valores.md): Os vocabulários controlados obrigatórios.
