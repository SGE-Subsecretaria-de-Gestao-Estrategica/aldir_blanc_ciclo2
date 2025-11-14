[< Voltar ao Guia de Adoção](guia-adesao.md) | [Ir para o Padrão SNIIC (README)](README.md)

# Guia de Adoção - Cenário 3: Implementação Simplificada (Planilhas/Formulários)

Este guia detalha o plano de ação para Entes Federativos que **não possuem um sistema dedicado** e optarão por coletar os dados usando ferramentas como Planilhas (Excel, Google Sheets) ou Formulários Online (Google Forms, Microsoft Forms).

### Perfil do Ente
Este cenário é a realidade da grande maioria dos municípios brasileiros. Se você não possui uma equipe de TI dedicada ou um sistema de gestão de editais, este é o seu guia.

### Vantagens e Desafios
* **Vantagens:**
    * Implementação mais rápida e flexível.
    * Custo zero de software (utiliza ferramentas que você provavelmente já tem).
    * Não exige conhecimento técnico em banco de dados ou programação.
* **Desafios / Pontos de Atenção:**
    * **O Risco Crítico: O Erro de Digitação.** Este é o maior desafio deste cenário. Para que os dados do Brasil inteiro possam ser somados, eles precisam ser idênticos. Se um proponente escreve "Audiovisual", outro "Audio Visual" e um terceiro "Audiovisuais", teremos três categorias diferentes em vez de uma.
    * **Solução:** O uso de **Validação de Dados** (listas suspensas) é **obrigatório** para evitar este problema.

---

### O Caminho Recomendado: Usar Formulários Online (Google Forms, etc.)

Esta é a abordagem **mais recomendada** para este cenário. Ela resolve o "Risco Crítico" (erro de digitação) de forma simples e gratuita.

**Por quê?** Um formulário online permite que você crie perguntas de "Lista Suspensa" (dropdown) ou "Múltipla Escolha". O proponente é forçado a selecionar um valor da lista oficial, garantindo que o dado chegue 100% correto na sua planilha de respostas.


**Plano de Ação (Formulários Online):**

1.  **Aguarde ou Use os Modelos:** A forma mais fácil será utilizar os modelos que o MinC irá disponibilizar.
    * _Um link para um Modelo de Google Forms pré-configurado, espelhando os dicionários, será disponibilizado em breve._
2.  **Se for criar o seu:**
    * Crie um conjunto de formulários (ex: Google Forms) para as Fases 1 e 2.
    * Para cada atributo do dicionário (ex: `Nome completo`), crie uma pergunta.
    * **(Obrigatório)** Para cada atributo que usa uma lista (ex: `segmento_cultural_principal`), crie uma pergunta do tipo "Lista Suspensa" e **copie/cole os valores exatos** do arquivo [`listas-de-valores.md`](listas-de-valores.md).
3.  **Use Validação de Dados:** Nos campos de texto (como CPF ou E-mail), use as regras de validação nativas do formulário para garantir que o formato esteja correto (ex: "deve ser um e-mail válido").
4.  **Coleta:** Envie o link do formulário para os proponentes no seu edital. As respostas serão salvas automaticamente em uma planilha (ex: Google Sheets).
5.  **Ajuste Final:** Após a coleta, você terá uma planilha de respostas (ex: Google Sheets). Seu único trabalho técnico será:
    * Abrir a planilha.
    * Renomear os cabeçalhos das colunas (que hoje são as "perguntas", ex: "Qual seu nome completo?") para que correspondam *exatamente* aos `Nomes formatados` dos dicionários (ex: `nome_completo`).
    * Exportar este arquivo final (em .CSV ou .XLSX) para o envio ao MinC.

### O Caminho Alternativo: Usar Planilhas Diretamente (Excel, Google Sheets)

Este caminho é possível, mas **mais arriscado** se a planilha for enviada aberta para o proponente preencher, pois ele pode cometer erros de digitação.

Esta abordagem funciona melhor se a **própria equipe de gestão do ente** preencher a planilha (centralizando a digitação) ou se a planilha for muito bem configurada com validação de dados.

**Plano de Ação (Planilhas Diretas):**

1.  **Aguarde ou Use os Modelos:** O MinC irá disponibilizar planilhas-modelo já configuradas.
    * _Um arquivo .xlsx (Excel) com as colunas, validações de dados e listas suspensas pré-configuradas será disponibilizado em breve._
2.  **Se for criar a sua:**
    * Crie um arquivo (Excel ou Google Sheets) para cada entidade (Agente Individual, Proposta de Ação, etc.).
    * **(Obrigatório - Regra 1)** Os cabeçalhos das colunas (linha 1) da sua planilha DEVEM ser os `Nomes formatados` (ex: `cpf`, `nome_completo`, `data_nascimento`).
    * **(Obrigatório - Regra 2)** Em todas as colunas que usam listas (ex: `segmento_cultural_principal`), use a ferramenta "Validação de Dados" para criar uma lista suspensa. Isso força o preenchimento correto.
3.  **Consolidação:** O gestor do ente ficará responsável por garantir que todas as linhas estão preenchidas corretamente, sem erros de digitação, e que as informações estão rastreáveis (ex: que o CPF do agente está correto na planilha de propostas).

### Modelos e Exemplos (Disponibilizados em Breve)
* _Link para um Modelo de Google Forms pré-configurado (Fase 1 e Fase 2)._
* _Arquivo .xlsx (Excel) com as colunas, validações de dados e listas suspensas pré-configuradas._
* _Tutorial em vídeo: "Como usar Validação de Dados no Excel/Google Sheets para as Listas da PNAB"._
