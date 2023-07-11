# Classificacao_de_Saude_Fetal
Projeto de Aprendizado de Máquina na Saúde: Classificação de Saúde Fetal


## Problema
A mortalidade infantil tem sido um problema contínuo por muitas décadas nos sistemas de saúde ao redor do mundo.

O número total de óbitos fetais no Brasil entre 2015 e 2020, segundo dados do DATASUS, foi de 182.612 casos, sendo que o ano de maior ocorrência foi 2015 com 32.994

Embora tenhamos desenvolvido instrumentos que podem avaliar muitos aspectos de saúde fetal, ler e interpretar dados Cardiotocografia nem sempre é possível em regiões que falta um obstetra especialista.

Com isso, o estudo desenvolvido teve o objetivo de implementar técnicas de aprendizado de máquina, para analisar os dados da Cardiotocografia e classificar a saúde do feto em Saudável, Suspeito ou Patológico.

Base: https://www.kaggle.com/datasets/andrewmvd/fetal-health-classification

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

• Coleta de Dados e Montagem da Base
    • Importação da base de dados, gerados de exames do Cardiotocografia.
    • Balanceamento da classes
    
• Analise de Dados
    • Descobrir as melhores features que influenciam para gerar uma melhor classificação
    • Montagem de gráficos para analisar padrões
    • Possíveis tratamentos de dados
    
• Desenvolvimento dos modelos
    • Support Vector Machine(SVM) , XGBoost e LGBMClassifier
    • Separação 75% Base para treino e 25% teste

