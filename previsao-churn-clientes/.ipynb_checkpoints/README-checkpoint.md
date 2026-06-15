# Previsão de Churn de Clientes

Este projeto tem como objetivo prever quais clientes têm maior probabilidade de cancelar o serviço (churn) usando Machine Learning.

### O que fiz:
- Análise exploratória dos dados de uma empresa de telecomunicações
- Tratamento de dados (valores faltantes, encoding de variáveis categóricas)
- Feature Engineering (criei algumas variáveis novas)
- Testei 3 modelos diferentes (Logistic Regression, Random Forest e XGBoost)
- Avaliação dos modelos usando AUC, Recall, F1-score
- Análise de quais variáveis mais influenciam o churn

### Principais resultados:
- Melhor modelo: **Logistic Regression** com AUC ≈ 0.84
- As variáveis mais importantes foram: tipo de contrato, tempo de fidelidade, valor mensal e serviço de internet
- Insight: Clientes com contrato mensal e conta mais cara têm muito mais chance de cancelar

### Tecnologias utilizadas:
- Python
- Pandas e NumPy
- Matplotlib + Seaborn (visualizações)
- Scikit-learn e XGBoost (modelos de Machine Learning)
- Jupyter Notebook
