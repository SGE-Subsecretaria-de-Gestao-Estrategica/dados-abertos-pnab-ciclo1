# Dados Abertos da Política Nacional Aldir Blanc (PNAB) - Ciclo I

Este repositório contém a base de dados consolidada e anonimizada dos agentes culturais contemplados no **Ciclo I da Política Nacional Aldir Blanc de Fomento à Cultura (PNAB)**. 

O objetivo deste projeto é fornecer transparência e subsidiar análises, reportagens e pesquisas sobre a distribuição territorial dos recursos e o perfil dos beneficiários da política cultural no Brasil.

> 📝 **Nota:** O conteúdo apresentado neste arquivo constitui uma **síntese da metodologia** de obtenção, tratamento e enriquecimento dos dados. A versão completa e detalhada está descrita nas publicações oficiais do Ministério da Cultura, especialmente na pesquisa **"RESULTADOS DO PRIMEIRO CICLO DA POLÍTICA NACIONAL ALDIR BLANC DE FOMENTO À CULTURA: recursos distribuídos, agentes contemplados e ações fomentadas"** (link disponível em breve).

---

## 📊 Conteúdo do Repositório

Os arquivos de dados e documentação estão organizados na pasta `dados/` e podem ser acessados diretamente pelos caminhos abaixo:

* **[`dados/agentes-contemplados-ciclo1`](dados/agentes-contemplados-ciclo1)**: Tabela contendo a listagem de 167.817 agentes culturais contemplados em 5.125 entes federativos (26 estados, Distrito Federal e 5.098 municípios), em diferentes formatos.
* **[`dados/dicionario_dados`](dados/dicionario-dados)**: Dicionário de dados detalhado, descrevendo cada variável contida na base de dados disponibilizada.

> 🔒 **Nota:** Em conformidade com a Lei Geral de Proteção de Dados (LGPD), todos os dados relativos a pessoas físicas beneficiárias foram **anonimizados**.

---

## 🔬 Obtenção e Tratamento dos Dados


A base de dados foi desenvolvida a partir de dados secundários das transações financeiras realizadas pelos entes que aderiram à PNAB. A pesquisa utilizou uma abordagem de *Data Warehouse* baseada em modelagem dimensional (esquema Estrela/*Star Schema*), onde as transações financeiras formam a tabela fato e os dados cadastrais/territoriais compõem as dimensões.

### 1. Extração e Tratamento
* **Fonte Principal:** Banco de dados do programa "BB Gestão Ágil", via API, fruto de Acordo de Cooperação Técnica entre o Banco do Brasil e o Ministério da Cultura (MinC).
* **Período de Coleta:** Movimentações realizadas até 31 de dezembro de 2025 (data-limite do Ciclo I). A extração final foi concluída em 24 de abril de 2026.
* **Critérios de exclusão:**  Considerou-se apenas registros com destinatário identificável (CPF ou CNPJ válido na Receita Federal) e de natureza de crédito. Estornos e duplicidades foram eliminados; Foram mantidas apenas transações de valor igual ou superior a R$ 375,00 (excluindo resíduos financeiros que não representavam execução finalística — menos de 1% da base) e beneficiários com idade igual ou superior a 16 anos.
* **Definição de "Contemplado":** O documento (CPF/CNPJ) que recebeu recursos de um determinado ente. Como um agente pode receber recursos de mais de um ente, ele pode aparecer replicado para entes diferentes (os dados estão agregados por documento e por ente). 

### 2. Enriquecimento dos Dados
A base de transações foi enriquecida via plataforma *Conecta Gov* e dados obtidos via Acordo de Cooperação Técnica (ACT), com cruzamentos de dados administrativos do Governo Federal:
* **Receita Federal do Brasil:** Dados cadastrais de CPF e CNPJ.
* **Cadastro Único (CadÚnico / MDS):** Indicadores familiares e socioeconômicos.
* **RAIS (MTE):** Informações sobre vínculos formais de trabalho, ocupação e escolaridade (recorte temporal de 2022 a 2024).
* **IBGE (SIDRA e CNEFE):** Qualificação da localização territorial e dados demográficos dos municípios.

*Nota metodológica: As bases possuem temporalidades distintas. Dados da Receita e CadÚnico refletem o estado mais recente (maio/2026), enquanto a RAIS cobre o período de 2022 a 2024. Essa assincronia deve ser considerada nas análises.*

---

## 💡 Como Utilizar estes Dados?

Esta base permite responder a perguntas como:
* Qual o volume de recursos da PNAB que chegou a municípios de pequeno porte?
* Qual o perfil socioeconômico majoritário dos agentes culturais contemplados?
* Como se distribuem os recursos entre proponentes Pessoa Física e Pessoa Jurídica nas diferentes regiões do país?

### ⚖️ Licença de Uso
Estes dados são públicos. Você é livre para compartilhar, analisar e utilizar os dados para qualquer finalidade (inclusive comercial), desde que **cite obrigatoriamente a fonte**.

**Como citar este repositório:**
> *Ministério da Cultura / Subsecretaria de Gestão Estratégica (SGE/MinC). Dados Abertos do Ciclo I da Política Nacional Aldir Blanc (PNAB) - Base Consolidada de Agentes Contemplados. Disponível em: [https://github.com/SGE-Subsecretaria-de-Gestao-Estrategica/dados-abertos-pnab-ciclo1](https://github.com/SGE-Subsecretaria-de-Gestao-Estrategica/dados-abertos-pnab-ciclo1). Acesso em: [Data de Acesso].*

---

## 🚀 Padronização de Dados 

Um dos desafios enfrentados na análise do Ciclo I foi a ausência de um preenchimento padronizado e a incompletude das categorias de despesas no ecossistema bancário, exigindo o uso de técnicas complexas de inferência estatística (como a pós-estratificação e o Bootstrap descritos na metodologia da pesquisa).

Para mitigar esse problema e aprimorar a governança da política pública, o **Ministério da Cultura (MInC) orienta, no âmbito do Sistema Nacional de Informações e Indicadores (SNIIC), que os entes federativos utilizem um [padrão de dados](https://github.com/SGE-Subsecretaria-de-Gestao-Estrategica/aldir-blanc-ciclo2) para o Ciclo II da PNAB**. A adoção de uma taxonomia e de campos obrigatórios harmonizados facilitará o monitoramento em tempo real, dispensará estimativas estatísticas secundárias e garantirá maior precisão na avaliação do impacto do fomento cultural no Brasil. Saiba mais [neste link](https://github.com/SGE-Subsecretaria-de-Gestao-Estrategica/aldir-blanc-ciclo2).
