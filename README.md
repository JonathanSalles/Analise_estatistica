# Desafio: Análise Estatística de Salários em Dados
https://dncgroupbr.notion.site/Desafio-An-lise-Estat-stica-de-Sal-rios-em-Dados-1c81b4d4252c8012a3d6e965d7a524ea
## 🎯 Sobre o Projeto

Este projeto tem como objetivo aplicar técnicas de estatística descritiva em um conjunto de dados contendo informações sobre profissionais da área de dados ao redor do mundo. A ideia é utilizar ferramentas de análise exploratória e visualização para entender como diferentes fatores impactam o salário desses profissionais.

### **Contexto**

Você foi contratado para apoiar uma equipe de RH especializada em tecnologia e ciência de dados. Essa equipe recebeu uma base de dados com informações salariais de profissionais ao redor do mundo e quer entender como variáveis como cargo, país, nível de experiência e ano influenciam os salários.

### **Sua Missão**

Sua missão é organizar e explorar os dados, aplicando técnicas de estatística descritiva para extrair insights relevantes sobre a remuneração na área de dados.

---

## 🛠️ Habilidades e Ferramentas

* **Escola:** Dados
* **Habilidades:** Estatística descritiva
* **Propriedades Adicionais:** Desafio

---

## 📁 Arquivos do Desafio

* `salario_profissionais_dados.csv` (269.7KB)

---

## 📖 Dicionário de Dados

O dataset contém dados de salários de profissionais da área de dados de diversas partes do mundo.

| Coluna | Descrição |
| :--- | :--- |
| `work_year` | Ano de referência do salário |
| `experience_level` | Nível de experiência (ex: EN = iniciante, MI = intermediário) |
| `employment_type` | Tipo de contrato (CLT, freelancer, etc.) |
| `job_title` | Cargo ocupado |
| `salary_in_usd` | Salário anual em dólares |
| `employee_residence` | País de residência do profissional |
| `company_location` | Localização da empresa |
| `company_size` | Tamanho da empresa (P = pequena, M = média, L = grande) |

### **Legenda das Categorias**

#### **Experience_level**

| Código | Descrição |
| :--- | :--- |
| `EN` | Entry-level / Iniciante |
| `MI` | Mid-level / Intermediário |
| `SE` | Senior-level / Sênior |
| `EX` | Executive-level / Executivo |

#### **Company_size**

| Código | Descrição |
| :--- | :--- |
| `S` | Pequena empresa |
| `M` | Média empresa |
| `L` | Grande empresa |

---

## 🚀 Como Começar?

1.  Importe os dados usando a biblioteca `pandas` e explore as primeiras linhas com `.head()`.
2.  Verifique os tipos de dados, identifique colunas importantes e confira se há valores ausentes.
3.  Comece com uma análise exploratória simples: frequências, distribuições e estatísticas básicas.
4.  Use gráficos para visualizar padrões e tendências.

---

## 📋 Etapas de Desenvolvimento

#### **Etapa 01) Importação e Exploração Inicial da Base**

Antes de qualquer análise, é fundamental entender a estrutura dos dados. Nesta etapa, seu foco será importar o dataset e realizar uma primeira exploração para verificar:

* Quais colunas estão disponíveis?
* Quantas linhas existem?
* Existem dados ausentes?
* Quais são os tipos de variáveis?

> **Dica:** Antes de começar a análise, entenda bem o que cada variável representa. Isso ajuda a guiar a leitura dos dados. Você pode usar métodos como `df.head()`, `df.shape`, `df.info()` e `df.isnull().sum()`.

#### **Etapa 02) Frequência e Distribuição das Categorias**

Agora que você já conhece a base, vamos explorar as variáveis categóricas. Seu objetivo aqui é responder perguntas como:

* Quais são os cargos mais comuns?
* Qual o nível de experiência predominante?
* Qual o tamanho de empresa mais frequente?

> **Dica:** Use `.value_counts().head(10)` para ver os mais frequentes e `normalize=True` para obter as proporções relativas (porcentagem).

#### **Etapa 03) Estatísticas Descritivas**

A principal variável numérica da base é `salary_in_usd`. Nesta etapa, você vai se aprofundar na análise estatística dessa variável para entender como os salários estão distribuídos.

* **Medidas de tendência central:** média, mediana.
* **Medidas de dispersão:** desvio padrão, mínimo e máximo.
* **Distribuição geral:** através de histogramas.
* **Comparações por grupos:** especialmente por nível de experiência (usando boxplots).

> **Dica:** Use `groupby()` com `mean()` para comparar médias entre categorias. Ex: `df.groupby('company_size')['salary_in_usd'].mean()`.

#### **Etapa 04) Comparações por País**

Agora que você já entendeu os salários em geral, é hora de investigar como eles variam entre diferentes grupos. O objetivo será:

* Verificar os 10 países com as maiores médias salariais.

> **Dica:** Use `groupby()` com `.mean()` para calcular médias por categoria, e depois ordene com `.sort_values()` para ver os maiores valores primeiro.

#### **Etapa 05) Correlações e Tendências**

Por fim, vamos analisar se existe alguma relação entre salário e outras variáveis quantitativas da base. As perguntas principais aqui são:

* Existe alguma tendência de aumento salarial com os anos?
* Quanto maior o tempo de experiência, maior o salário?

> **Dica:** Use `.corr()` para criar uma matriz de correlação entre `salary_in_usd`, `work_year` e `years_of_experience` (se disponível).

---

## 🏅 Critérios de Avaliação

| Critério | Descrição do que será avaliado | Pontos |
| :--- | :--- | :--- |
| **Importação e Exploração Inicial dos Dados** | Leitura correta do arquivo com pandas, análise inicial com `.info()`, `.shape()`, `.head()` e verificação de valores nulos. | 20 |
| **Análise de Frequências e Visualizações** | Análise das variáveis categóricas com `value_counts()` e interpretação correta dos cargos mais frequentes. Uso adequado de filtros como `head(10)`. | 20 |
| **Estatísticas Descritivas de Salários** | Aplicação das principais medidas descritivas (média, mediana, desvio padrão, etc.), além de visualização com histograma e boxplot para comparação entre grupos (como nível de experiência). | 20 |
| **Análises Comparativas e Correlações** | Cálculo da média salarial por grupo usando `groupby()` e interpretação de quais cargos e países apresentam os maiores valores médios. | 20 |
| **Correlação com Tempo e Experiência** | Aplicação da matriz de correlação entre variáveis numéricas com `.corr()` e interpretação dos coeficientes, especialmente entre `salary_in_usd`, `work_year` e `years_of_experience`. | 20 |

## Autor: Jonathan Salles Queiroz
