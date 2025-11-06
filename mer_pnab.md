# Modelo Entidade-Relacionamento (MER) da PNAB

A Modelagem Entidade-Relacionamento constitui o núcleo estruturante do Padrão de Dados da PNAB, funcionando como representação lógica e sistemática das informações que compõem a política. Seu objetivo é organizar as entidades centrais e explicitar os relacionamentos que as conectam, de modo a oferecer clareza conceitual tanto para gestores culturais quanto para equipes técnicas responsáveis por sistemas de informação.

O MER da PNAB foi elaborado a partir da lógica de execução da política, traduzindo o ciclo completo: identificação de agentes culturais, formalização dos instrumentos jurídicos de fomento, execução das ações culturais apoiadas e entregas consolidadas. Trata-se, portanto, não apenas de um diagrama técnico, mas de um instrumento de governança, que garante coerência estrutural e semântica em registros produzidos no contexto do ecossistema de soluções digitais relacionados à Pnab.

## Diagrama MER da PNAB (Ciclo II)

A imagem a seguir apresenta o diagrama completo do Padrão de Dados PNAB. Para uma melhor visualização, recomenda-se abrir a imagem em uma nova aba ou realizar o download.

![Diagrama MER da PNAB (Ciclo II)](mer-pnab-ciclo-2.png)

### Legenda do Diagrama

