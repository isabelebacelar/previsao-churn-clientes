# Previsão de Churn de Clientes

Projeto de Machine Learning desenvolvido para analisar o comportamento de clientes de uma empresa de telecomunicações e identificar padrões associados ao cancelamento do serviço (churn).

O projeto utiliza análise exploratória de dados, feature engineering e modelos de classificação para estimar a probabilidade de churn e gerar informações que possam apoiar estratégias de retenção de clientes.

## Dataset

O projeto utiliza o **Telco Customer Churn**, conjunto de dados contendo informações sobre clientes de uma empresa de telecomunicações.

O dataset possui **7.043 registros e 21 atributos iniciais**, incluindo informações sobre:

- perfil do cliente;
- tempo de relacionamento;
- serviços contratados;
- tipo de contrato;
- forma de pagamento;
- cobranças mensais e totais;
- ocorrência de churn.

A variável `Churn` é utilizada como alvo do modelo de classificação.

## Análise Exploratória

A análise exploratória busca compreender a distribuição dos dados e identificar padrões relacionados ao churn.

Foram analisados aspectos como:

- distribuição da variável `Churn`;
- tipo de contrato;
- tempo de relacionamento (`tenure`);
- valor da mensalidade (`MonthlyCharges`);
- tipo de serviço de internet;
- quantidade de serviços contratados.

As análises indicam associação entre maior ocorrência de churn e características como contratos mensais, menor tempo de relacionamento e mensalidades mais altas.

## Preparação dos Dados

Antes do treinamento dos modelos, foram realizadas etapas de preparação e transformação dos dados.

Entre elas:

- conversão de `TotalCharges` para formato numérico;
- remoção do identificador `customerID`;
- transformação da variável alvo `Churn` em valores binários;
- tratamento de valores ausentes;
- codificação de variáveis categóricas com One-Hot Encoding;
- padronização das variáveis numéricas;
- separação dos dados em conjuntos de treino e teste com estratificação.

O preprocessing foi implementado utilizando `Pipeline` e `ColumnTransformer` do Scikit-learn, permitindo que as transformações sejam aprendidas apenas a partir dos dados de treinamento e reduzindo o risco de data leakage.

## Feature Engineering

Foram criadas novas variáveis para representar características adicionais dos clientes:

- `TotalServices`: quantidade de serviços adicionais contratados;
- `HasInternet`: indica se o cliente possui serviço de internet;
- `HasFiber`: indica se o cliente utiliza internet por fibra óptica.

## Modelos

Foram comparados três algoritmos de classificação:

- Logistic Regression;
- Random Forest;
- XGBoost.

Todos os modelos utilizam o mesmo pipeline de preprocessing para manter o processo de comparação consistente.

## Avaliação

Os modelos foram avaliados utilizando:

- ROC-AUC;
- Recall;
- F1-score;
- Classification Report;
- Confusion Matrix.

Entre os modelos avaliados, a **Logistic Regression apresentou o melhor ROC-AUC, aproximadamente 0,84**.

O Recall também foi considerado uma métrica relevante, pois identificar clientes que realmente apresentam risco de churn pode ser importante para ações de retenção.

## Principais Insights

A análise identificou padrões associados a maior ocorrência de churn, principalmente entre clientes com:

- contratos mensais;
- menor tempo de relacionamento;
- mensalidades mais altas;
- serviço de internet por fibra óptica.

Esses resultados podem auxiliar na investigação de perfis com maior risco e na definição de estratégias de retenção.

É importante destacar que essas associações não representam necessariamente relações de causa e efeito.

## Estrutura do Projeto

```text
previsao-churn-clientes/
├── data/
│   └── Telco-Customer-Churn.csv
├── notebooks/
│   └── churn_analise.ipynb
├── .gitignore
├── README.md
└── requirements.txt
```

## Tecnologias

- Python
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook

## Como Executar

Clone o repositório:

```bash
git clone https://github.com/isabelebacelar/previsao-churn-clientes.git
cd previsao-churn-clientes
```

Instale as dependências:

```bash
pip install -r requirements.txt
```

Inicie o Jupyter Notebook:

```bash
jupyter notebook
```

Depois, abra:

```text
notebooks/churn_analise.ipynb
```

## Limitações e Próximos Passos

O projeto utiliza uma divisão estratificada entre treino e teste para avaliação dos modelos.

Como evolução, podem ser adicionados:

- validação cruzada;
- otimização de hiperparâmetros;
- análise do threshold de classificação;
- comparação mais detalhada entre precisão e recall;
- análise dos coeficientes da Logistic Regression;
- interpretação dos modelos com técnicas como SHAP.

## Conclusão

O projeto demonstra um fluxo completo de Machine Learning para classificação, passando pela análise exploratória, preparação dos dados, feature engineering, construção de pipelines, treinamento, comparação de modelos e interpretação dos resultados.

A Logistic Regression apresentou o melhor desempenho em ROC-AUC entre os modelos avaliados, mostrando que um modelo relativamente simples pode produzir bons resultados para este problema.
