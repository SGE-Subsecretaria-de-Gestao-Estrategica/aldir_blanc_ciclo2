# [Em construção/Validação] Guia Prático: Adoção do Padrão de Dados PNAB (SNIIC Ciclo 2)

Este guia destina-se aos gestores e equipes técnicas dos Entes Federativos (Estados, DF e Municípios) responsáveis pela execução da Política Nacional Aldir Blanc (PNAB).

O objetivo é fornecer diretrizes práticas para a adoção e implementação do **Padrão SNIIC para Coleta de Dados - PNAB Ciclo 2**, garantindo que os dados coletados sejam compatíveis, consistentes e aptos para o envio ao Ministério da Cultura (MinC).

## 1. Compreendendo o Padrão de Coleta e o fluxo de ações necessárias. 

Antes de implementar, é crucial entender o que o Padrão de Coleta do Ciclo 2 exige. O padrão não exige que os diferentes softwares do ecossistema PNAB sejam idênticos, mas sim que os **dados coletados** sejam compatíveis. O foco é a **coleta de dados**, não a arquitetura do seu sistema.

Para compreender a lógica completa e o mapeamento do fluxo de informações da PNAB, consulte a nossa [Modelagem Entidade-Relacionamento (mer_pnab.md)](mer_pnab.md). Para novas implementações ou adaptações de sistemas de informações já existentes, é fundamental considerar toda a modelagem de dados PNAB. 

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
* **Valores possíveis:** Especifica o tipo de dado esperado (ex: `Data (dd/mm/aaaa)`) ou referencia uma lista de valores padronizada.
  

### As Listas de Valores (Os "Vocabulários")

As listas de valores possíveis são um componente essencial do Padrão de Dados da PNAB. Elas funcionam como vocabulários padronizados que garantem a consistência na classificação das informações, eliminando ambiguidades e permitindo que os dados coletados em todo o território nacional sejam comparáveis e agregáveis.

Para que os dados sejam comparáveis, certos campos *devem* usar valores padronizados. Por exemplo, o campo `segmento_cultural` deve usar os valores da [Lista 8. Segmento Cultural](listas-de-valores.md#8-segmento-cultural).

Qualquer implementação deve **obrigatoriamente** usar os valores exatos fornecidos no arquivo [listas-de-valores.md](listas-de-valores.md).

---

## 2. Diretrizes Práticas de Implementação

Seja qual for a tecnologia que seu ente utiliza, o objetivo final é o mesmo: **produzir um conjunto de dados que esteja 100% compatível com os dicionários e listas de valores possíveis, seja por planilhas, arquivos ou comunicação via API.**

Para auxiliar nesse processo, mapeamos quatro cenários principais de implementação. Cada cenário possui um plano de ação sugerido, desde o mais simples (uso de planilhas) até o mais robusto (aderência a sistemas existentes ou federais).

* [**Cenário 1: Aderir à plataforma federal Mapa da Cultura (Solução Integrada)**](guia-cenario-1.md)
* [**Cenário 2: Ajustar um sistema de gestão de editais já existente**](guia-cenario-2.md)
* [**Cenário 3: Usar planilhas ou formulários online (Implementação Simplificada)**](guia-cenario-3.md)
* [**Cenário 4: Construir ou contratar um sistema novo**](guia-cenario-4.md)

Para detalhes completos, planos de ação e exemplos de cada cenário, consulte os guias específicos linkados acima.

---

## 3. Envio dos Dados ao MinC

Conforme descrito no [Padrão SNIIC para Coleta de Dados - PNAB Ciclo 2](readme.md), as informações deverão ser enviadas ao MinC através da plataforma Cult.BR.
Independentemente do cenário de implementação (Sistema Próprio, Planilha ou Novo Sistema), o resultado do seu trabalho deve ser um conjunto de dados estruturado que siga este padrão. 

---

## 4. Recursos (Links Essenciais)

* [**`mer_pnab.md`**](mer_pnab.md): O Modelo Conceitual, para entender o fluxo completo.
* [**`dicionario-fase-1.md`**](dicionario-fase-1.md): Dicionários para coleta na Inscrição (Agentes e Propostas).
* [**`dicionario-fase-2.md`**](dicionario-fase-2.md): Dicionários para coleta no Relatório (Ação Realizada e Entregas).
* [**`listas-de-valores.md`**](listas-de-valores.md): Os vocabulários controlados obrigatórios.

---

## 5. Suporte e Dúvidas

Para garantir que os entes federativos tenham o suporte necessário durante a implementação deste padrão, o MinC disponibiliza os seguintes canais de comunicação:

* Site: https://www.gov.br/cultura/pt-br/assuntos/politica-nacional-aldir-blanc 
* E-mail: pnab@cultura.gov.br
* Canal do Whatsapp: https://tr.ee/rff1H1JYYuaQ
* Plantões tira-dúvidas:
  * Toda quarta-feira, 14h30, agendamento via link: https://calendly.com/minc-scc/atendimento-aldirblanc

---

## 6. Glossário

Para auxiliar equipes técnicas e gestores, seguem definições de termos comuns utilizados neste guia:

* **CSV (Comma-Separated Values):** Um formato de arquivo de texto simples onde os dados são organizados em linhas, e os valores em cada linha são separados por vírgulas. É o formato de exportação mais comum de planilhas (como o Excel).
* **JSON (JavaScript Object Notation):** Um formato de arquivo leve para troca de dados, muito usado em APIs. Ele usa texto legível para transmitir objetos de dados que consistem em pares de atributo-valor.
* **API (Interface de Programação de Aplicações):** Um conjunto de regras e protocolos que permite que diferentes sistemas de software "conversem" entre si, trocando dados de forma automatizada. No contexto da PNAB, uma API permitiria que o sistema do seu município enviasse dados diretamente para o Cult.BR.
* **Banco de Dados:** Uma coleção organizada de informações ou dados estruturados, tipicamente armazenados eletronicamente em um sistema de computador. É onde seu sistema de editais (ou planilha) armazena as informações dos proponentes.
* **Front-End:** A parte de um sistema de software com a qual o usuário interage diretamente. No seu caso, são os formulários de inscrição e relatórios que o agente cultural preenche.
* **Back-End:** A parte "de trás" de um sistema de software, que o usuário não vê. É onde os dados são processados, armazenados (no banco de dados) e onde as regras de negócio são executadas. É o oposto do Front-End.
* **Script SQL:** Uma linguagem de programação usada para gerenciar e consultar bancos de dados. Um script `CREATE TABLE` é o comando usado para construir a estrutura de uma tabela (ex: a tabela `AgenteIndividual` com suas colunas `cpf`, `nome_completo`, etc.).
