# Classificacao_de_Saude_Fetal
Projeto de Aprendizado de Máquina na Saúde: Classificação de Saúde Fetal

## Problema
A mortalidade infantil tem sido um problema contínuo por muitas décadas nos sistemas de saúde ao redor do mundo.

O número total de óbitos fetais no Brasil entre 2015 e 2020, segundo dados do DATASUS, foi de 182.612 casos, sendo que o ano de maior ocorrência foi 2015 com 32.994

Embora tenhamos desenvolvido instrumentos que podem avaliar muitos aspectos de saúde fetal, ler e interpretar dados Cardiotocografia nem sempre é possível em regiões que falta um obstetra especialista.

## Objetivo
O estudo desenvolvido teve o objetivo de implementar técnicas de aprendizado de máquina, para analisar os dados da Cardiotocografia e classificar a saúde do feto em Saudável, Suspeito ou Patológico.

## Base De Dados

Nesse estudo utilizou base de dados de dados do Sisporto, no qual é sistema que armazena registros de exames cardiotocografia. O objetivo primário da base é servir para estudo, no qual possui 2126 registros de informações coletadas de 13 centros Europeus e um Australiano.

A base está disponível no site Kaggle, no qual é um dos principais repositórios de dados voltados para ciência de dados e aprendizado de máquina. Abaixo o link para acessar a base:

https://www.kaggle.com/datasets/andrewmvd/fetal-health-classification
Acessado em: 04/07/2023 19:50

### Variáveis de estudo

A base de dados do presente estudo contém 22 atributos, sendo 1 atributo classe. Com o objetivo de analisar descobrir quais variáveis gerados do exame mais impactam no resultado da classificação de saúde do feto. Os atributos são:

1)	Baseline Fetal - Frequência cardíaca fetal
2)	Accelerations – Aceleração cardíaca
3)	Fetal_movement – Movimento fetal por segundo
4)	Uterine_contractions - Número de contrações uterinas por segundo
5)	light_decelerations – Número de luzes desaceleração
6)	severe_decelerations – Desaceleração cardíaca por segundo
7)	prolongued_decelerations – Desaceleração cardíaca prolongada por segundo
8)	abnormal_short_term_variability - Porcentagem de tempo com variabilidade anormal de curto prazo
9)	mean_value_of_short_term_variability - Valor médio da variabilidade de curto prazo
10)	percentage_of_time_with_abnormal_long_term_variability - Porcentagem de tempo com variabilidade anormal de longo prazo
11)	mean_value_of_long_term_variability - Valor médio da variabilidade de longo prazo
12)	histogram_width - Largura do histograma feito com todos os valores de um registro
13)	histogram_min - Valor mínimo do histograma
14)	histogram_max - Valor máximo do histograma
15)	histogram_number_of_peaks - Número de picos no histograma do exame
16)	histogram_number_of_zeroes - Número de zeros no histograma do exame
17)	histogram_mode – Moda histograma
18)	histogram_mean - Media do histograma
19)	histogram_median – Mediana do histograma
20)	histogram_variance – Variância do histograma    
21)	histogram_tendency - Tendência do histograma
22)	fetal_health – Classificação Fetal 1-Saudável, 2-Suspeito ou 3-Patológico.

## Metodologia

**Coleta de Dados e Montagem da Base** <br />  
    • Importação da base de dados, gerados de exames do Cardiotocografia. <br />   
    
**Analise de Dados** <br />  
    • Descobrir as melhores features que influenciam para gerar uma melhor classificação <br />
    • Montagem de gráficos para analisar padrões <br />
    • Possíveis tratamentos de dados <br />
    
**Desenvolvimento dos modelos** <br /> 
    • Separação 75% Base para treino e 25% teste <br />
    • Balanceamento da classes  (Smote)  <br />
    • KNN, Decision Tree Random Forest, LGBMClassifier e LazyClassifier <br />

### Softwares utilizados

O estudo realizado foi desenvolvido na plataforma do Google Colab, no qual os experimentos foram utilizados a linguagem de programação Python, na versão 3.10.12. <br />  

Através do da linguagem Python, foram aplicadas as bibliotecas abaixo: <br />  
Numpy - Utilizada para realizar funções matemáticas. <br />  
Pandas - Realizou a manipulação e análise dos dados. <br />  
Seaborn e Matplotlib - Manipulada para visualização dos dados, desenvolvimento de gráficos e histogramas. <br />  
Imblearn – Biblioteca utilizada para realizar balanceamento da base de dados. <br />  
Scikit-learn - Aplicado para o desenvolvimento dos modelos de classificações. <br />  


### Metricas de Avaliação

Precisão: Mede a proporção de exemplos positivos que foram corretamente classificados como positivos em relação ao total de exemplos classificados como positivos. <br /> 
Precisão = Verdadeiros Positivos / (Verdadeiros Positivos + Falsos Positivos)

Acurácia: a mede a proporção de exemplos corretamente classificados em relação ao total de exemplos no conjunto de dados.<br /> 
Acurácia = (Verdadeiros Positivos + Verdadeiros Negativos) / (Total de Exemplos)

Sensibilidade(Recall) = A capacidade do modelo de identificar corretamente os casos positivos.<br /> 
Recall = Verdadeiros Positivos / (Verdadeiros Positivos + Falsos Negativos)

## Resultados

### Analisando a Base de dados, se mostrou desbalanceada, sendo:<br /> 
Saúdavel: 77.8%<br /> 
Suspeito: 13.8%<br /> 
Patologico: 8.2%<br /> 

![image](https://github.com/Matheusveloso/Classificacao_de_Saude_Fetal/assets/51542434/4cfa13bf-284f-48f6-9e13-68a3149860dd)

Com isso, foi necessário realizar um balanceamento das classes, na base de treinamento.

### Variaveis selecionadas para o modelo:

Através da matriz de correlação foram selecionadas os atributos com correlação maior que 0.3, sendo elas:<br />

accelerations<br />
prolongued_decelerations<br />	
abnormal_short_term_variability<br />	
percentage_of_time_with_abnormal_long_term_variability<br />	
histogram_mode<br />	
histogram_mean<br />	
histogram_median<br />	
histogram_variance<br />
fetal_health<br />


### Modelo Mais Competitivo:<br />

Entre os Modelos de classificação utilizados o LGBMClassifier se mostrou mais competitivo, visto que obteve melhores números nas principais metricas de avaliação: Acurácia, Precisão e Sensibilidade. <br />

![image](https://github.com/Matheusveloso/Classificacao_de_Saude_Fetal/assets/51542434/5d91423d-18c3-4c36-97ab-abd02ca9af7e)

![image](https://github.com/Matheusveloso/Classificacao_de_Saude_Fetal/assets/51542434/a353dc40-af97-4f0a-b4c9-348b63fe351e)


## Conclusão :<br />

Entre os Modelos de classificação utilizados o LGBMClassifier se mostrou mais competitivo, visto que obteve melhores números nas principais metricas de avaliação: Acurácia, Precisão e Sensibilidade.<br />

Visto os resultados, o uso de aprendizado de máquina para classificar a saúde fetal mostrou que é ferramenta eficiente e benéfica para apoiar especialistas em saúde.<br />
    

    
    

