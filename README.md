# Previsão de Churn de Clientes

**Projeto de Machine Learning**

Desenvolvi um modelo para prever quais clientes têm maior risco de cancelar o serviço (churn) em uma empresa de telecomunicações.

### O que fiz:
- Análise exploratória dos dados
- Tratamento de valores faltantes e encoding de variáveis categóricas
- Feature Engineering
- Teste e comparação de 3 modelos (Logistic Regression, Random Forest e XGBoost)
- Avaliação com AUC, Recall e F1-score
- Análise de Feature Importance

### Resultados:
- Melhor modelo: **Logistic Regression** com AUC ≈ 0.84
- Principais fatores de churn: contrato mensal, tempo de fidelidade e valor da mensalidade

### Tecnologias:
- Python, Pandas, Scikit-learn, XGBoost
- Matplotlib + Seaborn
- Jupyter Notebook

**Insight de negócio:** Clientes com contrato mensal e mensalidades altas têm muito mais chance de cancelar. O modelo pode ajudar a empresa a focar ações de retenção nesses perfis.
