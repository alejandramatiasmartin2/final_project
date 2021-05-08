# Final Project
![Ironhack logo](https://i.imgur.com/1QgrNNw.png)

## Alejandra Matías Martín

Bootcamp: Ironhack - Data Analytics Part Time Nov 2020

---


##  Resumen

Este proyecto de Machine Learning se basa en el estudio original de 2014: "A data-driven approach to predict the success of bank telemarketing", en el que los autores reaalizaron un proyecto de Minería de Datos para predecir el éxito de las llamadas de telemarketing para la venta de depósitos bancarios a largo plazo de un banco minorista portugués.


El conjunto de datos que hemos escogido, bank-additional-full.csv, se compone de 41188 ejemplos y 20 variables, ordenados por fecha (de mayo de 2008 a noviembre de 2010)

El objetivo de este proyecto es realizar un profundo análisis de las características de este conjunto de datos y escoger el mejor modelo para predecir si el cliente contratará o no un depósito a largo plazo

#### Referencias:

UCI Machine Learning Repository

[Moro et al., 2014] S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems, Elsevier, 62:22-31, June 2014


## Características del dataset
- Input variables:
# bank client data:
1 - age (numeric)
2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
5 - default: has credit in default? (categorical: 'no','yes','unknown')
6 - housing: has housing loan? (categorical: 'no','yes','unknown')
7 - loan: has personal loan? (categorical: 'no','yes','unknown')
# related with the last contact of the current campaign:
8 - contact: contact communication type (categorical: 'cellular','telephone')
9 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')
10 - day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')
11 - duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.
# other attributes:
12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
14 - previous: number of contacts performed before this campaign and for this client (numeric)
15 - poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')
# social and economic context attributes
16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)
17 - cons.price.idx: consumer price index - monthly indicator (numeric)
18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)
19 - euribor3m: euribor 3 month rate - daily indicator (numeric)
20 - nr.employed: number of employees - quarterly indicator (numeric)

Output variable (desired target):
21 - y - has the client subscribed a term deposit? (binary: 'yes','no')

## Informe de análisis exploratorio de datos: Instrucciones

Para hacer un buen análisis exploratorio, he hecho estadísticas de resumen incluyendo estadísticas descriptivas: máximo, mínimo, media, desviación estándar, percentiles, correlaciones, tipos de datos, etc.

Tr

También he hecho gráficos de visualización de datos con el fin de capturar una gran cantidad de datos de una sola vez de una manera clara y concisa (Box Plots, Bar Plots, Correlation Matrix, etc.).


## Cuadro de mando de datos de Tableau

Basándome en el análisis realizado en el informe de análisis de datos, he trazado en Tableau para corroborar las principales percepciones que he extraído de este conjunto de datos.
 Puedes acceder al dashbord [aquí.](https://public.tableau.com/profile/alejandra.mat.as.mart.n#!/vizhome/Diamondsdashboard/DiamondsDashboard?publish=yes)

### Conclusiones

- El <strong>carataje</strong> es la característica con mayor correlación con el <strong>precio</strong> del diamante: cuanto más alto sea el quilate (más pesa), más alto será el precio.
- El volumen también está muy correlacionado con el precio.
- En cuanto al <strong>color</strong>, en un principio habría pensado que los diamantes de color D (100 % incoloros), que son los mejores, tendrían el precio medio más alto. Sin embargo, los que tienen el precio medio más alto son los J y los I (menos incoloros).
- Los diamantes de mayor peso y precio son principalmente incoloros (J, I, H): 8 de los 10 diamantes de mayor peso y precio son incoloros.
	

___
### :ordenador: **Pila tecnológica**
- Python
- Pandas
- Matplotlib
- Numpy
- OneHotEncoder
- StandardScaler
- train_test_split
- KNeighborsClassifier
- DecisionTreeClassifier
- GaussianNB
- SVC
- KFold
- LogisticRegression
- Cross_val_score
- Confusion_matrix
- Accuracy_score


## :file_folder: Estructura de la carpeta
```
└── proyecto
    ├── .gitignore
    ├── README.md
    ├── data_bank_analysis.ipynb
    ├── data
    │ ├── bank-additional-full.csv
    |── feature analysis
  
    
```
	
---

## :love_letter: Contacto
> Email: <alejandramatias32@gmail.com>
> Teléfono: 626118167


