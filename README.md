# Final Project
# Bank marketing analysis
![Ironhack logo](https://i.imgur.com/1QgrNNw.png)

## Alejandra Matías Martín

Bootcamp: Ironhack - Data Analytics Part Time Nov 2020

---


##  Resumen

Este proyecto de Machine Learning se basa en el estudio original de 2014: "A data-driven approach to predict the success of bank telemarketing", en el que los autores reaalizaron un proyecto de Minería de Datos para predecir el éxito de las llamadas de telemarketing para la venta de depósitos bancarios a largo plazo de un banco minorista portugués.


El conjunto de datos que hemos escogido, bank-additional-full.csv, se compone de 41188 ejemplos y 20 variables, ordenados por fecha (de mayo de 2008 a noviembre de 2010)

El objetivo de este proyecto es realizar un profundo análisis de las características de este conjunto de datos y escoger el mejor modelo para predecir si el cliente contratará o no un depósito a largo plazo

### Referencias:

UCI Machine Learning Repository

[Moro et al., 2014] S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems, Elsevier, 62:22-31, June 2014


## Descripción del dataset

- Input variables:

#### Datos del cliente:
- age (numeric)
- job : tipo de trabajo (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
- marital : estado civil (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
- education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
- default: tiene un crédito pendiente de pago? (categorical: 'no','yes','unknown')
- housing: tiene una hipoteca? (categorical: 'no','yes','unknown')
- loan: tiene un préstamos personal? (categorical: 'no','yes','unknown')

#### Relacionado con el último contacto de la campaña actual:
- contact: ctipo de comunicación (categorical: 'cellular','telephone')
- month: mes del año del último contacto (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')
- day_of_week: día de la semana del último contacto (categorical: 'mon','tue','wed','thu','fri')
- duration: duración del último contacto, en segundos (numérico). Nota importante: este atributo afecta en gran medida al objetivo de salida (por ejemplo, si la duración=0 entonces y='no'). Sin embargo, la duración no se conoce antes de realizar una llamada. Además, después de la finalización de la llamada y es obviamente conocido. Por lo tanto, esta entrada sólo debería incluirse con fines de referencia y debería descartarse si la intención es tener un modelo de predicción realist

#### Otros atributos:
- campaign: número de contactos realizados durante esta campaña y para este cliente  (numeric, incluye el último contacto)
- pdays: número de días transcurridos desde que se contactó por última vez con el cliente en una campaña anterior (numeric; 999 significa que no se contactó con el cliente previamente)
- previous: número de contactos realizados antes de esta campaña y para este cliente (numeric)
- poutcome: resultado de la campaña de marketing anterior (categorical: 'failure','nonexistent','success')

#### Atributos del contexto social y económico
- emp.var.rate: tasa de variación del empleo - quarterly indicator (numeric)
- cons.price.idx: índice de precios al consumo - monthly indicator (numeric)
- cons.conf.idx: índice de confianza del consumidor - monthly indicator (numeric)
- euribor3m: euribor a 3 meses - daily indicator (numeric)
- nr.employed: número de empleados - quarterly indicator (numeric)

Output variable (desired target):
- y - ¿ha contratado el cliente un depósito a plazo? (binary: 'yes','no')

## Informe de análisis exploratorio de datos

Para hacer un buen análisis exploratorio, he hecho estadísticas de resumen incluyendo estadísticas descriptivas: máximo, mínimo, media, desviación estándar, percentiles, correlaciones, tipos de datos, etc.


También he hecho gráficos de visualización de datos con el fin de capturar una gran cantidad de datos de una sola vez de una manera clara y concisa (Box Plots, Bar Plots, Correlation Matrix, etc.).


## 

Basándome en el análisis realizado en el informe de análisis de datos, he trazado en Tableau para corroborar las principales percepciones que he extraído de este conjunto de datos.
 Puedes acceder al dashbord [aquí.](https://public.tableau.com/profile/alejandra.mat.as.mart.n#!/vizhome/Diamondsdashboard/DiamondsDashboard?publish=yes)

## Conclusiones

- El <strong>carataje</strong> es la característica con mayor correlación con el <strong>precio</strong> del diamante: cuanto más alto sea el quilate (más pesa), más alto será el precio.
- El volumen también está muy correlacionado con el precio.
- En cuanto al <strong>color</strong>, en un principio habría pensado que los diamantes de color D (100 % incoloros), que son los mejores, tendrían el precio medio más alto. Sin embargo, los que tienen el precio medio más alto son los J y los I (menos incoloros).
- Los diamantes de mayor peso y precio son principalmente incoloros (J, I, H): 8 de los 10 diamantes de mayor peso y precio son incoloros.
	

___
## Technology

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


## :file_folder: Estructura del proyecto
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


