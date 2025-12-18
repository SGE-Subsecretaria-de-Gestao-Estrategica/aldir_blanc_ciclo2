[< Voltar ao Guia de Adoção](guia_pratico.md) | [Ir para o Padrão SNIIC](README.md)

# Guia de Adoção - Cenário 4: Construção de Novo Sistema

Este guia detalha o plano de ação para Entes Federativos que irão **desenvolver um software do zero** (com equipe própria) ou **licitar/contratar um novo sistema** de gestão de editais.

### Perfil do Ente
Este cenário é para entes (geralmente de médio e grande porte) que estão em processo de licitação/contratação ou que possuem equipes de desenvolvimento próprias para criar uma nova solução de gestão cultural. É a oportunidade de "começar certo", com um sistema 100% aderente.

### Vantagens e Desafios
* **Vantagens:**
    * **Aderência Nativa:** O sistema já nasce 100% compatível com o Padrão SNIIC (dicionários, listas e fluxo).
    * **Garante Rastreabilidade:** Permite criar a arquitetura de banco de dados correta desde o início, garantindo a ligação entre Agentes, Propostas e Ações Realizadas.
    * **Integração Futura (API):** O sistema pode ser construído prevendo a comunicação direta com a plataforma Cult.BR, eliminando o trabalho manual de exportação/importação de arquivos.
* **Desafios / Pontos de Atenção:**
    * **Custo e Tempo:** É o cenário que exige maior investimento financeiro e tempo de desenvolvimento ou contratação.
    * **Requisito Crítico (TR):** O sucesso depende inteiramente da qualidade do **Termo de Referência (TR)** da licitação. Se o Padrão SNIIC não estiver detalhado nos requisitos, o sistema entregue pode não ser aderente.

### Guia Passo-a-Passo
O sucesso deste cenário depende da qualidade dos requisitos técnicos definidos no início. Os dicionários e listas deste repositório são seus principais documentos de requisitos.

#### 1. Definição de Requisitos (Termo de Referência - TR)
Este é o passo fundamental. O Termo de Referência (TR) da licitação (ou a documentação de requisitos para a equipe de desenvolvimento) **deve** considerar e incluir os 4 arquivos do Padrão SNIIC como anexos técnicos:

* [mer_pnab.md](mer_pnab.md) (para a lógica de fluxo e arquitetura)
* [dicionario-fase-1.md](dicionario-fase-1.md) (para os formulários de inscrição)
* [dicionario-fase-2.md](dicionario-fase-2.md) (para os formulários de relatório)
* [listas-de-valores.md](listas-de-valores.md) (para os vocabulários controlados)

#### 2. Requisitos Técnicos (Back-End / Banco de Dados)
O TR deve exigir que o banco de dados do novo sistema utilize:
* Os **`Nomes formatados`** (ex: `nome_completo`) como os nomes das colunas nas tabelas.
* Os **`Valores possíveis`** (ex: `Texto Curto (até 100 caracteres)`) para definir os tipos e tamanhos dos dados (ex: `VARCHAR(100)`).
* As **`Listas de Valores`** devem ser importadas para tabelas de domínio no banco de dados (ex: `tbl_segmentos`, `tbl_pautas`).
* **Segurança e Privacidade (LGPD):** O TR deve prever requisitos de segurança da informação e conformidade com a **Lei Geral de Proteção de Dados (LGPD)** e outras leis cabíveis. Isso é especialmente crítico no tratamento de dados sensíveis (como os de `Cor/Raça`, `Gênero`, `Pessoa com deficiência`) e dados pessoais (CPF, Renda), exigindo controle de acesso e armazenamento seguro.
#### 3. Requisitos Técnicos (Front-End / Telas de Inscrição)
O TR deve exigir que as interfaces (telas e formulários) sigam as melhores práticas de experiência do usuário, priorizando:
* **Acessibilidade Digital:** O sistema deve seguir as diretrizes do [Modelo de Acessibilidade em Governo Eletrônico (eMAG)](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/modelo-de-acessibilidade). Isso garante que pessoas com deficiência (visuais, auditivas, motoras) possam se inscrever de forma autônoma (ex: compatibilidade total com leitores de tela, navegação por teclado, contraste adequado).
* **Linguagem Simples:** Os textos dos formulários, rótulos de campo e, principalmente, os textos de ajuda (que podem ser baseados na coluna `Finalidade` dos dicionários) devem ser escritos em linguagem clara, direta e acessível, evitando jargões técnicos ou burocráticos.
* **Vocabulários Controlados:** Os campos de seleção (dropdowns) devem ser populados *exclusivamente* a partir das tabelas de domínio (Listas de Valores) para garantir a integridade dos dados.
#### 4. Requisitos Técnicos (Exportação / API)
O TR deve prever como os dados serão enviados ao MinC:
* **Mínimo:** O sistema deve, nativamente, ser capaz de exportar os dados da Fase 1 e Fase 2 seguindo 100% o Padrão SNIIC (em formato JSON ou CSV com `Nomes formatados` nos cabeçalhos).
* **Ideal:** O sistema deve possuir uma **API** para comunicação direta com a plataforma Cult.BR, eliminando a necessidade de exportação/importação manual de arquivos. 

### Modelos e Exemplos (Disponibilizados em Breve)
* *Um script SQL `CREATE TABLE` de exemplo (PostgreSQL/MySQL) para a criação da estrutura do banco de dados.*
* *Um exemplo de estrutura de API/JSON para modelagem de envio de dados ao MinC.*
