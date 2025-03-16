# **Previsão de Score de Crédito** 🚀

**Autor:** Rafael A. Dutra
**Data:** 15/03/2025
**Repositório:** https://github.com/Haell39/Analise-Credito/tree/main

---

## **Visão Geral** 📋

Bem-vindo ao projeto **Previsão de Score de Crédito**! Este trabalho utiliza técnicas de ciência de dados para prever o `score_credito` de clientes com base em variáveis financeiras e comportamentais. O objetivo é fornecer insights acionáveis para decisões de crédito, combinando exploração de dados, modelagem preditiva e análise prática.

---

## **Objetivo** 🎯

Prever o `score_credito` (classificado como "Good", "Standard" ou "Poor") de clientes, utilizando:

- **Dataset:** `clientes.csv` (100.000 registros) e `novos_clientes.csv` (3 novos clientes).
- **Variáveis principais:** `mix_credito`, `num_pagamentos_atrasados`, `num_contas`, `juros_emprestimo`, `num_cartoes`.

---

## **Metodologia** 🛠️

1. **Exploração de Dados** 📊

   - Visualizações com histogramas, boxplots e heatmaps para entender distribuições e correlações.
   - Identificação de padrões, como o impacto de atrasos no pagamento no `score_credito`.

2. **Pré-processamento** 🔧

   - Codificação de variáveis categóricas com `LabelEncoder`.
   - Seleção das 5 variáveis mais correlacionadas ao alvo.

3. **Modelagem** 🤖

   - **Random Forest:** Acurácia de 0.72.
   - **KNN (k=5):** Acurácia de 0.70.
   - Avaliação da importância das features (e.g., `juros_emprestimo` como fator dominante).

4. **Previsão** 🚀
   - Aplicação dos modelos em novos clientes com resultados interpretados.

---

## **Resultados** 📈

- **Random Forest:** Previu "Poor" para Cliente 0 e "Good" para Clientes 1 e 2.
- **KNN:** Previu "Poor" para Cliente 0 e "Standard" para Clientes 1 e 2.
- **Conclusão:** O Random Forest foi recomendado por sua maior acurácia (0.72).

| Cliente | RF Prediction | KNN Prediction |
| ------- | ------------- | -------------- |
| 0       | Poor          | Poor           |
| 1       | Good          | Standard       |
| 2       | Good          | Standard       |

---

## **Tecnologias Utilizadas** 💻

- **Python:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`.
- **Ambiente:** Jupyter Notebook.
- **Ferramentas:** VS Code, Notion (Anotações)

---

## **Como Executar** ⚙️

1. Clone o repositório: `git clone [URL]`.
2. Instale as dependências: `pip install -r requirements.txt`.
3. Execute o notebook: `jupyter notebook Previsao_Score_Credito.ipynb`.

---

## **Diferenciais** 🌟

- Exploração detalhada com visualizações intuitivas.
- Comparação de dois modelos preditivos.
- Aplicação prática em novos dados com análise crítica dos resultados.

---

## **Próximos Passos** 💡

- Implementar validação cruzada para maior robustez.
- Explorar métricas como F1-score para classes desbalanceadas.
- Otimizar hiperparâmetros dos modelos.

---

**Contato:** rafaeldutrapro@gmail.com <br>
**Agradecimentos:** Obrigado por conferir meu trabalho! Feedback é sempre bem-vindo! 😊
