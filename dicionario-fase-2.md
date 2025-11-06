# Dicionários de Dados - Fase 2: Relatório de Execução Cultural

Informações a serem solicitadas no Relatório de Objeto da Execução Cultural dos agentes culturais.

## A. Ação Cultural Realizada

Informações mínimas que caracterizam as ações culturais realizadas, a serem enviadas ao MinC após o encerramento da prestação de contas de cada edital.

| Atributo / Descrição | Finalidade | Nome formatado | Valores possíveis |
| :--- | :--- | :--- | :--- |
| **A ação cultural foi selecionada em qual edital?** <br> Identificação do edital que fomentou a ação. | Vincular a ação cultural executada ao seu respectivo processo seletivo (Edital) de origem. | identificador_edital | Texto Curto (até 100 caracteres) |
| **CPF do responsável** <br> CPF do agente cultural responsável pela execução. | Identificar o agente cultural (PF) que executou a ação para fins de prestação de contas e rastreabilidade. | cpf_responsavel_execucao | CPF Válido |
| **CNPJ do responsável** <br> CNPJ do agente cultural responsável pela execução. | Identificar o agente cultural (PJ/MEI/Coletivo) que executou a ação para fins de prestação de contas e rastreabilidade. | cnpj_responsavel_execucao | CNPJ Válido (se aplicável) |
| **Início da execução** <br> Data efetiva de início das atividades da ação. | Auxiliar no monitoramento do cronograma, permitindo o acompanhamento do ciclo de vida da ação cultural. | data_inicio_execucao | Data (dd/mm/aaaa) |
| **Término da execução** <br> Data efetiva de encerramento das atividades da ação. | Permitir calcular a duração da ação e avaliar sua execução no tempo, sendo um dado crucial para relatórios de vigência. | data_termino_execucao | Data (dd/mm/aaaa) |
| **Valor recebido da PNAB** <br> Montante total de recursos da PNAB efetivamente recebidos. | Registrar o valor total do fomento recebido, para fins de controle financeiro e prestação de contas. | valor_recebido_pnab | Valor Monetário (R$) |
| **Data de recebimento dos recursos** <br> Data do primeiro pagamento (em caso de parcelamento). | Estabelecer o marco inicial financeiro da execução para fins de monitoramento e prestação de contas. | data_recebimento_recurso | Data (dd/mm/aaaa) |
| **A ação cultural recebeu recursos financeiros de outras fontes?** <br> Indicação de outras fontes de financiamento para o projeto. | Identificar se o projeto possui outras fontes de recursos, para compreender sua sustentabilidade. | recebeu_recursos_outras_fontes | Seleção múltipla a partir da [Lista 14. Recursos Financeiros de Outras Fontes](listas-de-valores.md#14-recursos-financeiros-de-outras-fontes). |
| **Qual o valor total dos recursos financeiros recebidos de outras fontes?** <br> Montante dos recursos provenientes de outras fontes. | Quantificar o valor de outras fontes de financiamento para uma análise completa do orçamento. | valor_recursos_outras_fontes | Valor Monetário (R$) |
| **Quantas pessoas foram remuneradas com o recurso do edital?** <br> Número de postos de trabalho diretos efetivamente gerados. | Mensurar o impacto econômico e a geração de trabalho e renda efetivados pela PNAB. | qtd_pessoas_remuneradas_exec | Número Inteiro |
| **CPF das pessoas remuneradas** <br> Lista de CPFs dos profissionais pagos com o recurso. | Permitir a rastreabilidade e a análise da distribuição de renda e do perfil dos profissionais envolvidos. | cpfs_remunerados | Lista de CPFs Válidos (separados por vírgula) |
| **A ação cultural foi realizada em qual formato?** <br> Indica o modo de execução efetivo da ação. | Classificar as ações quanto à sua natureza (presencial, online, híbrida) para análises de formato e alcance. | formato_execucao | Seleção única: <br> • Presencialmente em local fixo <br> • Presencialmente itinerante <br> • Remotamente/Online <br> • Em formato híbrido <br> • Outros <br> • Não aplicável |
| **Qual o CEP do local de realização da ação? (se aplicável)** <br> CEP principal do local onde a ação efetivamente ocorreu. | Permitir a geolocalização das ações fomentadas para análise de distribuição territorial. | cep_local_execucao | CEP Válido (se aplicável) |

## B. Entregas (Realizadas)

Informações mínimas que caracterizam entregas realizadas por cada ação cultural.

| Atributo / Descrição | Finalidade | Nome formatado | Valores possíveis |
| :--- | :--- | :--- | :--- |
| **A entrega está vinculada a qual edital?** <br> Identificação do edital que fomentou a entrega. | Vincular a entrega ao seu respectivo processo seletivo (Edital) de origem. | identificador_edital_entrega | Texto Curto (até 100 caracteres) |
| **Tipo de entrega** <br> Classificação da natureza da entrega realizada (ex: relatório, produto cultural, evento). | Categorizar as entregas para facilitar a análise da prestação de contas e a avaliação dos diferentes tipos de resultados. | tipo_entrega | Seleção única a partir da [Lista 12. Tipos de Entregas](listas-de-valores.md#12-tipos-de-entregas). |
| **Qual o principal segmento da entrega realizada?** <br> Área ou linguagem cultural principal da entrega. | Classificar a entrega para permitir análises sobre a distribuição de recursos entre os diversos segmentos culturais. | segmento_cultural_entrega | Seleção única a partir da [Lista 8. Segmento Cultural](listas-de-valores.md#8-segmento-cultural). |
| **A entrega contempla quais medidas de acessibilidade?** <br> Medidas que visam garantir o acesso de pessoas com deficiência. | Detalhar as medidas de acessibilidade, para avaliar o cumprimento da legislação e o compromisso do projeto com a inclusão. | medidas_acessibilidade | Seleção múltipla a partir da [Lista 15. Medidas de Acessibilidade](listas-de-valores.md#15-medidas-de-acessibilidade). |
| **Qual o CEP do local em que a entrega foi realizada? (se aplicável)** <br> CEP do local onde a entrega presencial ocorreu. | Permitir a geolocalização das entregas para análise de distribuição territorial e alcance. | cep_local_entrega | CEP Válido (se aplicável) |
| **A entrega alcançou quantas pessoas?** <br> Número de beneficiários/público alcançado pela entrega. | Quantificar o alcance da entrega, fornecendo dados para a mensuração do impacto social do projeto. | publico_alcancado_entrega | Número Inteiro |
