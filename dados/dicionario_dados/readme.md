# 📖 Dicionário de Dados: PNAB - Ciclo I

Este documento descreve detalhadamente as variáveis presentes na base de dados consolidada dos agentes culturais contemplados na **Política Nacional Aldir Blanc de Fomento à Cultura (PNAB) - Ciclo I**. As informações foram enriquecidas e estruturadas a partir de diversas bases governamentais. Consulte também a [página principal do repositório](https://github.com/SGE-Subsecretaria-de-Gestao-Estrategica/dados-abertos-pnab-ciclo1/blob/main/README.md) para informações sobre a metodologia e o contexto da pesquisa.


---

### Banco do Brasil (BB Gestão Ágil)
*Dados originais das transações financeiras e identificação dos beneficiários e entes pagadores.*

| Variável | Descrição |
| :--- | :--- |
| `uf_bbagil` | Unidade da Federação do ente pagador. |
| `cod_ibge_bbagil` | Código IBGE do ente pagador. |
| `nome_ente_bbagil` | Nome do ente pagador. |
| `documento_beneficiario_bbagil` | CPF anonimizado ou CNPJ do beneficiário do pagamento. |
| `tipo_ente_bbagil` | Tipo do ente pagador (Estado ou Município). |
| `tipo_documento_bbagil` | Tipo do documento do beneficiário (CPF ou CNPJ). |
| `valor_transacao_total_bbagil` | Valor total recebido pelo beneficiário (em reais). |
| `faixa_vlr_pago_bbagil` | Faixa de valor total recebido. |

---

### Receita Federal do Brasil
*Dados cadastrais de Pessoas Físicas (CPF) e Pessoas Jurídicas (CNPJ).*

#### Pessoa Física (CPF)

| Variável | Descrição |
| :--- | :--- |
| `residenteexterior_receita_cpf` | Indica se a pessoa física é residente no exterior. |
| `sexo_receita_cpf` | Sexo cadastrado da pessoa física. |
| `estrangeiro_receita_cpf` | Indica se a pessoa física é estrangeira. |
| `nomenaturezaocupacao_receita_cpf` | Natureza da ocupação cadastrada da pessoa física. |
| `nomeocupacaoprincipal_receita_cpf` | Ocupação principal cadastrada da pessoa física. |
| `idade_receita_cpf` | Idade da pessoa física. |
| `faixa_etaria_receita_cpf` | Faixa etária da pessoa física. |
| `codigomunicipio_receita_cpf` | Código IBGE do município de residência da pessoa física. |
| `flag_cpf_mei_receita_cpf` | Indica se o CPF está associado a um Microempreendedor Individual (MEI). |

#### Pessoa Jurídica (CNPJ)

| Variável | Descrição |
| :--- | :--- |
| `cnaeprincipal_receita_cnpj` | Descrição do CNAE principal da empresa. |
| `cnaesecundarias_receita_cnpj` | Lista dos CNAEs secundários da empresa. |
| `naturezajuridica_receita_cnpj` | Natureza jurídica da empresa. |
| `porte_receita_cnpj` | Porte da empresa. |
| `cnpj_optante_mei_receita_cnpj` | Indica se o CNPJ é optante pelo MEI. |
| `flag_cnae_cultural_receita_cnpj` | Indica se o CNAE principal pertence ao setor cultural. |
| `codigo_municipio_receita_cnpj` | Código IBGE do município da empresa. |
| `cod_cnae_principal_receita_cnpj` | Código do CNAE principal. |
| `descr_cnae_principal_receita_cnpj` | Descrição do CNAE principal. |
| `naturezajuridica_agrupada_receita_cnpj` | Agrupamento simplificado da natureza jurídica. |
| `flag_cnae_educacao_receita_cnpj` | Indica se o CNAE principal pertence ao setor de educação. |
| `flag_cnae_audiovisual_receita_cnpj` | Indica se o CNAE principal pertence ao setor audiovisual. |

---

### RAIS e Relações Trabalhistas (MTE / INSS)
*Dados de vínculos formais de emprego, ocupações e perfil do trabalhador.*

| Variável | Descrição |
| :--- | :--- |
| `raca_cor_desc_description_rais` | Raça/cor do trabalhador. |
| `escolaridade_description_rais` | Escolaridade detalhada. |
| `escolaridade_agregado_rais` | Escolaridade agrupada. |
| `tipo_deficiencia_description_rais` | Tipo de deficiência do trabalhador. |
| `indicador_pcd_rais` | Indica se o trabalhador possui deficiência (0 = não; 1 = sim). |
| `tipo_vinculo_description_rais` | Tipo de vínculo empregatício. |
| `tipo_vinculo_agregado_rais` | Agrupamento do tipo de vínculo empregatício. |
| `cbo_2002_ocupacao_codigo_rais` | Código CBO da ocupação. |
| `vinculo_ativo_2024_rais` | Indica se havia vínculo ativo em 2024 na RAIS. |
| `flag_cbo_cultural_rais` | Indica se a ocupação pertence ao setor cultural. |
| `faixa_salarial_rais` | Faixa salarial do trabalhador. |
| `cbo_codigo_rel_trabalhista_inss` | Código CBO do vínculo registrado no INSS. |
| `cbo_descricao_rel_trabalhista_inss` | Descrição da ocupação do vínculo registrado no INSS. |
| `flag_cbo_cultural_rel_trabalhista_inss` | Indica se a ocupação registrada no INSS pertence ao setor cultural. |

---

###  Cadastro Único (CadÚnico / MDS)
*Dados socioeconômicos e de participação em programas sociais.*

| Variável | Descrição |
| :--- | :--- |
| `pessoacadastrada_cadunico` | Indica se a pessoa está cadastrada no CadÚnico. |
| `familiabeneficiariapbf_cadunico` | Indica se pertence a família beneficiária do Programa Bolsa Família. |
| `faixarendafamiliartotal_descricao_cadunico` | Faixa da renda familiar total. |
| `caracteristicaslocaldomicilio_descricao_cadunico` | Característica do local do domicílio. |
| `faixarendafamiliarpercapita_descricao_cadunico` | Faixa da renda familiar per capita. |
| `situacao_renda_cadunico` | Classificação da situação de renda familiar. |
| `pertence_bpc` | Indica se a pessoa pertence ao público do Benefício de Prestação Continuada (BPC). |

---

###  IBGE (CNEFE e Bases Territoriais)
*Características geográficas, tipologia urbana e porte populacional.*

| Variável | Descrição |
| :--- | :--- |
| `situacao_cnfe` | Classificação da localização do domicílio no CNEFE (urbana/rural). |
| `cod_situacao_nome_cnefe` | Descrição da situação do domicílio. |
| `cod_tipo_nome_cnefe` | Tipo de aglomerado/subnormalidade do domicílio. |
| `populacao_ibge` | População do ente federativo. |
| `flag_capital_ibge` | Indica se o município é capital estadual (True/False). |
| `porte_populacional_ibge` | Classificação do porte populacional do município ("-99" para entes estaduais). |
| `nome_macrorregiao_ibge` | Macrorregião do Brasil à qual pertence o ente. |
| `categoria_municipio_ibge` | Categoria do município (capital, metropolitano, interior etc.). |
| `local_residencia_contemplados_ibge` | Classificação do local de residência do contemplado segundo a tipologia do município. |

---

*Nota: Todas as variáveis que poderiam permitir a identificação direta de pessoas físicas foram anonimizadas ou agrupadas, em conformidade com a LGPD.*