* **Agrupamento lógico:** Blocos conceituais que reúnem entidades relacionadas (ex: Plano de Aplicação de Recursos).
* **Entidades PNAB (Ciclo II):** Entidades centrais da política, especialmente no Ciclo II, que possuem dicionários de dados e são objeto de coleta ou integração de dados.
* **Entidades Conceituais e de Classificação:** Entidades abstratas (ex: `Agente Cultural`) ou de classificações (ex: `Pessoa Física`, `PNCV`) que detalham ou agrupam as Entidades PNAB e são fundamentais para a compreensão e estruturação dos fluxos de informação.
* **Relacionamentos entre Entidades:** Representados por losangos, indicam vínculos e interações entre as entidades (ex: Firma, Realiza, Submete). As linhas que os conectam podem indicar **cardinalidade** (a "quantidade" da relação, como "um para muitos" - 1:N).
* **Herança / Subcategorias:** Setas que indicam quando uma entidade se desdobra em tipos específicos (ex: `Proposta` se divide em `Proposta de Ação Cultural`, `Proposta de Subsídio`, etc.).
* **Metas / Ações:** Conceitos relacionados ao [TransfereGov](https://www.gov.br/transferegov/pt-br) e indicam quais Ações são mapeadas neste modelo.
* **PNCV:** Elementos conceituais destacados que pertencem à Política Nacional Cultura Viva.

## Agrupamentos Lógicos e Descrição das Entidades

O modelo foi estruturado em blocos lógicos que representam os componentes e fases da política, desde os atores envolvidos até a execução final.

### Agentes do Fomento Cultural
*Contém as entidades que representam os atores centrais no fluxo da política.* 

| Entidade | Descrição | Relacionamentos |
| :--- | :--- | :--- |
| **Ente Federativo** | Instância da administração pública (Estado, DF ou Município) que atua como **gestor e executor** dos recursos da PNAB. É a entidade que recebe os repasses federais, define seu Plano de Aplicação de Recursos (PAR), publica os Editais e formaliza o fomento com os Agentes Culturais. Esta entidade **possui dicionário de dados** (aplicado na plataforma CultBR). | `Promove` **uma ou mais** Consultas Públicas; `Descreve` **uma ou mais** Atividades (PAR); `Realiza` **um ou mais** Editais; `Firma` **um ou mais** Instrumentos de Celebração. |
| **Agente Cultural** | Entidade **lógica**, que representa a persona central do fomento (proponentes e executores). No âmbito da PNAB, podem ser reconhecidos como agentes culturais tanto pessoas físicas (Agente Individual) quanto organizações (Pessoa Jurídica ou Coletivo Informal). Não possui dicionário próprio, sendo materializada por seus subtipos. | `Firma` **um ou mais** Instrumentos de Celebração; `Submete` **uma ou mais** Propostas. (Executa o conceito de Ação Cultural). |
| **Agente Individual** | Subtipo de Agente Cultural. Representa a pessoa física que atua em nome próprio, podendo ser classificada conceitualmente como Pessoa Física ou Microempreendedor Individual (MEI). Esta entidade **possui dicionário de dados** e é objeto da coleta da **PARTE I** do PADRÃO SNIIC PARA COLETA DE DADOS - PNAB CICLO 2. | Herda todos os relacionamentos de `Agente Cultural`. |
| **Pessoa Jurídica** | Subtipo de Agente Cultural. Representa a entidade coletiva com CNPJ, classificada conceitualmente como "com fins lucrativos" ou "sem fins lucrativos (OSC)". Esta entidade **possui dicionário de dados** e é objeto da coleta da **PARTE I** do PADRÃO SNIIC PARA COLETA DE DADOS - PNAB CICLO 2. | Herda todos os relacionamentos de `Agente Cultural`. |
| **Coletivo Informal** | Subtipo de Agente Cultural. Representa o grupo ou coletivo cultural sem CNPJ, representado por uma pessoa física. É a entidade que se inscreve no edital e executa a proposta. Esta entidade **possui dicionário de dados** e é objeto da coleta da **PARTE I** do PADRÃO SNIIC PARA COLETA DE DADOS - PNAB CICLO 2. | Herda todos os relacionamentos de `Agente Cultural`. |

### Plano de Aplicação de Recursos
*Mapeia o planejamento e a pactuação das ações que serão executadas pelo Ente Federativo.*

| Entidade | Descrição | Relacionamentos |
| :--- | :--- | :--- |
| **Atividade (PAR)** | Representa cada uma das ações planejadas pelo Ente Federativo em seu Plano de Aplicação de Recursos (PAR), detalhando o que será executado. É a entidade que conecta o planejamento (TransfereGov) à execução (Editais). Esta entidade **possui dicionário de dados** (aplicado no sistema CultBR). | É `Descrita` por **um** Ente Federativo; É `Fundamentada` por **uma ou mais** Consultas Públicas; e `Viabiliza` **um ou mais** Editais. |
| **Consulta Pública** | Representa o processo de participação social (ex: oitivas, audiências) para a elaboração do PAR, cujos resultados fundamentam o planejamento das Atividades. Esta entidade **possui dicionário de dados** (aplicado no sistema CultBR). | É `Realizada` por **um** Ente Federativo; `Fundamenta` **uma** Atividade (PAR); `Recebe participação` de **um ou mais** Públicos / Participantes. |

### Chamamento Público
*Detalha as entidades que vão desde o processo de seleção pública (Edital) até a submissão de Propostas pelos agentes.*

| Entidade | Descrição | Relacionamentos |
| :--- | :--- | :--- |
| **Edital** | Processo administrativo de seleção pública (Chamamento Público) que convoca Agentes Culturais a apresentarem propostas para receberem fomento. É o principal instrumento de execução da Atividade (PAR). Esta entidade **possui dicionário de dados** (aplicado no sistema CultBR). | É `Realizado` por **um** Ente Federativo; É `Viabilizado` por **uma** Atividade (PAR); `Seleciona` **uma ou mais** Propostas; `Fundamenta` **um ou mais** Instrumentos de Celebração. |
| **Proposta** | Documento detalhado submetido por um Agente Cultural em resposta a um Edital. Descreve o objeto, objetivos e orçamento do projeto. Esta é uma entidade **abstrata** e não possui dicionário, sendo materializada pelos seus subtipos. | É `Submetida` por **um** Agente Cultural; É `Selecionada` por **um** Edital. (Compõe o conceito de Ação Cultural). |
| **Proposta de Ação Cultural** | Subtipo de Proposta. Caracteriza as **ações culturais** propostas pelos agentes, detalhando o projeto (ex: festival, circulação, oficina). Esta entidade **possui dicionário de dados** e é objeto da coleta da **PARTE I** do PADRÃO SNIIC PARA COLETA DE DADOS - PNAB CICLO 2. | Herda relacionamentos de `Proposta`. |
| **Proposta de Subsídio** | Subtipo de Proposta. Caracteriza a solicitação de **subsídio para a manutenção de espaços e equipamentos culturais** (conforme Art. 7º da PNAB). Esta entidade **possui dicionário de dados** e é objeto da coleta da **PARTE I** do PADRÃO SNIIC PARA COLETA DE DADOS - PNAB CICLO 2. | Herda relacionamentos de `Proposta`. |
| **Proposta de Bolsa** | Subtipo de Proposta. Caracteriza a solicitação de **bolsas** para atividades de formação, pesquisa, intercâmbio ou residências artísticas. Esta entidade **possui dicionário de dados** e é objeto da coleta da **PARTE I** do PADRÃO SNIIC PARA COLETA DE DADOS - PNAB CICLO 2. | Herda relacionamentos de `Proposta`. |
| **Proposta de Premiação** | Subtipo de Proposta. Caracteriza a solicitação de **prêmios** por reconhecimento de trajetória, obras ou iniciativas (culturais ou de mestres/mestras). Esta entidade **possui dicionário de dados** e é objeto da coleta da **PARTE I** do PADRÃO SNIIC PARA COLETA DE DADOS - PNAB CICLO 2. | Herda relacionamentos de `Proposta`. (Nota: Premiações não descrevem ações futuras). |
| **Instrumento de Celebração** | Documento que formaliza a relação entre o Ente Federativo e o Agente Cultural (ex: Termo de Execução Cultural, Termo de Fomento, etc.), estabelecendo direitos e obrigações. Esta é uma entidade **conceitual** e não possui dicionário. | É `Firmado` por **um** Ente Federativo e **um** Agente Cultural; É `Fundamentado` por **um** Edital; `Formaliza` **uma ou mais** Ações Realizadas. |


### Ações Culturais
*Este agrupamento lógico descreve o fluxo de execução e comprovação das ações culturais fomentadas.*

| Entidade | Descrição | Relacionamentos |
| :--- | :--- | :--- |
| **Público / Participante** | Entidade **conceitual** que representa o público que acessa as entregas das ações culturais,garantindo a efetivação de direitos culturais. Não possui dicionário, sendo seus dados coletados de forma agregada na entidade `Entrega`. | `Participa` de **uma ou mais** Consultas Públicas; `Acessa` **uma ou mais** Entregas. |
| **Ação Realizada** | Representa a **execução** da ação cultural, ou seja, o que foi efetivamente realizado (diferente do plano da Proposta). Esta entidade **possui dicionário de dados** e é objeto da coleta da **PARTE II** (Relatório de Execução) do PADRÃO SNIIC PARA COLETA DE DADOS - PNAB CICLO 2. | É `Formalizada` por **um** Instrumento de Celebração; `Viabiliza` **uma ou mais** Entregas. |
| **Entrega** | Representa os produtos, serviços ou eventos **concretos e reportados** como resultado da Ação Realizada (ex: um show, um filme, uma oficina). É a unidade de comprovação da execução. Esta entidade **possui dicionário de dados** e é objeto da coleta da **PARTE II** (Relatório de Execução) do PADRÃO SNIIC PARA COLETA DE DADOS - PNAB CICLO 2. | É `Viabilizada` por **uma** Ação Realizada; É `Acessada` por **um ou mais** Públicos / Participantes. |
