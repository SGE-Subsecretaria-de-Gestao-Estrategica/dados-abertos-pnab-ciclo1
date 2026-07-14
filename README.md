# Dados Abertos da Política Nacional Aldir Blanc (PNAB) - Ciclo I

Este repositório contém a base de dados consolidada e anonimizada dos agentes culturais contemplados no **Ciclo I da Política Nacional Aldir Blanc de Fomento à Cultura (PNAB)**. Os dados integram o processo de reestruturação do **Sistema Nacional de Informações e Indicadores Culturais (SNIIC)** e fundamentaram a pesquisa **“Resultados do Primeiro Ciclo da Política Nacional Aldir Blanc de Fomento à Cultura: recursos distribuídos, agentes contemplados e ações fomentadas”**.

A divulgação em formato aberto assegura a transparência ativa, a reprodutibilidade das análises e a credibilidade dos resultados, permitindo que a sociedade debata a política pública com base em evidências.

---

## Sobre a pesquisa

O estudo analisa o primeiro ciclo da PNAB (Lei nº 14.399/2022), implementado entre 2023 e 2025, a partir de três eixos: **distribuição territorial dos recursos**, **perfil dos agentes culturais contemplados** e **ações fomentadas**. A base consolidada reúne **167.817 agentes** distribuídos por **5.125 entes federativos** (26 estados, o Distrito Federal e 5.098 municípios). Os dados têm origem nas transações financeiras registradas no BB Gestão Ágil e foram enriquecidos com informações da Receita Federal, CadÚnico, RAIS e IBGE.

---

## Transparência e Privacidade

