# 📈 Análise de Crédito com Random Forest e KNN

## 📌 Previsão de Score de Crédito com Machine Learning

Este projeto tem como objetivo analisar dados de crédito e criar um modelo de previsão utilizando os algoritmos de machine learning Random Forest e K-Nearest Neighbors (KNN), para prever o score de crédito de clientes com base em suas informações financeiras.

## 🛠️ Tecnologias Utilizadas
- **Linguagem:** Python
- **Bibliotecas:** Pandas, Scikit-Learn
- **Modelos:** Random Forest, K-Nearest Neighbors (KNN)
- **Ferramentas:** Jupyter Notebook, Git, GitHub

## 🔥 Objetivos de Aprendizado 🎯
- 🔹 Pré-processamento e limpeza de grandes volumes de dados
- 🔹 Implementação de modelos de machine learning (Random Forest e KNN)
- 🔹 Análise de variáveis e transformação de features
- 🔹 Avaliação de modelos com métricas como acurácia, precisão e recall

## 📌 Estrutura do Projeto

```
previsao-score-credito-random-forest-knn/
├── data/                # Conjuntos de dados utilizados na análise  
│   ├── clientes.csv     # Dados de clientes com informações financeiras  
│   └── novos_clientes.csv # Dados de novos clientes para teste do modelo  
├── src/                 # Scripts de pré-processamento e modelagem  
├── notebooks/           # Notebooks para análise exploratória  
├── requirements.txt     # Arquivo com as dependências necessárias para o projeto  
├── README.md            # Documento de explicação do projeto  
└── LICENSE              # Licença de uso do projeto
```

⚙️ **Instalação das Dependências:**
```sh
pip install -r requirements.txt
```

## 📊 Resultados da Análise

### 1. Desempenho do Modelo:
- **Random Forest Classifier:** 83% de precisão
- **K-Nearest Neighbors:** 73% de precisão

O modelo Random Forest supera o KNN e é escolhido para análise adicional.

### 2. Características Mais Importantes:
As 5 características mais influentes para determinar o score de crédito são:
- **dívida_total**
- **mix_crédito**
- **juros_emprestimo**
- **utilização_crédito**
- **idade**

### 3. Comparação com a Linha de Base:
- A categoria de score de crédito **'Standard'** representa 53% do conjunto de dados.
- Nosso modelo **Random Forest** alcança **83% de precisão**, superando significativamente a linha de base.

### 4. Impacto nos Negócios:
Com este modelo de 83% de precisão, a empresa agora pode:
- Avaliar melhor a capacidade de crédito dos clientes
- Personalizar produtos financeiros de acordo com os perfis dos clientes
- Implementar estratégias de gestão de risco mais eficazes
- Potencialmente aumentar as taxas de aprovação para clientes com boa capacidade de crédito

### 5. Próximos Passos:
- Considerar engenharia de características para melhorar o desempenho do modelo
- Explorar outros algoritmos (por exemplo, Gradient Boosting, SVM)
- Investigar os casos classificados incorretamente para entender as limitações do modelo
- Desenvolver um sistema para monitoramento e atualização contínua do modelo

Esta análise fornece insights valiosos sobre os scores de crédito dos clientes, permitindo uma tomada de decisão mais informada em empréstimos e ofertas de produtos financeiros.

---

📌 **Autor:** Rafael Dutra (Haell39-Github)  
📬 **Contato:** [rafaeldutrapro@gmail.com]

