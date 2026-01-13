# FraudDetect-XGBoost: Uso do XGboost na deteção de fraudes em transações de Cartões de Crédito
## Descrição do Projeto

Este é um projeto pessoal que faz parte dos meus estudos em Data Science, utilizando Python para análise e modelagem de dados.

O conjunto de dados está disponível no Kaggle e refere-se a transações realizadas com cartões de crédito em setembro de 2013 por titulares de cartões europeus, ocorrendo ao longo de dois dias.

O objetivo deste projeto é construir um ***modelo preditivo***, utilizando o algoritmo XGBoost, que, de maneira o mais precisa possível, consiga identificar se uma transação é suspeita de fraude ou não. O dataset contém apenas variáveis numéricas de entrada, que resultam de uma transformação por Análise de Componentes Principais (PCA). As características, como V1, V2, ..., V28, representam os principais componentes extraídos pelo PCA, sendo que os dados originais não estão disponíveis. Em razão disso, informações adicionais sobre as características não podem ser fornecidas.


# Métricas

Como estamos lidando com um problema de classificação binária, as métricas utilizadas para avaliar o desempenho do modelo serão: 

## Matriz de Confusão

A matriz de confusão, de modo que os valores serão apresentados em forma de porcentagem relativa ao total de valores na classe real e de maneira absoluta. Isso permite visualizar a relação de valores previstos corretamente, falsos positivos e falsos negativos. 


|                | Predito Positivo | Predito Negativo |
|----------------|-----------------|-----------------|
| **Real Positivo** | TP              | FN              |
| **Real Negativo** | FP              | TN              |

Onde:

- **TP (True Positives)**: número de casos positivos corretamente classificados  
- **FP (False Positives)**: número de casos negativos classificados como positivos  
- **FN (False Negatives)**: número de casos positivos classificados como negativos  
- **TN (True Negatives)**: número de casos negativos corretamente classificados

A matriz de confusão ajuda a **visualizar erros do modelo** e é a base para métricas como **Precision, Recall e F1-Score**.

## F1-Score

Também utilizaremos o F1-Score para avaliar o desempenho do Modelo pois ele combina *Precision* e *Recall* em uma única métrica.

- *Precision* representa a proporção de predições positivas corretas em relação ao total de predições positivas

- *Recall* indica a proporção de casos positivos corretamente identificados em relação ao total de casos positivos reais

O F1-Score permite portanto, avaliar o modelo de forma equilibrada, priorizando um tanto evitar falsos positivos, quanto não deixar de detecta-los.

Ele é definido como:

$$
F1 = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}
{\text{Precision} + \text{Recall}}
$$

Onde:

$$
\text{Precision} = \frac{TP}{TP + FP} \quad
\text{Recall} = \frac{TP}{TP + FN}
$$


- **TP** = True Positives (verdadeiros positivos)  
- **FP** = False Positives (falsos positivos)  
- **FN** = False Negatives (falsos negativos)

## Outras Métricas

Por fim, utilizaremos o método classification_report para avaliar métricas adicionais do modelo, como Precision, Recall, F1-Score e acurácia, fornecendo uma visão mais completa do desempenho em cada classe.

### Dicionário de Variáveis

- ***V1, V2, …, V28:*** Componentes principais obtidos através da transformação PCA. Estes são valores numéricos que representam as variáveis originais após a redução de dimensionalidade com PCA.

- ***Time:*** Tempo, em segundos, decorrido entre cada transação e a primeira transação no dataset.

- ***Amount:*** Valor da transação. Esta variável pode ser usada em modelos de aprendizado que consideram custos sensíveis ao exemplo.

- ***Class:*** Variável de resposta, indicando se a transação é fraudulenta. Assume valor 1 em caso de fraude e 0 caso contrário.


### Tecnologias Utilizadas
#### Python: Ambiente de desenvolvimento 
#### Bibliotecas

- scikit-learn (versão 1.5.2): Métricas de Avaliação e Ferramentas utilitárias
- xgboost (versão 2.1.3): Algoritmo usado para a Classificação Binária
- matplotlib (3.10.0): Plotagem de Gráficos
- numpy (1.26.4): Manipulação de Dados
- pandas (2.2.3): Manipulação de Dados


### [Link para o Dataset Original no Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data)
