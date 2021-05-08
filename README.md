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

He comprobado que no había valores nulos


Este dataset está desequilibrado, hay mucha más gente que no se ha suscrito al préstamo:
yes (11,26 %)
no (88,73 %)
Para solucionar este problema, se procedió a realizar un Oversampling

Análisis de las variables:

- AGE: La mayoría de clientes está entre los 25 y los 55, media (40 años). Esta variable tiene outliers pero el máximo es 98, que es una edad que pertenece a una muestra representativa de la población en general (no es como si tuviésemos un máximo de 150 años, ya que esto es imposible y se trataría de un error)
Por tanto no quitamos outliers para que el modelo sea lo más representativo de la realidad posible
- EDUCATION: La gente 'illiterate' es la que tiene mayor proporción de yes VS no
Pero al ser tan pocos, vamos a fijarnos mejor en el dato del resto y vemos la tendencia de que a más estudios, más gente se suscribe al préstamo
- MARITAL: Más de la mitad de los clientes están casados (60 %), pero vemos que los que están solteros se han subscrito al préstamo en mayor proporción que el resto (14 % contratan)
- DEFAULT: Esta variable no nos aporta información relevante ya que apenas hay gente en situación de default y no se ve un comportamiento similar entre el 'no' y el 'unknown'
- HOUSING: No hay casi diferencia en la tendencia de las personas con hipoteca o a la hora de suscribirse a un depósito
- LOAN: La mayoría de los clientes no tiene un préstamos personal (82,42 %)
- JOB: Para intentar reducir el número de unknowns voy a poner que aquellas personas mayores de 66 años están retiradas (edad legal de jubilación en portugal)
Se impacta en mayor medida a personas que trabajan de admin (1352 yes), blue-collar (638) y technician (730) para la promoción de la contratación del préstamo
Es interesante ver que contratan en mayor proporción el préstamo aquellas personas que son estudiantes, retirados, desempleados y admin así que para futuras campañas sería interesante prestarles especial atención 
- CONTACT: Se producen más impactos a través de móvil que de teléfono fijo y hay una mayor proporción de personas que se suscriben al préstamo vía móvil así que funciona mejor este tipo de canal
- MONTH: Es interesante ver que mayo ha sido el mes con mayor captación. A los que se impactó en mayo, junio, julio y agosto (verano) tienen una mayor proporción de no suscritores (90 % aprox), en cambio a los que se impactó en septiembre y octubre mejora el ratio
- DAY_OF_WEEK: No hay mucha diferencia entre los días de la semana. Los lunes son los días que menos proporción de suscripciones tienen y los jueves los que más
- DURATION: Como nos pone en la descripción del dataset, este atributo afecta en gran medida al objetivo de salida. Sin embargo, la duración no se conoce antes de realizar una llamada. Además, después de la finalización de la llamada y ya se conoce. Por lo tanto, la excluiremos de nuestro modelo de predicción.
- CAMPAIGN: Al igual que la edad, esta variable tiene muchos outliers pero pueden ser importantes así que no quitaremos filas sino que lo agruparemos por grupos.
- PREVIOUS: A la mayoría de clientes no se les impactó antes de esta campaña
- PDAYS: Relacionado con la variable anterior, a la mayoría de clientes no se les impactó antes de esta campaña
- POUTCOME: los clientes que contrataron con la anterior campaña han contratado en esta en mayor proporción que el resto de clientes (65 %)

Herramientas utilizadas:
OneHotEncodeer
StandardScaler
Oversampling
TrainTestSplit
Cross-validation
Confusion matrix

## Conclusiones

Tras comporbar el performance de diferentes modelos, he comprobado que el algoritmo que mejor funciona es el Decission tree classifier:
Prediction accuracy=93.0 %
Cross Validation=0.9261236104569861
La matriz de confusión nos indica que nuestro modelo predijo correctamente 6381 no abonados (0), 7186 abonados (1) con 13567 predicciones correctas en total y tuvimos 1053 predicciones incorrectas en total.
	

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


