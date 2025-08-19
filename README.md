# Modelo Preditivo de Churn – Desafio Telecom X (Parte 2)

Este repositório contém a segunda parte do desafio de análise de dados da Telecom X, focada no desenvolvimento de um modelo de **Machine Learning** para prever a evasão de clientes (churn). Este projeto é a continuação direta da análise exploratória de dados (EDA) realizada no desafio anterior.

## 🎯 Objetivo do Projeto

Após identificar os principais fatores que levam à evasão de clientes na primeira parte da análise, o objetivo deste desafio foi construir, treinar e otimizar um modelo de classificação capaz de **prever com alta acurácia quais clientes têm maior probabilidade de cancelar seus serviços**. O modelo final pode ser utilizado pela empresa para identificar clientes em risco e aplicar estratégias de retenção de forma proativa.

## ⚙️ Processo de Machine Learning

O desenvolvimento do modelo seguiu um fluxo de trabalho estruturado, desde a preparação dos dados até a otimização do algoritmo final.

### 1. Pré-processamento e Preparação dos Dados

Antes do treinamento, os dados limpos do desafio anterior (`dados_tratados.csv`) passaram por uma etapa de pré-processamento para adequá-los aos algoritmos de machine learning:

- **Seleção de Features:** A coluna `ID_Cliente`, que não possui valor preditivo, foi removida.
- **Encoding de Variáveis Categóricas:** Todas as colunas com dados textuais (como `Genero`, `Contrato`, `Servico_Internet`, etc.) foram transformadas em formato numérico utilizando a técnica de **One-Hot Encoding** (`pd.get_dummies`).
- **Transformação da Variável Alvo:** A coluna `Churn` (com valores "Sim" e "Nao") foi convertida para um formato binário (1 e 0).

### 2. Treinamento e Avaliação de Modelos

- **Divisão dos Dados:** O conjunto de dados foi dividido em dois subconjuntos: 70% para **treinamento** e 30% para **teste**.
- **Modelos de Baseline:** Três algoritmos de classificação foram treinados e avaliados para estabelecer uma performance de base:
    1.  Regressão Logística (`LogisticRegression`)
    2.  Árvore de Decisão (`DecisionTreeClassifier`)
    3.  Random Forest (`RandomForestClassifier`)
- **Métrica de Avaliação:** A **acurácia** foi a principal métrica utilizada para comparar o desempenho dos modelos, complementada pela análise da **matriz de confusão** e pelo **relatório de classificação**.

### 3. Otimização de Hiperparâmetros

O modelo **Random Forest**, que apresentou a melhor acurácia inicial, foi selecionado para uma etapa de otimização. Utilizou-se a técnica de **GridSearchCV** para testar sistematicamente diferentes combinações de hiperparâmetros (como `n_estimators` e `max_depth`) e encontrar a configuração que maximiza o desempenho do modelo.

## 🛠️ Ferramentas e Bibliotecas

- **Linguagem:** Python
- **Bibliotecas Principais:**
    - `Pandas`: Para manipulação de dados.
    - `Scikit-learn`: Para pré-processamento (`train_test_split`), modelagem (`LogisticRegression`, `DecisionTreeClassifier`, `RandomForestClassifier`), otimização (`GridSearchCV`) e avaliação (`accuracy_score`, `confusion_matrix`).

## 📊 Resultados

- **Performance dos Modelos de Baseline:** O Random Forest se destacou como o modelo com a maior acurácia entre os três algoritmos testados inicialmente.
- **Performance do Modelo Otimizado:** Após a otimização com GridSearchCV, a acurácia do modelo Random Forest foi **aprimorada**, resultando em um classificador final mais robusto e preciso.

## 🏆 Conclusão

O projeto foi bem-sucedido na criação de um modelo preditivo eficaz para a evasão de clientes. O modelo **Random Forest otimizado** demonstrou ser uma ferramenta valiosa, capaz de identificar clientes com alta probabilidade de churn. A implementação deste modelo pode gerar um impacto de negócio significativo para a Telecom X, permitindo a redução de perdas de receita através de ações de retenção direcionadas e inteligentes.

## 🚀 Como Executar o Projeto

1.  Este projeto depende do arquivo `dados_tratados.csv`, gerado no desafio anterior. Certifique-se de que ele está disponível no mesmo diretório.
2.  Abra o notebook `Desafio_TelecomX_BR_Pedro_pt2.ipynb` em um ambiente como Jupyter ou Google Colab.
3.  Execute as células em ordem para reproduzir todo o processo de pré-processamento, treinamento, avaliação e otimização do modelo.
