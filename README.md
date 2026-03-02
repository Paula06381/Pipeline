# Pipeline
##Descripción general

Este proyecto desarrolla un modelo de clasificación supervisada para la detección de fraude en transacciones con tarjeta de crédito.
Se utiliza el conjunto de datos Credit Card Fraud Detection, que contiene transacciones etiquetadas como fraudulentas o legítimas.

El objetivo principal es construir un pipeline de Machine Learning que automatice el proceso de transformación de datos, estandarización y entrenamiento de un modelo de regresión logística.

## Objetivo
Analizar la distribución de la variable objetivo (fraude vs no fraude).
Explorar la variable Amount (monto de la transacción).
Implementar una transformación logarítmica para reducir la asimetría del monto.

## Metodología
### Carga y exploración inicial de datos
-Se cargó el archivo creditcard.csv y se verificó la dimensión del conjunto de datos.
-Se analizó la proporción de la variable objetivo (Class), evidenciando un fuerte desbalance entre transacciones normales y fraudulentas.

### Análisis exploratorio
- Se graficó la distribución de la variable Amount para observar su comportamiento y posible asimetría.

### Transformación de datos
- Se aplicó una transformación logarítmica a la variable Amount mediante un FunctionTransformer, con el fin de estabilizar la varianza y reducir el efecto de valores extremos.

### Preprocesamiento
- Se utilizó un ColumnTransformer para aplicar estandarización (StandardScaler) a todas las variables numéricas.

### Construcción del pipeline
- Se integraron los siguientes pasos en un Pipeline:
- Transformación logarítmica del monto.
- Escalamiento de variables numéricas.
- Modelo de clasificación con regresión logística.

## Resultados

- El dataset presenta un alto desbalance, con una proporción muy baja de fraudes respecto al total de transacciones.
- La transformación logarítmica mejoró la distribución de la variable Amount.
- El uso de ponderación de clases permitió mejorar la detección de la clase minoritaria (fraude).

## Conclusiones

- La implementación de un pipeline estructurado facilita la automatización del flujo de trabajo en Machine Learning, garantizando coherencia entre el entrenamiento y la predicción.
- El manejo del desbalance de clases y la correcta transformación de variables son aspectos fundamentales en problemas de detección de fraude, donde la clase positiva es minoritaria pero crítica.
