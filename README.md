# CFE-IA-E6

# *IMAGEN PODIO*
<img width="1366" height="768" alt="Captura de pantalla (4)" src="https://github.com/user-attachments/assets/a3c5c08d-907f-47c6-9066-c6807938700d" />
-- 
Este proyecto utiliza el dataset Titanic - Machine Learning from Disaster de Kaggle para predecir la probabilidad de supervivencia de los pasajeros en función de variables demográficas.
--
# Objetivo

Entrenar un modelo de clasificación que estime la supervivencia de un pasajero en el Titanic en base a sus características y generar un archivo de predicciones para envío a Kaggle.
--
# Datos

Variables utilizadas en el modelo:

Sex: sexo del pasajero (0 = masculino, 1 = femenino).

Age: edad del pasajero (valores faltantes fueron completados con la moda en train.csv y la mediana en test.csv).

Survived: variable objetivo (0 = no sobrevivió, 1 = sobrevivió).
--
# Pasos realizados

Carga y preprocesamiento de datos

Se cargaron los datasets train.csv y test.csv.

Se completaron valores faltantes en la variable Age.

Se eliminaron filas con valores nulos en Embarked (aunque finalmente no se usó en el modelo).

Se codificaron las variables categóricas:

Sex → {male: 0, female: 1}

Embarked → {S: 0, C: 1, Q: 2} (no utilizada finalmente).

Se aplicó StandardScaler para normalizar las variables de entrada.

Análisis exploratorio

Se realizaron gráficos de caja (boxplots) para analizar valores atípicos en la edad antes y después del filtrado.
--
# Entrenamiento del modelo KNN

Se seleccionaron como características: Sex y Age.

Se entrenó un modelo KNeighborsClassifier con k=3.

Se evaluó el rendimiento con un conjunto de validación (20%), obteniendo como métrica la exactitud (accuracy).

Predicciones y generación de submission

Se aplicó el mismo preprocesamiento al conjunto de prueba (test.csv).

El modelo generó predicciones de supervivencia para cada pasajero.

Se creó el archivo submission.csv con las columnas:

PassengerId

Survived

# Resultados

El modelo logra una exactitud aproximada de entre 0.75 - 0.80

El archivo submission.csv está listo para enviarse a Kaggle.
