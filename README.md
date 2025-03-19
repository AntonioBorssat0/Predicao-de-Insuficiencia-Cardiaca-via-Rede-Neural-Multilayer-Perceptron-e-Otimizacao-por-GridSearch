# 🏥 Predição de Insuficiência Cardíaca via Rede Neural MLP e Grid Search

## 📌 Descrição
Este projeto implementa um modelo de rede neural **Multilayer Perceptron (MLP)** para **classificação binária** do risco de insuficiência cardíaca em pacientes. O modelo é otimizado utilizando **Grid Search** e avaliado com métricas de desempenho, como **precisão, recall e F1-Score**. A análise de importância das variáveis foi realizada com **SHAP**.

## 🎯 Objetivos
- Construir um modelo de **Rede Neural Artificial (RNA)** para prever insuficiência cardíaca.
- Otimizar os hiperparâmetros do MLP usando **Grid Search**.
- Identificar as variáveis clínicas com maior impacto nas predições.
- Avaliar as limitações do modelo e propor melhorias.

## 🏥 Conjunto de Dados
Os dados foram coletados do Kaggle ([Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction/data)) e contêm informações de **918 pacientes**.

### 📊 Principais Variáveis:
- **Numéricas**: `Age`, `RestingBP`, `Cholesterol`, `MaxHR`, `Oldpeak`
- **Categóricas**: `Sex`, `ChestPainType`, `FastingBS`, `RestingECG`, `ExerciseAngina`, `ST_Slope`
- **Variável Alvo (Target)**: `HeartDisease` (0 = Sem Doença, 1 = Com Doença)

## 🛠️ Metodologia
1. **Coleta e Pré-processamento dos Dados**:
   - Remoção de valores ausentes e inconsistentes.
   - Codificação de variáveis categóricas (One-Hot Encoding e Label Encoding).
   - Normalização dos dados com **StandardScaler**.

2. **Análise Exploratória**:
   - Estatísticas descritivas e distribuição das variáveis.
   - Matriz de correlação e gráficos para identificar padrões nos dados.

3. **Treinamento do Modelo**:
   - Arquitetura **MLP** com múltiplas camadas ocultas.
   - Otimização dos hiperparâmetros via **Grid Search**.
   - Uso de **Early Stopping** para evitar overfitting.
   - Validação cruzada **Stratified K-Fold (k=3)**.

## 📈 Resultados
- **Precisão Média**: **85%**
- **Recall Médio**: **85%**
- **F1-Score Médio**: **85%**
- **Principais Variáveis que Impactam a Predição (via SHAP)**:
  - `ST_Slope_Flat`
  - `Sex`
  - `ChestPainType_ATA`
  - `ExerciseAngina`
  - `ChestPainType_NAP`

### 🔥 Matriz de Confusão
O modelo obteve um bom desempenho geral, mas apresentou **23 falsos negativos**, o que pode ser crítico no contexto clínico.

## 🔬 **Discussões e Limitações**  
- O modelo apresentou **bom equilíbrio entre precisão e recall**.  
- **Falsos negativos podem ser problemáticos** para diagnóstico clínico.  
- O espaço de busca do **Grid Search** foi limitado devido a restrições computacionais.  
- **Possíveis melhorias** incluem a experimentação com **modelos híbridos** e técnicas avançadas de **ajuste de hiperparâmetros**.  

