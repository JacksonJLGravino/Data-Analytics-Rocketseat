# Data Analytics - Insights na TechGrow - Rocketseat

## 🧠 Contexto

Você faz parte do time de dados de uma empresa SaaS fictícia chamada **TechGrow**, que oferece soluções de gestão para pequenos negócios.

Nos últimos meses, a empresa identificou um aumento significativo na taxa de cancelamento (**churn**), e o time de produto precisa entender:

- Por que os clientes estão cancelando?
- Quais clientes estão em risco?
- O que pode ser feito para reduzir o churn?

## 🎯 Objetivo

Realizar uma análise completa de dados para:

- Explorar e entender o comportamento dos clientes
- Identificar fatores que influenciam o churn
- Construir modelos preditivos
- Gerar insights acionáveis para o negócio

## 📂 Base de Dados

O dataset contém informações sobre:

- Tempo de contrato
- Plano contratado
- Região
- Frequência de uso (logins)
- Uso médio diário
- Tickets de suporte
- Valor mensal
- Inadimplência
- Quantidade de funcionários
- Variável alvo: **churn (0 = ativo, 1 = cancelado)**

## 🔍 Etapa 1: Análise Exploratória (EDA)

Principais análises realizadas:

- Verificação de tipos de dados e valores nulos
- Estatísticas descritivas
- Análise de distribuição das variáveis
- Comparação entre clientes que cancelaram e os que permaneceram

### 📊 Principais insights:

- Aproximadamente **42% dos clientes cancelaram** (churn elevado)
- Clientes com:
  - Menor tempo de contrato
  - Menor número de logins
  - Maior número de tickets
  - Maior inadimplência
    possuem maior propensão ao churn

## 🧹 Etapa 2: Tratamento de Dados

- Encoding de variáveis categóricas (One-Hot Encoding)
- Padronização das variáveis numéricas (StandardScaler)
- Remoção de multicolinearidade:
  - `uso_media_diaria_horas` (correlacionada com logins)
  - `qtd_funcionarios` (correlacionada com valor mensal)

## 🤖 Etapa 3: Modelagem

Divisão dos dados:

- 70% treino
- 30% teste (com estratificação)

Modelos utilizados:

- Regressão Logística (baseline)
- Random Forest
- XGBoost

## 📈 Etapa 4: Avaliação dos Modelos

Métricas utilizadas:

- Accuracy
- Precision
- Recall ⭐
- F1-score
- ROC-AUC

### 🏆 Resultados (Resumo)

| Modelo              | Accuracy | Precision | Recall | F1-score | ROC-AUC |
| ------------------- | -------- | --------- | ------ | -------- | ------- |
| Logistic Regression | 0.93     | 0.86      | 1.00   | 0.92     | 1.00    |
| Random Forest       | 1.00     | 1.00      | 1.00   | 1.00     | 1.00    |
| XGBoost             | 0.90     | 0.81      | 1.00   | 0.89     | 0.91    |

### ⚠️ Observações

- Todos os modelos apresentaram **recall perfeito (1.0)**
- Random Forest apresentou métricas perfeitas, indicando possível **overfitting**
- A Regressão Logística foi escolhida por:
  - equilíbrio entre métricas
  - maior interpretabilidade

## 🔍 Matriz de Confusão (Regressão Logística)

- 28 acertos em 30 previsões
- **0 falsos negativos** (nenhum cliente perdido)
- 2 falsos positivos (alertas desnecessários)

👉 Ideal para churn, pois evita perda de clientes.

## 📉 Curva ROC

- ROC-AUC = **1.0**
- Excelente capacidade de separação entre clientes que cancelam e não cancelam

## 💡 Principais Insights de Negócio

### 🚨 Fatores que aumentam churn:

- Inadimplência
- Alto número de tickets de suporte

### 📉 Fatores que reduzem churn:

- Maior engajamento (logins)
- Maior tempo de contrato

## 🚀 Recomendações

### 🎧 Melhorar suporte

- Identificar principais problemas recorrentes
- Reduzir necessidade de abertura de tickets

### 💰 Reduzir inadimplência

- Alertas de pagamento
- Flexibilização de cobrança
- Opções de renegociação

### 📊 Aumentar engajamento

- Melhor onboarding
- Treinamentos e tutoriais
- Avaliar adequação ao público-alvo

### ⏳ Focar nos primeiros meses

- Acompanhamento ativo de novos clientes
- Garantir geração de valor inicial

### 🎁 Estratégias de retenção

- Benefícios por tempo de uso
- Incentivo à migração de planos

## 🏁 Conclusão

O modelo desenvolvido demonstrou alta capacidade de identificar clientes com risco de churn, permitindo ações preventivas eficazes.

A análise mostrou que churn está fortemente relacionado a:

- Experiência do usuário
- Valor percebido
- Questões financeiras

Com base nesses insights, a empresa pode atuar de forma estratégica para melhorar retenção e reduzir cancelamentos.

## 🛠️ Tecnologias utilizadas

- Python
- Pandas
- NumPy
- Matplotlib / Seaborn
- Scikit-learn
- XGBoost
