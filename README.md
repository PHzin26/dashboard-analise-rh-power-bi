# 📊 Análise de Dados de RH com Power BI

<p align="center"> <img src="imagens/Dashboard-RH-Imagem.png" alt="Dashboard de Análise de Recursos Humanos" width="100%"> </p> 

## 📌 Sobre o Projeto

Este projeto consiste no desenvolvimento de um **Dashboard de Recursos Humanos utilizando Microsoft Power BI**, com o objetivo de transformar dados de funcionários em informações relevantes para análise e tomada de decisões.

Em uma organização, a área de Recursos Humanos trabalha com uma grande quantidade de informações relacionadas aos colaboradores, como experiência profissional, remuneração, gênero, função, envolvimento com o trabalho e disponibilidade para realização de horas extras.

A utilização de ferramentas de **Business Intelligence (BI)** permite transformar esses dados em indicadores e visualizações que facilitam a identificação de padrões e apoiam a gestão de pessoas.

Neste projeto, foi desenvolvido um dashboard interativo para analisar o quadro de funcionários de uma empresa fictícia, permitindo uma visão geral dos principais indicadores de RH.

---

## 🎯 Objetivo

O principal objetivo do projeto é desenvolver um dashboard capaz de responder às principais questões de negócio relacionadas aos funcionários da empresa.

A solução utiliza **Power BI, DAX e Power Query** para realizar o tratamento dos dados, criação de medidas e construção das visualizações.

Além da apresentação visual dos indicadores, o projeto também busca demonstrar a aplicação prática de conceitos de **Análise de Dados e Business Intelligence**.

---

## ❓ Questões de Negócio

O dashboard foi desenvolvido para responder às seguintes questões:

### 1. Qual o total de funcionários atualmente na empresa?

Identificar o tamanho atual do quadro de funcionários da empresa.

### 2. Qual o tempo médio de experiência dos funcionários (em anos)?

Calcular a experiência média dos colaboradores para obter uma visão geral da experiência profissional presente na organização.

### 3. Qual o total e percentual de funcionários do gênero masculino e feminino?

Analisar a distribuição dos funcionários por gênero, considerando tanto a quantidade absoluta quanto o percentual em relação ao total da empresa.

### 4. Qual a média salarial mensal?

Calcular o salário médio mensal dos funcionários da empresa.

### 5. Qual o total de funcionários por função?

Analisar como os funcionários estão distribuídos entre as diferentes funções existentes na organização.

### 6. Qual o percentual de funcionários disponíveis para fazer hora extra?

Identificar a proporção de funcionários que estão disponíveis para realizar horas extras.

### 7. Qual o nível de envolvimento dos funcionários no trabalho?

Analisar o nível de envolvimento dos funcionários considerando quatro categorias:

- Ruim
- Baixo
- Médio
- Alto

### 8. Qual o total e o percentual de funcionários que devem receber promoção?

Este indicador **não deve ser apresentado no Dashboard**, mas precisa ser calculado separadamente.

Para essa análise, são considerados os funcionários que possuem **5 anos ou mais desde a última promoção**.

---

## 📊 Principais Indicadores

O dashboard apresenta os seguintes indicadores:

| Indicador | Resultado |
|---|---:|
| Total de Funcionários | 1.400 |
| Funcionários Masculinos | 838 |
| Funcionários Femininos | 562 |
| Percentual Masculino | 59,86% |
| Percentual Feminino | 40,14% |
| Experiência Média | 11 anos |
| Salário Médio | R$ 6.927,51 |
| Disponíveis para Hora Extra | 28,43% |

Além dos indicadores apresentados em cartões, o dashboard também permite visualizar:

- Total de funcionários por função;
- Nível de envolvimento no trabalho;
- Distribuição de funcionários disponíveis para hora extra;
- Análise por faixa etária através de segmentação.

---

## 🧮 Principais Medidas DAX

Durante o desenvolvimento foram criadas medidas utilizando DAX para gerar os principais indicadores do dashboard.

### Total de Funcionários

```DAX
TotalFunc =
COUNTROWS(DatasetRH)
```

A função `COUNTROWS` é utilizada para contar o número de registros existentes na tabela `DatasetRH`.

### Total de Funcionários Masculinos

```DAX
TotalMasculino =
CALCULATE(
    [TotalFunc],
    DatasetRH[Genero] = "Masculino"
)
```

A função `CALCULATE` modifica o contexto de filtro para considerar somente os funcionários cujo gênero é "Masculino".

### Percentual Masculino

```DAX
% Masculino =
DIVIDE(
    [TotalMasculino],
    [TotalFunc],
    0
)
```

A função `DIVIDE` é utilizada para calcular a proporção de funcionários masculinos em relação ao total de funcionários.

**Resultado:** 59,86%

### Total de Funcionários Femininos

A mesma lógica utilizada para os funcionários masculinos é aplicada para o gênero feminino:

```DAX
TotalFeminino =
CALCULATE(
    [TotalFunc],
    DatasetRH[Genero] = "Feminino"
)
```

