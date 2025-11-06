# Dicionários de Dados - Fase 1: Inscrição

Informações a serem solicitadas durante a inscrição.

## A. Agentes Culturais - Pessoa física

Informações mínimas que caracterizam o agente cultural pessoa física e sua trajetória, a serem coletadas durante a inscrição.

| Atributo / Descrição | Finalidade | Nome formatado | Valores possíveis |
| :--- | :--- | :--- | :--- |
| **Tipo de agente cultural individual** <br> Classificação do tipo de proponente individual. | Diferenciar a natureza do proponente (Pessoa Física ou MEI) para aplicação de regras de validação e fomento. | tipo_agente_individual | Seleção única: <br> • Pessoa física <br> • Microempreendedor individual - MEI |
| **CPF** <br> Identificador numérico e intransferível do Cadastro de Pessoas Físicas (CPF). | Identifica a pessoa física nos sistemas oficiais, permitindo integração e validação. | cpf | CPF Válido |
| **CNPJ** <br> Número de inscrição no Cadastro Nacional da Pessoa Jurídica (aplicável apenas a MEI). | Viabilizar a validação da regularidade fiscal e jurídica do MEI em bases oficiais. | cnpj_mei | CNPJ Válido (se aplicável) |
| **Nome completo** <br> Nome civil do indivíduo, conforme registrado em documento oficial de identificação. | Identificar formalmente o indivíduo em todos os atos oficiais da política, garantindo segurança jurídica. | nome_completo | Texto Curto (até 100 caracteres) |
| **Nome artístico ou Nome Social** <br> Designação pela qual a pessoa se identifica, é socialmente reconhecida ou conhecida artisticamente. | Assegurar o respeito à identidade de gênero e/ou registrar o nome artístico para fins de comunicação e identificação no setor cultural. | nome_social_artistico | Texto Curto (até 100 caracteres) |
| **Data de nascimento** <br> Data de nascimento completa do indivíduo. | Permitir a verificação de critérios de elegibilidade (como maioridade) e a produção de análises sobre o perfil etário dos beneficiários. | data_nascimento | Data (dd/mm/aaaa) |
| **E-mail** <br> Endereço de correio eletrônico para contato. | Principal canal de comunicação oficial com o agente cultural para notificações, convocações e informes. | email | Texto (Validado como e-mail) |
| **Telefone** <br> Número de telefone para contato (preferencialmente móvel). | Canal de comunicação secundário ou alternativo com o agente cultural. | telefone | Número (com DDD) |
| **CEP** <br> Código de Endereçamento Postal da residência. | Permitir a geolocalização do agente para análises sobre a distribuição territorial dos recursos. | cep | CEP Válido |
| **Estado** <br> Unidade Federativa de residência do agente. | Padronizar a identificação geográfica para a geração de relatórios sobre a capilaridade da PNAB. | uf_residencia | Texto (ou seleção de lista) |
| **Cidade** <br> Município de residência do agente. | Padronizar a identificação geográfica para a geração de relatórios sobre a capilaridade da PNAB. | municipio_residencia | Texto (ou seleção de lista) |
| **Endereço completo** <br> Logradouro, número, bairro e complemento da residência. | Qualificar a localização do agente para fins operacionais e comprovação de residência quando necessário. | endereco_completo | Texto Longo (até 200 caracteres) |
| **Pertence a povos e comunidades tradicionais?** <br> Vinculação do agente a povos e comunidades tradicionais. | Mapear e fomentar a participação de povos e comunidades tradicionais, garantindo a aplicação de políticas afirmativas. | comunidade_tradicional | Seleção múltipla a partir da [Lista 1. Povos e comunidades tradicionais](listas-de-valores.md#1-povos-e-comunidades-tradicionais). |
| **É mestre ou mestra das culturas tradicionais e populares?** <br> Reconhecimento (autodeclarado ou formal) como mestre ou mestra. | Identificar e valorizar os mestres e mestras, permitindo análises sobre o fomento aos saberes tradicionais. | mestre_cultura_popular | Booleano (Sim/Não) |
| **Gênero** <br> Autodeclaração de identidade de gênero do indivíduo. | Produzir dados e diagnósticos sobre a diversidade de gênero no setor cultural, orientando a aplicação de políticas afirmativas. | genero | Seleção única a partir da [Lista 2. Gênero](listas-de-valores.md#2-gênero). |
| **Orientação sexual** <br> Autodeclaração de orientação sexual do indivíduo. | Coletar dados para a produção de relatórios de diversidade e para o monitoramento da efetividade de políticas afirmativas. | orientacao_sexual | Seleção única a partir da [Lista 3. Orientação sexual](listas-de-valores.md#3-orientação-sexual). |
| **Cor/raça/etnia** <br> Autodeclaração de pertencimento racial, conforme categorias do IBGE. | Coletar dados para diagnósticos sobre equidade racial no acesso aos recursos da PNAB, fundamentando ações afirmativas. | cor_raca | Seleção única a partir da [Lista 4. Cor/Raça/Etnia](listas-de-valores.md#4-corraçaetnia). |
| **É pessoa com deficiência?** <br> Autodeclaração da condição de deficiência. | Identificar pessoas com deficiência para garantir a aplicação de ações afirmativas e monitorar a inclusão. | pessoa_com_deficiencia | Seleção múltipla a partir da [Lista 5. Pessoa com deficiência](listas-de-valores.md#5-pessoa-com-deficiência). |
| **Escolaridade** <br> Nível de instrução formal mais elevado alcançado. | Caracterizar o perfil de instrução dos agentes, informação relevante para relatórios e diagnósticos. | escolaridade | Seleção única a partir da [Lista 6. Escolaridade](listas-de-valores.md#6-escolaridade). |
| **Renda média individual (R$)** <br> Faixa de rendimento mensal individual do agente. | Coletar informações para a aplicação de critérios socioeconômicos em ações afirmativas e para a análise do perfil de renda. | faixa_renda | Seleção única a partir da [Lista 7. Renda média individual (R$)](listas-de-valores.md#7-renda-média-individual-r). |
| **Possui quantos anos de experiência na área cultural?** <br> Tempo de atuação profissional (em anos) no setor cultural. | Analisar o perfil de senioridade dos agentes fomentados e correlacionar experiência com acesso a recursos. | anos_experiencia_cultural | Número Inteiro |
| **Acessou recursos públicos de fomento à cultura nos últimos 5 (cinco) anos?** <br> Histórico de acesso a editais ou fomento direto. | Mapear a capilaridade da política e identificar agentes que acessam recursos pela primeira vez. | acessou_recursos_5anos | Seleção única (Sim/Não/Não sei) |

## B. Agentes Culturais - Pessoa jurídica

Informações mínimas que caracterizam as organizações culturais e sua trajetória.

| Atributo / Descrição | Finalidade | Nome formatado | Valores possíveis |
| :--- | :--- | :--- | :--- |
| **Tipo de pessoa jurídica** <br> Classificação da natureza jurídica da entidade. | Diferenciar os proponentes (com ou sem fins lucrativos) para a aplicação de regras de habilitação e validações de sistema. | tipo_pessoa_juridica | Seleção única: <br> • Pessoa Jurídica com fins lucrativos (empresas) <br> • Pessoa Jurídica sem fins lucrativos (OSCs) |
| **CNPJ** <br> Número de inscrição no Cadastro Nacional da Pessoa Jurídica. | Viabilizar a validação da regularidade fiscal e jurídica da organização em bases oficiais. | cnpj | CNPJ Válido |
| **Razão social** <br> Nome oficial (PJ) conforme registro no CNPJ. | Identificar formalmente a organização em todos os documentos e interfaces públicas da PNAB. | razao_social | Texto Curto (até 100 caracteres) |
| **Nome fantasia** <br> Nome de referência (fantasia) da organização. | Identificar a organização pelo seu nome público ou comercial, facilitando o reconhecimento pela comunidade. | nome_fantasia | Texto Curto (até 100 caracteres) |
| **Data de fundação** <br> Data de criação formal ou do início das atividades da organização. | Permitir a aplicação de critérios de elegibilidade baseados no tempo de atuação da organização. | data_fundacao | Data (dd/mm/aaaa) |
| **Nome do representante legal** <br> Nome completo do indivíduo responsável legalmente pela organização. | Identificar o responsável legal para fins de assinatura de termos e responsabilidade jurídica. | nome_representante_legal | Texto Curto (até 100 caracteres) |
| **CPF do representante legal** <br> CPF do indivíduo responsável legalmente pela organização. | Validar o representante legal nos sistemas oficiais e vincular o responsável à organização. | cpf_representante_legal | CPF Válido |
| **E-mail** <br> Endereço de correio eletrônico institucional ou do responsável. | Principal canal de comunicação oficial com a organização para notificações e informes. | email_organizacao | Texto (Validado como e-mail) |
| **Telefone** <br> Número de telefone institucional ou do responsável. | Canal de comunicação secundário ou alternativo com a organização. | telefone_organizacao | Número (com DDD) |
| **CEP da sede** <br> Código de Endereçamento Postal da sede da organização. | Permitir a geolocalização da sede para fins de análise da distribuição territorial dos recursos. | cep_sede | CEP Válido |
| **Endereço completo (da sede)** <br> Logradouro, número, bairro e complemento da sede. | Qualificar a localização da organização para fins operacionais e comprovação de endereço. | endereco_sede | Texto Longo (até 200 caracteres) |
| **Cidade** <br> Município da sede da organização. | Padronizar a identificação geográfica para a geração de relatórios sobre a capilaridade da PNAB. | municipio_sede | Texto (ou seleção de lista) |
| **Estado** <br> Unidade Federativa da sede da organização. | Padronizar a identificação geográfica para a geração de relatórios sobre a capilaridade da PNAB. | uf_sede | Texto (ou seleção de lista) |
| **Anos de atuação na área cultural?** <br> Tempo de atuação (em anos) da organização no setor cultural. | Analisar o perfil de senioridade das organizações fomentadas e correlacionar experiência com acesso a recursos. | anos_atuacao_cultural | Número Inteiro |
| **A organização acessou recursos públicos de fomento à cultura nos últimos 5 (cinco) anos?** <br> Histórico de acesso a editais ou fomento direto. | Mapear a capilaridade da política e identificar organizações que acessam recursos pela primeira vez. | acessou_recursos_5anos_org | Seleção única (Sim/Não/Não sei) |

## C. Agentes Culturais - Coletivos sem constituição jurídica

Informações mínimas que caracterizam a trajetória de grupos e coletivos culturais.

| Atributo / Descrição | Finalidade | Nome formatado | Valores possíveis |
| :--- | :--- | :--- | :--- |
| **Nome do grupo ou coletivo** <br> Nome de referência do coletivo cultural. | Identificar formalmente o coletivo em todos os documentos e interfaces públicas da PNAB. | nome_coletivo | Texto Curto (até 100 caracteres) |
| **Quantas pessoas fazem parte do coletivo** <br> Número de membros integrantes do coletivo. | Dimensionar o alcance e a estrutura dos coletivos informais fomentados. | qtd_membros_coletivo | Número Inteiro |
| **Nome do representante** <br> Nome completo do indivíduo que representa o coletivo. | Identificar o responsável pela proposta e pela comunicação em nome do coletivo. | nome_representante_coletivo | Texto Curto (até 100 caracteres) |
| **CPF do representante** <br> CPF do indivíduo que representa o coletivo. | Validar o representante e vinculá-lo à proposta do coletivo, visto que o coletivo não possui CNPJ. | cpf_representante_coletivo | CPF Válido |
| **E-mail** <br> Endereço de correio eletrônico do representante. | Principal canal de comunicação oficial com o coletivo. | email_coletivo | Texto (Validado como e-mail) |
| **Telefone** <br> Número de telefone do representante. | Canal de comunicação secundário ou alternativo com o coletivo. | telefone_coletivo | Número (com DDD) |
| **CEP da sede** <br> CEP do local de referência ou sede do coletivo. | Permitir a geolocalização do coletivo para fins de análise da distribuição territorial dos recursos. | cep_coletivo | CEP Válido |
| **Endereço completo da sede** <br> Endereço do local de referência ou sede do coletivo. | Qualificar a localização do coletivo para fins operacionais e comprovação de atuação territorial. | endereco_coletivo | Texto Longo (até 200 caracteres) |
| **Cidade** <br> Município da sede do coletivo. | Padronizar a identificação geográfica para a geração de relatórios sobre a capilaridade da PNAB. | municipio_coletivo | Texto (ou seleção de lista) |
| **Estado** <br> Unidade Federativa da sede do coletivo. | Padronizar a identificação geográfica para a geração de relatórios sobre a capilaridade da PNAB. | uf_coletivo | Texto (ou seleção de lista) |
| **Anos de atuação na área cultural?** <br> Tempo de atuação (em anos) do coletivo no setor cultural. | Analisar o perfil de senioridade dos coletivos fomentados e correlacionar experiência com acesso a recursos. | anos_atuacao_coletivo | Número Inteiro |
| **O grupo ou coletivo acessou recursos públicos de fomento à cultura nos últimos 5 (cinco) anos?** <br> Histórico de acesso a editais ou fomento direto. | Mapear a capilaridade da política e identificar coletivos que acessam recursos pela primeira vez. | acessou_recursos_5anos_col | Seleção única (Sim/Não/Não sei) |

## D. Proposta de ação cultural

Informações mínimas que caracterizam as ações culturais propostas pelos agentes culturais.

| Atributo / Descrição | Finalidade | Nome formatado | Valores possíveis |
| :--- | :--- | :--- | :--- |
| **Edital vinculado** <br> Identificação do edital ao qual a proposta está concorrendo. | Vincular a proposta ao seu respectivo processo seletivo (Edital) de origem para rastreabilidade. | id_edital | Texto Curto (até 100 caracteres) |
| **A proposta foi selecionada em alguma modalidade de reserva de vagas (cotas)?** <br> Indica se a proposta foi classificada via política de ação afirmativa. | Monitorar a eficácia das políticas de cotas e ações afirmativas nos editais da PNAB. | selecionado_cotas | Seleção única: <br> • Proposta selecionada em ampla concorrência <br> • Reserva de vagas para pessoas negras <br> • Reserva de vagas para pessoas indígenas <br> • Reserva de vagas para pessoas com deficiência <br> • Reserva de vagas para outros grupos |
| **Título da proposta** <br> Nome do projeto, ação ou proposta cultural submetida. | Identificar o projeto cultural durante todo o processo de seleção e acompanhamento. | titulo_proposta | Texto Curto (até 100 caracteres) |
| **Resumo da ação proposta** <br> Breve descrição da proposta de ação cultural. | Fornecer uma visão geral do escopo, relevância e principais características do projeto. | resumo_proposta | Texto Longo (até 1000 caracteres) |
| **Valor da proposta** <br> Montante de recursos solicitado para a execução do projeto. | Registrar o montante solicitado para a análise orçamentária e controle de repasses. | valor_proposta | Valor Monetário (R$) |
| **A ação cultural proposta será realizada em qual formato?** <br> Indica o modo de execução da proposta. | Classificar as propostas quanto à sua natureza (presencial, online, híbrida) para análises de formato e alcance. | formato_proposta | Seleção única: <br> • Presencialmente em local fixo <br> • Presencialmente itinerante <br> • Remotamente/Online <br> • Em formato híbrido <br> • Outros <br> • Não aplicável |
| **Qual o CEP do local de realização? (se aplicável)** <br> CEP principal do local onde a ação presencial ou híbrida ocorrerá. | Permitir a geolocalização das ações fomentadas para análise de distribuição territorial. | cep_local_realizacao | CEP Válido (se aplicável) |
| **Quantas pessoas serão remuneradas com o recurso do edital?** <br> Estimativa de postos de trabalho diretos gerados pela proposta. | Mensurar o impacto econômico e a geração de trabalho e renda fomentados pela PNAB. | qtd_pessoas_remuneradas | Número Inteiro |
| **Qual o principal segmento contemplado pela proposta?** <br> Área ou linguagem cultural principal da proposta. | Classificar a atuação da proposta para permitir análises sobre a distribuição de recursos entre os diversos segmentos culturais. | segmento_cultural_principal | Seleção única a partir da [Lista 8. Segmento Cultural](listas-de-valores.md#8-segmento-cultural). |
| **Qual a principal etapa do ciclo cultural contemplada pela proposta?** <br> Fase da cadeia produtiva principal da proposta. | Identificar a(s) etapa(s) da cadeia produtiva da cultura que a proposta visa a fomentar. | etapa_ciclo_cultural_principal | Seleção única a partir da [Lista 9. Etapas do Ciclo Cultural](listas-de-valores.md#9-etapas-do-ciclo-cultural). |
| **Qual a principal pauta temática contemplada pela proposta?** <br> Temática transversal principal abordada pela proposta. | Mapear as transversalidades abordadas pelas propostas para análise do alinhamento com eixos estratégicos. | pauta_tematica_principal | Seleção única a partir da [Lista 10. Pautas Temáticas](listas-de-valores.md#10-pautas-temáticas). |
| **A proposta prevê ações em algum território prioritário?** <br> Indica se o escopo da proposta inclui atuação em territórios prioritários. | Identificar o foco territorial da proposta para analisar a distribuição de recursos em territórios estratégicos. | atua_territorio_prioritario | Seleção múltipla a partir da [Lista 11. Territórios Prioritários](listas-de-valores.md#11-territórios-prioritários). |
| **Quais as principais entregas previstas pela proposta?** <br> Lista dos principais produtos, serviços ou eventos a serem realizados. | Definir o escopo de entregáveis da proposta para fins de monitoramento e prestação de contas. | entregas_previstas | Seleção múltipla a partir da [Lista 12. Tipos de Entregas](listas-de-valores.md#12-tipos-de-entregas). |

## E. Proposta de subsídio a espaços e equipamentos culturais

Informações mínimas que caracterizam os espaços e equipamentos culturais selecionados para receber subsídios.

| Atributo / Descrição | Finalidade | Nome formatado | Valores possíveis |
| :--- | :--- | :--- | :--- |
| **Edital vinculado** <br> Identificação do edital ao qual a proposta está concorrendo. | Vincular a proposta ao seu respectivo processo seletivo (Edital) de origem para rastreabilidade. | id_edital | Texto Curto (até 100 caracteres) |
| **A proposta foi selecionada em alguma modalidade de reserva de vagas (cotas)?** <br> Indica se o espaço foi classificado via política de ação afirmativa. | Monitorar a eficácia das políticas de cotas e ações afirmativas nos editais de subsídio. | selecionado_cotas_espaco | Seleção única: <br> • Proposta selecionada em ampla concorrência <br> • Reserva de vagas para pessoas negras <br> • Reserva de vagas para pessoas indígenas <br> • Reserva de vagas para pessoas com deficiência <br> • Reserva de vagas para outros grupos |
| **Nome do espaço, ambiente ou iniciativa** <br> Nome oficial ou de referência do espaço cultural. | Identificar o espaço cultural beneficiado pelo subsídio. | nome_espaco_cultural | Texto Curto (até 100 caracteres) |
| **Qual o CEP do espaço?** <br> CEP do endereço do espaço cultural. | Permitir a geolocalização dos espaços subsidiados para análise de distribuição territorial. | cep_espaco | CEP Válido |
| **Tipo de espaço** <br> Classificação do tipo de espaço ou equipamento cultural. | Permitir que o Ente Federativo defina quais tipos de espaços culturais são elegíveis para receber subsídios. | tipo_espaco_cultural | Seleção múltipla a partir da [Lista 13. Tipos de Espaços e Equipamentos Culturais](listas-de-valores.md#13-tipos-de-espaços-e-equipamentos-culturais). |
| **Porte do espaço** <br> Porte físico (área) do espaço cultural. | Permitir que o Ente Federativo defina as faixas de porte dos espaços elegíveis para o subsídio. | porte_espaco_cultural | Seleção única: <br> • Pequeno: até 499 m² <br> • Médio: de 500 m² a 1999 m² <br> • Grande: acima de 2000 m² <br> • Não se aplica |
| **Quais os principais segmentos do espaço cultural?** <br> Áreas ou linguagens culturais principais de atuação do espaço. | Classificar a atuação do espaço para permitir análises sobre a distribuição de recursos entre os diversos segmentos culturais. | segmentos_espaco_cultural | Seleção múltipla a partir da [Lista 8. Segmento Cultural](listas-de-valores.md#8-segmento-cultural). |
| **O espaço cultural está localizado em território prioritário?** <br> Indica se o espaço está fisicamente localizado em um território prioritário. | Identificar o foco territorial do espaço para analisar a distribuição de recursos em territórios estratégicos. | espaco_territorio_prioritario | Seleção múltipla a partir da [Lista 11. Territórios Prioritários](listas-de-valores.md#11-territórios-prioritários). |
| **O espaço cultural existe há quantos anos?** <br> Tempo de existência (em anos) do espaço cultural. | Analisar o perfil de senioridade e a consolidação dos espaços culturais fomentados. | anos_existencia_espaco | Número Inteiro |
| **O espaço acessou recursos públicos de fomento à cultura nos últimos 5 (cinco) anos?** <br> Histórico de acesso a editais ou fomento direto. | Mapear a capilaridade da política e identificar espaços que acessam recursos pela primeira vez. | acessou_recursos_5anos_esp | Seleção única (Sim/Não/Não sei) |
| **Valor total do subsídio** <br> Montante total de recursos de subsídio a ser recebido. | Registrar o valor total do fomento recebido, para fins de controle financeiro. | valor_total_subsidio | Valor Monetário (R$) |
| **Quantidade de parcelas** <br> Número de parcelas em que o subsídio será pago. | Definir o cronograma de desembolso financeiro para o espaço cultural. | qtd_parcelas_subsidio | Número Inteiro |

## F. Proposta de bolsa

Informações mínimas que caracterizam as propostas de bolsa, a serem coletadas durante a inscrição.

| Atributo / Descrição | Finalidade | Nome formatado | Valores possíveis |
| :--- | :--- | :--- | :--- |
| **Edital vinculado** <br> Identificação do edital ao qual a proposta está concorrendo. | Vincular a proposta ao seu respectivo processo seletivo (Edital) de origem para rastreabilidade. | id_edital | Texto Curto (até 100 caracteres) |
| **A proposta foi selecionada em alguma modalidade de reserva de vagas (cotas)?** <br> Indica se a proposta foi classificada via política de ação afirmativa. | Monitorar a eficácia das políticas de cotas e ações afirmativas nos editais da PNAB. | selecionado_cotas | Seleção única: <br> • Proposta selecionada em ampla concorrência <br> • Reserva de vagas para pessoas negras <br> • Reserva de vagas para pessoas indígenas <br> • Reserva de vagas para pessoas com deficiência <br> • Reserva de vagas para outros grupos |
| **Título da proposta** <br> Nome do projeto de bolsa submetido. | Identificar o projeto cultural durante todo o processo de seleção e acompanhamento. | titulo_proposta | Texto Curto (até 100 caracteres) |
| **Resumo da ação proposta** <br> Breve descrição da proposta de bolsa (formação, pesquisa, intercâmbio, etc.). | Fornecer uma visão geral do escopo, relevância e principais características do projeto. | resumo_proposta | Texto Longo (até 1000 caracteres) |
| **Valor da proposta** <br> Montante de recursos solicitado para a bolsa. | Registrar o montante solicitado para a análise orçamentária e controle de repasses. | valor_proposta | Valor Monetário (R$) |
| **Quantas pessoas serão remuneradas com o recurso da bolsa?** <br> Número de bolsistas diretos. | Mensurar o impacto direto do fomento na formação e pesquisa. | qtd_pessoas_remuneradas | Número Inteiro |
| **Qual o principal segmento da formação ou atividade que será realizada?** <br> Área ou linguagem cultural principal da bolsa. | Classificar a atuação da proposta para permitir análises sobre a distribuição de recursos entre os diversos segmentos culturais. | segmento_cultural_principal | Seleção única a partir da [Lista 8. Segmento Cultural](listas-de-valores.md#8-segmento-cultural). |
| **Qual a principal pauta temática contemplada pela proposta?** <br> Temática transversal principal abordada pela bolsa. | Mapear as transversalidades abordadas pelas propostas para análise do alinhamento com eixos estratégicos. | pauta_tematica_principal | Seleção única a partir da [Lista 10. Pautas Temáticas](listas-de-valores.md#10-pautas-temáticas). |
| **A bolsa irá custear qual categoria de atividades?** <br> Classificação da natureza da bolsa. | Identificar o objetivo principal da bolsa (pesquisa, difusão, intercâmbio). | categoria_atividades_bolsa | Seleção única: <br> • Pesquisa/Formação em educação patrimonial <br> • Pesquisa/Formação artístico-cultural ou técnica <br> • Pesquisa/Formação em política e gestão cultural <br> • Difusão/circulação artístico-cultural <br> • Participação em eventos <br> • Intercâmbios ou residências artísticas <br> • Outros (especificar) |
| **A bolsa irá custear atividades em qual âmbito?** <br> Abrangência geográfica da bolsa. | Diferenciar o alcance das ações de formação e intercâmbio fomentadas. | ambito_bolsa | Seleção única: <br> • Nacional <br> • Internacional <br> • Ambos (nacional e internacional) |
| **Qual o principal (ou principais) destino nacional custeado com recursos da bolsa?** <br> Município(s) de destino, se aplicável. | Mapear os fluxos de intercâmbio e formação dentro do país. | destino_nacional_bolsa | Texto (lista de municípios) |
| **Qual o principal (ou principais) destino internacional custeado com recursos da bolsa?** <br> País(es) de destino, se aplicável. | Mapear os fluxos de intercâmbio e formação internacionais. | destino_internacional_bolsa | Texto (lista de países) |
| **Do projeto resultará algum produto/entrega?** <br> Indica se a bolsa prevê uma entrega final (artigo, relatório, obra). | Identificar se a bolsa gerará um produto cultural ou de pesquisa rastreável. | gera_produto_entrega | Booleano (Sim/Não) |
| **Selecione o tipo de produto/entrega que mais se aproxima do previsto** <br> Classificação da entrega final da bolsa, se houver. | Definir o escopo de entregáveis da proposta para fins de monitoramento. | tipo_entrega_prevista | Seleção múltipla a partir da [Lista 12. Tipos de Entregas](listas-de-valores.md#12-tipos-de-entregas). |

## G. Proposta de premiação

Informações mínimas que caracterizam as propostas de premiação, a serem coletadas durante a inscrição.

| Atributo / Descrição | Finalidade | Nome formatado | Valores possíveis |
| :--- | :--- | :--- | :--- |
| **Edital vinculado** <br> Identificação do edital ao qual a proposta está concorrendo. | Vincular a proposta ao seu respectivo processo seletivo (Edital) de origem para rastreabilidade. | id_edital | Texto Curto (até 100 caracteres) |
| **A proposta foi selecionada em alguma modalidade de reserva de vagas (cotas)?** <br> Indica se a proposta foi classificada via política de ação afirmativa. | Monitorar a eficácia das políticas de cotas e ações afirmativas nos editais da PNAB. | selecionado_cotas | Seleção única: <br> • Proposta selecionada em ampla concorrência <br> • Reserva de vagas para pessoas negras <br> • Reserva de vagas para pessoas indígenas <br> • Reserva de vagas para pessoas com deficiência <br> • Reserva de vagas para outros grupos |
| **Valor da premiação** <br> Montante de recursos solicitado para o prêmio. | Registrar o montante solicitado para a análise orçamentária e controle de repasses. | valor_premiacao | Valor Monetário (R$) |
| **Qual o principal segmento de atuação do agente premiado?** <br> Área ou linguagem cultural principal do agente (ou obra) premiado. | Classificar a atuação do premiado para permitir análises sobre a distribuição de recursos entre os diversos segmentos culturais. | segmento_cultural_principal | Seleção única a partir da [Lista 8. Segmento Cultural](listas-de-valores.md#8-segmento-cultural). |
| **O agente premiado trabalha prioritariamente com alguma pauta temática? Qual?** <br> Temática transversal principal do agente (ou obra) premiado. | Mapear as transversalidades abordadas pelos premiados para análise do alinhamento com eixos estratégicos. | pauta_tematica_principal | Seleção única a partir da [Lista 10. Pautas Temáticas](listas-de-valores.md#10-pautas-temáticas). |
| **O agente premiado atua em algum território prioritário?** <br> Indica se o agente premiado atua em territórios prioritários. | Identificar o foco territorial do premiado para analisar a distribuição de recursos em territórios estratégicos. | atua_territorio_prioritario | Seleção múltipla a partir da [Lista 11. Territórios Prioritários](listas-de-valores.md#11-territórios-prioritários). |
