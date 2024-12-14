# MPV_Machine_Learning

# Predicting Student Retention and Dropout

## Conceito
Este projeto visa prever a retenção e o abandono de alunos em cursos de ensino superior com base em um conjunto de variáveis socioeconômicas e acadêmicas. A análise de abandono escolar é fundamental para instituições educacionais, pois ajuda a identificar fatores de risco que podem afetar a permanência dos alunos, permitindo intervenções mais eficazes para melhorar a taxa de conclusão dos cursos.

## Intuito
O objetivo principal é construir modelos preditivos que possam identificar alunos com maior risco de desistência, ajudando as instituições a adotar medidas proativas para aumentar a retenção de alunos. Com a aplicação de técnicas de machine learning, o modelo poderá auxiliar no diagnóstico precoce de padrões de abandono, o que pode influenciar políticas educacionais e ações específicas para apoiar os alunos.

## Métodos

### Pré-processamento de Dados
O dataset utilizado neste projeto foi limpo e transformado para melhorar a qualidade dos dados. As principais etapas de pré-processamento incluem:
- **Tratamento de dados faltantes**: Utilizamos diferentes estratégias para imputação de valores faltantes, como a média para variáveis numéricas e a moda para variáveis categóricas.
- **Codificação de variáveis categóricas**: As variáveis categóricas foram transformadas utilizando técnicas de One-Hot Encoding, que geram colunas binárias representando as categorias.
- **Escalonamento de variáveis numéricas**: As variáveis numéricas foram escalonadas para um padrão comum utilizando a técnica de **StandardScaler**, o que ajuda a melhorar o desempenho de modelos sensíveis a escala como SVM e XGBoost.

### Modelos Utilizados
Foram explorados diversos algoritmos de machine learning para o problema de classificação binária/múltipla. Os principais modelos incluídos neste projeto são:

- **Random Forest**: Um modelo de ensemble baseado em árvores de decisão, conhecido por sua robustez e capacidade de lidar com dados desbalanceados.
- **XGBoost**: Um modelo de boosting que utiliza árvores de decisão de forma sequencial, com o objetivo de minimizar o erro residual do modelo anterior.
- **SVM (Support Vector Machine)**: Um classificador baseado na busca da melhor margem de separação entre as classes, sendo eficaz em problemas de alta dimensionalidade.

### Validação e Avaliação
- **Validação Cruzada**: Para garantir a robustez dos modelos, utilizamos a validação cruzada (K-fold), o que ajuda a mitigar o risco de overfitting e fornece uma visão mais precisa do desempenho do modelo.
- **Métricas de Avaliação**: As principais métricas utilizadas para avaliar os modelos incluem:
  - **Acurácia**: A proporção de previsões corretas no conjunto de dados.
  - **F1-Score**: Métrica que combina precisão e recall, útil quando há classes desbalanceadas.
  - **Matriz de Confusão**: Uma tabela que visualiza o desempenho do modelo em termos de falso positivo, falso negativo, verdadeiro positivo e verdadeiro negativo.
  - **ROC-AUC**: Avaliação da performance do modelo em uma curva que representa a taxa de falso positivo versus a taxa de verdadeiro positivo.

### Ensemble Methods
Além de treinar modelos individuais, foram testados métodos de **ensemble** para melhorar o desempenho:
- **Voting Classifier**: Combina a previsão de múltiplos modelos (Random Forest, XGBoost e SVM) e escolhe a classe mais votada como a previsão final.
- **Stacking Classifier**: Combina diferentes modelos base e usa um modelo final (metamodelo) para realizar a previsão com base nas saídas dos modelos base.

## Resultados
Após o treinamento e validação dos modelos, observou-se que o **XGBoost** e o **SVM** foram os modelos mais promissores, apresentando boa performance tanto na acurácia quanto no **F1-Score**. O **Random Forest** apresentou sinais de overfitting, com uma grande diferença entre as acurácias de treinamento e teste.

A acurácia final do **VotingClassifier** e **StackingClassifier** foi comparável, com uma leve vantagem para o **Stacking**, que apresentou um desempenho ligeiramente superior.

## Conclusão
A combinação de múltiplos modelos (ensemble methods) mostrou-se eficaz para melhorar a previsão de retenção e abandono de alunos. A metodologia empregada pode ser útil para instituições de ensino que buscam estratégias baseadas em dados para aumentar as taxas de conclusão de cursos.