**Resultado:** 562 funcionários

### Percentual Feminino

```DAX
% Feminino =
DIVIDE(
    [TotalFeminino],
    [TotalFunc],
    0
)
```

**Resultado:** 40,14%

### Experiência Média

A experiência média dos funcionários é calculada utilizando uma agregação de média sobre a coluna referente aos anos de experiência.

Esse indicador permite obter uma visão geral do nível de experiência presente no quadro de colaboradores.

**Resultado:** 11 anos

### Salário Médio

O salário médio mensal é obtido através da média dos salários dos funcionários.

**Resultado:** R$ 6.927,51

### Percentual de Funcionários Disponíveis para Hora Extra

O indicador considera os funcionários classificados como disponíveis para realização de hora extra e calcula sua participação sobre o total de funcionários.

**Resultado:** 28,43%

### Nível de Envolvimento no Trabalho

Os funcionários são distribuídos em quatro categorias de envolvimento:

- Ruim
- Baixo
- Médio
- Alto

Essa distribuição é apresentada no dashboard através de um gráfico de rosca, facilitando a comparação entre os níveis.

### Funcionários Elegíveis para Promoção

Esse cálculo foi realizado separadamente e não foi incluído no dashboard, conforme a especificação do projeto.

A regra considera como elegíveis para promoção os funcionários que possuem **5 anos ou mais desde a última promoção**.

O cálculo permite identificar tanto:

- Total de funcionários elegíveis;
- Percentual de funcionários elegíveis em relação ao total.

---

## 🛠️ Tecnologias e Ferramentas

- Microsoft Power BI
- DAX
- Power Query
- Excel / CSV
- GitHub

---

## 📐 Técnicas e Conceitos Aplicados

Durante o desenvolvimento do projeto foram aplicados conceitos de:

- Business Intelligence;
- Análise exploratória de dados;
- Tratamento e transformação de dados;
- Power Query;
- Modelagem de dados;
- Criação de medidas DAX;
- Contexto de filtro;
- COUNTROWS;
- CALCULATE;
- DIVIDE;
- Funções de agregação;
- Cálculos percentuais;
- Criação de indicadores;
- Segmentação de dados;
- Visualização de dados;
- Construção de dashboards interativos.

---

## 📈 Visualizações

O dashboard utiliza diferentes elementos visuais para apresentar os indicadores de forma clara e objetiva.

### Cards / KPIs

Utilizados para apresentar:

- Total de funcionários;
- Total masculino;
- Total feminino;
- Percentual masculino;
- Percentual feminino;
- Salário médio;
- Experiência média.

### Gráfico de Barras

Utilizado para apresentar o total de funcionários por função, facilitando a identificação das funções com maior concentração de colaboradores.

### Gráfico de Rosca

Utilizado para apresentar:

- Nível de envolvimento dos funcionários;
- Disponibilidade para realização de hora extra.

### Segmentação de Dados

Foi utilizada uma segmentação de dados por idade, permitindo analisar os indicadores de acordo com diferentes faixas etárias.

---

## 🔎 Principais Insights

A análise realizada através do dashboard permite observar alguns pontos relevantes:

- A empresa possui **1.400 funcionários**;
- O quadro de funcionários é composto por **838 homens** e **562 mulheres**;
- O gênero masculino representa **59,86%** dos funcionários;
- O gênero feminino representa **40,14%**;
- A experiência média dos funcionários é de aproximadamente **11 anos**;
- O salário médio mensal é de **R$ 6.927,51**;
- A função de **Cientista de Dados** possui a maior quantidade de funcionários entre as funções apresentadas;
- **28,43%** dos funcionários estão disponíveis para realizar hora extra;
- O nível de envolvimento dos funcionários pode ser analisado através das categorias Ruim, Baixo, Médio e Alto.

---

## 📚 Referência

Projeto desenvolvido com base no **Mini-Projeto 3 — Análise de Dados de Recursos Humanos**, apresentado no capítulo correspondente do curso:

**Microsoft Power BI para Business Intelligence e Data Science**

da **Data Science Academy (DSA)**.

O projeto possui finalidade educacional e utiliza uma base de dados fictícia para aplicação prática dos conceitos apresentados no curso.

A proposta envolve a análise de indicadores relacionados ao quadro de funcionários, experiência, gênero, remuneração, funções, horas extras, envolvimento e promoções.

---

## 📁 Estrutura do Projeto

```text
dashboard-analise-rh-power-bi/
│
├── README.md
│
├── Dashboard_Analise_RH.pbix
│
└── imagens/
    └── papel-de-parede-painel-rh.svg
    └── Dashboard-RH-Imagem.png
```

---

## 👨‍💻 Autor

**Pedro Campos**

Estudante de Ciência da Computação, com interesse em:

- 📊 Análise de Dados
- 📈 Business Intelligence
- 🗄️ SQL
- 📊 Power BI
- 📐 DAX
- 📉 Visualização de Dados

---

## 📌 Versão

**Versão 1.0**

Projeto desenvolvido para fins educacionais e de portfólio.
