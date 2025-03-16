## **Relatório de Projeto: Análise e Previsão de Score de Crédito**  
**Autor:** Rafael A. Dutra  
**Data:** 15/03/2025  
**Objetivo:** Prever o `score_credito` de clientes com base em variáveis financeiras e comportamentais, utilizando técnicas de ciência de dados.

---

#### **Sumário**
1. [Introdução](#introdução)
2. [Exploração de Dados](#exploração-de-dados)
3. [Pré-processamento](#pré-processamento)
4. [Modelagem](#modelagem)
5. [Previsão em Novos Clientes](#previsão-em-novos-clientes)
6. [Conclusão](#conclusão)
7. [Recomendações](#recomendações)

---

#### **Introdução**  
Este projeto tem como objetivo analisar um conjunto de dados de clientes (`clientes.csv`) para prever o `score_credito` (classificado como "Good", "Standard" ou "Poor") com base em variáveis como `mix_credito`, `num_pagamentos_atrasados`, `num_contas`, `juros_emprestimo` e `num_cartoes`. Dois modelos de machine learning foram implementados — **Random Forest** e **KNN** — para comparar suas performances e aplicá-los em novos clientes (`novos_clientes.csv`), gerando previsões úteis para decisões financeiras.

---

#### **Exploração de Dados** 📊  
- **Carregamento e Inspeção:**  
  - Os dados foram carregados com a biblioteca `pandas`, contendo 100.000 linhas e 25 colunas.  
  - Não foram encontrados valores nulos, e os tipos de dados foram verificados com `table.info()`.  

- **Visualizações:**  
  - Histogramas (`sns.histplot`) para variáveis como `idade`, `salario_anual` e `divida_total` mostraram distribuições assimétricas e presença de outliers.  
  - Boxplots (`sns.boxplot`) indicaram variações salariais por `profissao` e `score_credito`.  
  - Um `sns.countplot` revelou desbalanceamento na variável alvo `score_credito`, com predominância da classe "Standard".  

- **Estatísticas Descritivas:**  
  - O método `table.describe()` forneceu um resumo das variáveis numéricas.  
  - Agrupamentos por `profissao` e `score_credito` calcularam médias de `salario_anual` e `divida_total`, destacando padrões comportamentais.  

**Insight:** A exploração identificou correlações importantes, como a relação entre `num_pagamentos_atrasados` e `score_credito`, e apontou a necessidade de lidar com o desbalanceamento de classes na modelagem.

---

#### **Pré-processamento** 🔧  
- **Codificação:**  
  - Variáveis categóricas (`profissao`, `mix_credito`, `comportamento_pagamento`) foram transformadas em valores numéricos com `LabelEncoder`.  
  - O `score_credito` foi codificado como: 0 = "Good", 1 = "Poor", 2 = "Standard".  

- **Correlações:**  
  - Correlações foram calculadas com `.corr()`, e as cinco variáveis mais relevantes para `score_credito` foram selecionadas.  
  - Um heatmap (`sns.heatmap`) confirmou a importância de `mix_credito` (correlação 0.27) e `num_pagamentos_atrasados` (0.20).  

**Insight:** As variáveis escolhidas (`mix_credito`, `num_pagamentos_atrasados`, `num_contas`, `juros_emprestimo`, `num_cartoes`) mostraram correlações moderadas a fortes, sendo ideais para a construção dos modelos.

---

#### **Modelagem** 🤖  
Dois modelos foram treinados e avaliados com base nas cinco variáveis mais correlacionadas:  

- **Random Forest:**  
  - **Acurácia:** 0.72.  
  - **Importância das Features:** `juros_emprestimo` (0.31), `num_pagamentos_atrasados` (0.23), `mix_credito` (0.19).  

- **KNN (k=5):**  
  - **Acurácia:** 0.70.  
  - **Importância via Permutação:** `juros_emprestimo` (0.22), `num_cartoes` (0.11), `num_pagamentos_atrasados` (0.11).  

- **Segmentação:**  
  - Análise das médias das variáveis por `score_credito` confirmou que clientes com "Poor" possuem mais atrasos e juros elevados.  

**Insight:** O Random Forest apresentou desempenho ligeiramente superior ao KNN, com ambos destacando `juros_emprestimo` como a variável mais influente.

---

#### **Previsão em Novos Clientes** 🚀  
- **Dados:** Arquivo `novos_clientes.csv` com 3 clientes.  
- **Resultados das Previsões:**  
  - **Cliente 0:** Ambos os modelos preveem **"Poor"**.  
  - **Cliente 1:** Random Forest prevê **"Good"**, KNN prevê **"Standard"**.  
  - **Cliente 2:** Random Forest prevê **"Good"**, KNN prevê **"Standard"**.  

| Cliente | Mix Credito | Pag. Atrasados | Contas | Juros | Cartões | RF Prediction | KNN Prediction |
|---------|-------------|----------------|--------|-------|---------|---------------|----------------|
| 0       | Normal      | 19.0           | 6.0    | 17.0  | 7.0     | Poor          | Poor           |
| 1       | Bom         | 18.0           | 5.0    | 10.0  | 5.0     | Good          | Standard       |
| 2       | Bom         | 14.0           | 8.0    | 14.0  | 6.0     | Good          | Standard       |

**Insight:** As divergências nas previsões para os Clientes 1 e 2 indicam perfis intermediários, sugerindo a necessidade de análise adicional para maior precisão.

---

#### **Conclusão** 📋  
- O modelo Random Forest (acurácia 0.72) demonstrou ser mais confiável que o KNN (0.70) para prever o `score_credito`.  
- Variáveis como `juros_emprestimo` e `num_pagamentos_atrasados` foram determinantes na classificação do score.  
- Para novos clientes, o Random Forest previu "Poor" para o Cliente 0 e "Good" para os Clientes 1 e 2, enquanto o KNN foi mais conservador, sugerindo "Standard" para os dois últimos.  

---

#### **Melhorias Futuras** 💡  
- **Próximas Implementações:**  
  - Aplicar validação cruzada para aumentar a robustez e a generalização dos modelos.  
  - Explorar métricas adicionais, como F1-score, para mitigar os efeitos do desbalanceamento de classes.  
  - Realizar a otimização de hiperparâmetros, ajustando, por exemplo, o número de árvores no Random Forest e o valor de k no KNN.  
  - Ampliar a documentação do código, detalhando as decisões metodológicas para facilitar revisões e manutenções futuras.  
