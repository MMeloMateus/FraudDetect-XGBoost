# FraudDetect-XGBoost
## Uso do XGboost na deteção de fraudes em transações de Cartões de Crédito

Este é um projeto pessoal que faz parte dos meus estudos em Data Science, utilizando Python para análise e modelagem de dados.

O conjunto de dados está disponível no Kaggle e refere-se a transações realizadas com cartões de crédito em setembro de 2013 por titulares de cartões europeus, ocorrendo ao longo de dois dias.

O objetivo deste projeto é construir um ***modelo preditivo***, utilizando o algoritmo XGBoost, que, de maneira o mais precisa possível, consiga identificar se uma transação é suspeita de fraude ou não. O dataset contém apenas variáveis numéricas de entrada, que resultam de uma transformação por Análise de Componentes Principais (PCA). As características, como V1, V2, ..., V28, representam os principais componentes extraídos pelo PCA, sendo que os dados originais não estão disponíveis. Em razão disso, informações adicionais sobre as características não podem ser fornecidas.

O dataset original pode ser acessado no Kaggle através do seguinte link: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data


### Métricas

Como estamos lidando com um problema de classificação binária, as métricas utilizadas para avaliar o desempenho do modelo serão: a matriz de confusão configurada com o padrão de normalização 'pred', de modo que os valores serão apresentados em forma de porcentagem relativa ao total de valores na classe real. Isso permite visualizar a relação de valores previstos corretamente, falsos positivos e falsos negativos. Além disso, utilizaremos a Área Sob a Curva de Precisão-Recall (AUPRC) e a Área Sob a Curva ROC (AUC-ROC) para avaliar o desempenho do modelo, especialmente em cenários de desbalanceamento de classes. Por fim, o método classification_report será utilizado para a avaliação de métricas adicionais.
Dicionário de Variáveis

- ***V1, V2, …, V28:*** Componentes principais obtidos através da transformação PCA. Estes são valores numéricos que representam as variáveis originais após a redução de dimensionalidade com PCA.

- ***Time:*** Tempo, em segundos, decorrido entre cada transação e a primeira transação no dataset.

- ***Amount:*** Valor da transação. Esta variável pode ser usada em modelos de aprendizado que consideram custos sensíveis ao exemplo.

- ***Class:*** Variável de resposta, indicando se a transação é fraudulenta. Assume valor 1 em caso de fraude e 0 caso contrário.

### Versões dos Pacotes

- scikit-learn versão 1.5.2
- xgboost versão 2.1.3
- numpy 1.26.4
- pandas 2.2.3
- matplotlib 3.10.0