Alinhada às [diretrizes de dados abertos](https://www.gov.br/governodigital/pt-br/dados-abertos) e à **Lei de Acesso à Informação (LAI)**, esta página garante o acesso público e irrestrito aos dados utilizados na avaliação dos resultados da política.

Em conformidade com a **Lei Geral de Proteção de Dados Pessoais (LGPD)**, a base de microdados passou por um processo de anonimização. Identificadores diretos (como nomes e documentos pessoais) foram suprimidos, assegurando que o escrutínio público seja seguro e focado na avaliação do impacto territorial e social dos recursos. A disponibilização dos dados — tanto nas visualizações interativas quanto para download em formato aberto — fomenta a participação cidadã e estimula a produção de pesquisas, reportagens e indicadores sobre o alcance da política cultural no Brasil.


---

##  Conteúdo do Repositório

A base de dados está organizada na pasta `dados/` e pode ser acessada nos seguintes formatos:

- **CSV particionado:** a base foi dividida em 6 arquivos CSV (devido ao limite de tamanho do GitHub), disponíveis em [`dados/agentes-contemplados-ciclo1/`](dados/agentes-contemplados-ciclo1).
- **Parquet (versão completa):** arquivo único em formato colunar, ideal para análises mais pesadas, também disponível na mesma pasta.
- **Dicionário de dados:** documentação detalhada de cada variável está em [`dados/dicionario_dados`](dados/dicionario_dados).

>  **Nota:** Em conformidade com a LGPD, todos os dados relativos a pessoas físicas foram anonimizados. Variáveis que poderiam permitir a identificação direta foram suprimidas ou agrupadas.

---

## Obtenção e Tratamento dos Dados

A metodologia foi estruturada em etapas complementares, organizadas a partir dos três eixos analíticos da pesquisa: distribuição territorial dos recursos, perfil dos agentes culturais contemplados e ações culturais fomentadas. A extração, a validação e o tratamento dos dados deram suporte à análise territorial, enquanto o enriquecimento da base permitiu caracterizar os perfis. Para a análise das ações, foi necessário categorizar as despesas, como detalhado a seguir.

### 1. Extração, validação e tratamento dos dados
- **Fonte principal:** BB Gestão Ágil, acessado via API no âmbito de Acordo de Cooperação Técnica entre o Banco do Brasil e o Ministério da Cultura.
- **Período:** movimentações até 31 de dezembro de 2025 (data-limite do Ciclo I), incluindo extratos e subtransações. Extração concluída em 24 de abril de 2026.
- **Critérios de inclusão:** apenas registros com destinatário identificável (CPF ou CNPJ) e natureza de crédito. Estornos, duplicidades e transações residuais foram removidos.
- **Filtros aplicados:** valor igual ou superior a R$ 375,00; idade do beneficiário igual ou superior a 16 anos; documentos com situação válida na Receita Federal.
- **Validação:** comparação dos valores movimentados com os saldos das contas dos entes, obtendo diferenças residuais (mediana inferior a 1%).
- **Definição de contemplado:** documento (CPF ou CNPJ) que recebeu recurso de um ente federativo. Um mesmo agente pode constar mais de uma vez na base caso tenha recebido de entes diferentes.

### 2. Enriquecimento dos dados
O enriquecimento foi feito por meio de cruzamentos com bases administrativas acessadas via Conecta Gov e acordos de cooperação:

- **Receita Federal:** qualificação cadastral de pessoas físicas e jurídicas.
- **CadÚnico (MDS):** indicadores socioeconômicos e faixas de renda.
- **RAIS (MTE/INSS):** vínculos formais de trabalho, ocupação e escolaridade (recorte 2022–2024).
- **IBGE (SIDRA e CNEFE):** dados territoriais, tipologia urbana e localização.

*Nota: As bases têm temporalidades distintas. Dados da Receita Federal e do CadÚnico refletem a informação mais recente disponível no momento da extração (maio/2026). A RAIS é anual, abrangendo 2022 a 2024. Essas diferenças devem ser consideradas na interpretação das variáveis.*

O resultado do processo é uma **única tabela enriquecida**, que consolida todas as variáveis disponíveis para os agentes contemplados. O detalhamento completo de cada variável (nome, descrição, tipo e fonte) está no **Dicionário de Dados** (link acima).

### 3. Categorização das despesas (análise das ações culturais)
Para a análise das ações culturais fomentadas, foi necessário categorizar as despesas registradas no BB Gestão Ágil. Diante do preenchimento parcial dos campos, adotou-se uma combinação de harmonização dos registros (alinhamento a domínios culturais) e inferência estatística. A estimação foi aplicada apenas aos municípios, utilizando pós-estratificação e calibração de pesos, com porte populacional, região geográfica e natureza jurídica (PF/PJ) como variáveis estruturantes. A variabilidade das estimativas foi obtida por meio do método Bootstrap, permitindo a construção de intervalos de confiança de 95%.

**Importante:** essa etapa foi utilizada exclusivamente no estudo das ações culturais e **não interfere nos dados de agentes disponibilizados neste repositório**. Os microdados referem-se à tabela enriquecida de contemplados, sem qualquer modificação decorrente da categorização de despesas.

---

## Como citar

Estes dados são **públicos e abertos**. Você pode compartilhar, analisar, cruzar e utilizar os dados para qualquer finalidade acadêmica, jornalística ou cidadã, desde que a fonte seja obrigatoriamente citada.

**Formato sugerido para citação:**

> *Ministério da Cultura / Subsecretaria de Gestão Estratégica (SGE/MinC). Dados Abertos do Ciclo I da Política Nacional Aldir Blanc (PNAB) - Base Consolidada de Agentes Contemplados. Disponível no Sistema Nacional de Informações e Indicadores Culturais (SNIIC) e em: [https://github.com/SGE-Subsecretaria-de-Gestao-Estrategica/dados-abertos-pnab-ciclo1](https://github.com/SGE-Subsecretaria-de-Gestao-Estrategica/dados-abertos-pnab-ciclo1). Acesso em: [sua data].*

---

## Perspectivas para o Ciclo II da PNAB

Um dos desafios enfrentados na análise do Ciclo I foi a ausência de preenchimento padronizado e a incompletude das categorias de despesas no sistema BB Ágil, o que exigiu o uso de técnicas de inferência estatística — como pós‑estratificação e Bootstrap descritos na metodologia da pesquisa.

Para mitigar esse problema e aprimorar a governança da política, o **Ministério da Cultura (MinC)** orienta, no âmbito do **Sistema Nacional de Informações e Indicadores Culturais (SNIIC)**, que os entes federativos utilizem um [padrão de dados para o Ciclo II da PNAB](https://github.com/SGE-Subsecretaria-de-Gestao-Estrategica/aldir-blanc-ciclo2). A adoção de uma taxonomia e de campos obrigatórios harmonizados permitirá o monitoramento em tempo real, dispensará estimativas estatísticas secundárias e garantirá maior precisão na avaliação do impacto do fomento cultural no Brasil. Saiba mais [neste link](https://github.com/SGE-Subsecretaria-de-Gestao-Estrategica/aldir-blanc-ciclo2).
