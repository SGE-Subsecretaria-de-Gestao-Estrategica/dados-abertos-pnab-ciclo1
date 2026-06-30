# 📖 Dicionário de Dados: PNAB - Ciclo I

Este documento descreve detalhadamente as variáveis presentes na base de dados consolidada dos agentes culturais contemplados na **Política Nacional Aldir Blanc de Fomento à Cultura (PNAB) - Ciclo I**. 

As informações foram enriquecidas e estruturadas a partir de diversas bases governamentais. Abaixo, as variáveis estão agrupadas por suas respectivas fontes [saiba mais neste link](https://github.com/SGE-Subsecretaria-de-Gestao-Estrategica/dados-abertos-pnab-ciclo1/blob/main/README.md).

---

### 🏦 Banco do Brasil (BB Gestão Ágil)
*Dados originais referentes às transações financeiras e à identificação dos beneficiários e entes pagadores.*

| Variável | Descrição |
| :--- | :--- |
| `ente_bbagil` | Identificador do ente responsável pelo pagamento. |
| `documento_beneficiario_bbagil` | CPF anonimizado ou CNPJ do beneficiário do pagamento. |
| `tipo_ente_bbagil` | Tipo do ente pagador (Estado ou Município). |
| `tipo_documento_bbagil` | Tipo do documento do beneficiário (CPF ou CNPJ). |
| `valor_transacao_total_bbagil` | Valor total recebido pelo beneficiário. |
| `faixa_vlr_pago_ju_bbagil` | Faixa de valor total recebido. |
| `uf_bbagil` | Unidade da Federação do ente pagador. |
| `cod_ibge_bbagil` | Código IBGE do ente pagador. |
| `nome_ente_bbagil` | Nome do ente pagador. |

---

### 🏢 Receita Federal do Brasil
*Dados cadastrais para caracterização de Pessoas Físicas (CPF) e Pessoas Jurídicas (CNPJ).*

| Variável | Descrição | Base Específica |
| :--- | :--- | :--- |
| `residenteexterior_receita_cpf` | Indica se a pessoa física é residente no exterior. | CPF |
| `sexo_receita_cpf` | Sexo cadastrado da pessoa física. | CPF |
| `estrangeiro_receita_cpf` | Indica se a pessoa física é estrangeira. | CPF |
| `nomenaturezaocupacao_receita_cpf` | Natureza da ocupação cadastrada da pessoa física. | CPF |
| `nomeocupacaoprincipal_receita_cpf` | Ocupação principal cadastrada da pessoa física. | CPF |
| `idade_receita_cpf` | Idade da pessoa física. | CPF |
| `faixa_etaria_receita_cpf` | Faixa etária da pessoa física. | CPF |
| `codigomunicipio_receita_cpf` | Código IBGE do município de residência da pessoa física. | CPF |
| `flag_cpf_mei_receita_cpf` | Indica se o CPF está associado a um Microempreendedor Individual (MEI). | CPF/CNPJ |
| `cnaeprincipal_receita_cnpj` | Descrição do CNAE principal da empresa. | CNPJ |
| `cnaesecundarias_receita_cnpj` | Lista dos CNAEs secundários da empresa. | CNPJ |
| `naturezajuridica_receita_cnpj` | Natureza jurídica da empresa. | CNPJ |
| `porte_receita_cnpj` | Porte da empresa. | CNPJ |
| `cnpj_optante_mei_receita_cnpj` | Indica se o CNPJ é optante pelo MEI. | CNPJ |
| `flag_cnae_cultural_receita_cnpj` | Indica se o CNAE principal pertence ao setor cultural. | CNPJ |
| `codigo_municipio_receita_cnpj` | Código IBGE do município da empresa. | CNPJ |
| `cod_cnae_principal_receita_cnpj` | Código do CNAE principal. | CNPJ |
| `descr_cnae_principal_receita_cnpj` | Descrição do CNAE principal. | CNPJ |
| `naturezajuridica_agrupada_receita_cnpj` | Agrupamento simplificado da natureza jurídica. | CNPJ |
| `flag_cnae_educacao_receita_cnpj` | Indica se o CNAE principal pertence ao setor de educação. | CNPJ |
| `flag_cnae_audiovisual_receita_cnpj` | Indica se o CNAE principal pertence ao setor audiovisual. | CNPJ |

---

### 💼 RAIS e Relações Trabalhistas (MTE / INSS)
*Dados sobre vínculos formais de emprego, ocupações e informações demográficas do trabalhador.*

| Variável | Descrição | Fonte |
| :--- | :--- | :--- |
| `raca_cor_desc_description_rais` | Raça/cor do trabalhador. | RAIS |
| `escolaridade_description_rais` | Escolaridade detalhada. | RAIS |
| `escolaridade_agregado_rais` | Escolaridade agrupada. | RAIS |
| `tipo_deficiencia_description_rais` | Tipo de deficiência do trabalhador. | RAIS |
| `indicador_pcd_rais` | Flag que indica se o trabalhador possui deficiência (0 = não; 1 = sim). | RAIS |
| `tipo_vinculo_description_rais` | Tipo de vínculo empregatício. | RAIS |
| `tipo_vinculo_agregado_rais` | Agrupamento do tipo de vínculo empregatício. | RAIS |
| `cbo_2002_ocupacao_codigo_rais` | Código CBO da ocupação. | RAIS |
| `vinculo_ativo_2024_rais` | Indica se havia vínculo ativo em 2024 na RAIS. | RAIS |
| `flag_cbo_cultural_rais` | Indica se a ocupação pertence ao setor cultural. | RAIS |
| `faixa_salarial_rais` | Faixa salarial do trabalhador. | RAIS |
| `cbo_codigo_rel_trabalhista_inss` | Código CBO do vínculo registrado no INSS. | INSS |
| `cbo_descricao_rel_trabalhista_inss` | Descrição da ocupação do vínculo registrado no INSS. | INSS |
| `flag_cbo_cultural_rel_trabalhista_inss` | Indica se a ocupação registrada no INSS pertence ao setor cultural. | INSS |

---

### 👨‍👩‍👧‍👦 Cadastro Único (CadÚnico / MDS)

| Variável | Descrição |
| :--- | :--- |
| `pessoacadastrada_cadunico` | Indica se a pessoa está cadastrada no CadÚnico. |
| `familiabeneficiariapbf_cadunico` | Indica se pertence a família beneficiária do Programa Bolsa Família. |
| `faixarendafamiliartotal_descricao_cadunico` | Faixa da renda familiar total. |
| `caracteristicaslocaldomicilio_descricao_cadunico` | Característica do local do domicílio. |
| `faixarendafamiliarpercapita_descricao_cadunico` | Faixa da renda familiar per capita. |
| `situacao_renda_cadunico` | Classificação da situação de renda familiar. |
| `pertence_bpc` | Indica se a pessoa pertence ao público beneficiário do BPC (Benefício de Prestação Continuada). |

---

### 🗺️ IBGE (CNEFE e Bases Territoriais)
*Dados sobre as características geográficas, tipologia urbana e porte populacional.*

| Variável | Descrição | Base Específica |
| :--- | :--- | :--- |
| `situacao_cnfe` | Classificação da localização do domicílio no CNEFE (urbana/rural). | CNEFE |
| `cod_situacao_nome_cnefe` | Descrição da situação do domicílio. | CNEFE |
| `cod_tipo_nome_cnefe` | Tipo de aglomerado/subnormalidade do domicílio. | CNEFE |
| `populacao_ibge` | População do ente. | IBGE |
| `flag_capital_ibge` | Indica se o município é capital estadual. | IBGE |
| `porte_populacional_ibge` | Classificação do porte populacional do município ("-99" para entes estaduais). | IBGE |
| `nome_macrorregiao_ibge` | Macrorregião do Brasil à qual pertence o ente. | IBGE |
| `categoria_municipio_ibge` | Categoria do município (capital, metropolitano, interior etc.). | IBGE |
| `local_residencia_contemplados_ibge` | Classificação do local de residência do contemplado segundo a tipologia do município. | IBGE |
