
# Proyecto de Análisis de Recuperación de Oro

Este proyecto consiste en un análisis de datos para evaluar y mejorar la precisión en los cálculos de recuperación de oro en una planta de procesamiento, así como en la construcción de modelos de machine learning para predecir la recuperación en futuras operaciones.

## Descripción del Proyecto

El objetivo principal es verificar la exactitud de los cálculos de recuperación proporcionados y desarrollar modelos de machine learning que puedan predecir la recuperación de oro en distintas etapas del proceso.

## Estructura del Análisis

1. **Importación de Librerías y Datos**
   - Se cargan las librerías necesarias (`pandas`, `numpy`, `plotly`, `scipy`, `sklearn`) y se importan los datos de tres conjuntos: `data_train`, `data_test` y `data_full`.

2. **Verificación del Cálculo de Recuperación**
   - Se lleva a cabo un cálculo manual de la recuperación de oro basado en la fórmula proporcionada y se compara con los valores del conjunto de datos.
   - **Resultado**: El error absoluto medio es extremadamente bajo, lo que confirma que los cálculos de recuperación en los datos originales son precisos. Esto proporciona confianza en la calidad de los datos y en la fórmula utilizada.

3. **Análisis de Características No Disponibles**
   - Se identifican las columnas que están presentes en el conjunto de entrenamiento (`data_train`) pero ausentes en el conjunto de prueba (`data_test`). Se concluye que estas columnas corresponden a valores de salida (`output`) que solo pueden calcularse después del procesamiento, y por lo tanto, no están disponibles para la predicción inicial.

4. **Preprocesamiento de Datos**
   - Los datos se limpian y preparan, lo cual incluye el tratamiento de valores faltantes y la normalización de ciertas características. Este paso asegura que los datos estén en un formato adecuado para los modelos de machine learning.

5. **Construcción y Evaluación de Modelos**
   - Se implementan y comparan varios modelos de regresión, incluyendo:
     - **Regresión Lineal (Linear Regression)**
     - **Árboles de Decisión (DecisionTreeRegressor)**
     - **Bosque Aleatorio (RandomForestRegressor)**
   - Se realiza un ajuste de hiperparámetros con `GridSearchCV` para optimizar el desempeño de los modelos.
   - La métrica principal de evaluación es el **error absoluto medio** (MAE), lo cual permite medir la precisión de cada modelo en la predicción de la recuperación de oro.

## Resultados Principales

- **Verificación de Cálculos**: El bajo error absoluto medio en el cálculo manual de recuperación valida la fórmula y los datos originales. Esto indica que la recuperación de oro ha sido calculada de manera consistente y confiable en el conjunto de datos.
  
- **Evaluación de Modelos**:
   - **Regresión Lineal**: Proporciona una buena base, pero carece de la flexibilidad para capturar relaciones no lineales en los datos, lo cual afecta su precisión.
   - **Árbol de Decisión**: Ofrece una mejora en precisión en comparación con la regresión lineal, pero puede sobreajustarse a los datos de entrenamiento, lo cual afecta su rendimiento en el conjunto de prueba.
   - **Bosque Aleatorio**: Este modelo muestra el mejor desempeño general. Con su capacidad para reducir el sobreajuste y capturar patrones complejos, el Bosque Aleatorio logró el menor error absoluto medio, haciéndolo la opción preferida para predecir la recuperación de oro.

## Conclusiones

El análisis concluye que los cálculos de recuperación de oro en los datos originales son precisos y confiables. Además, el modelo de **Bosque Aleatorio** destaca como la mejor opción para predecir la recuperación de oro debido a su alta precisión y capacidad de generalización.

## Requisitos

- **Python 3.7+**
- Librerías: `pandas`, `numpy`, `plotly`, `scipy`, `sklearn`

## Cómo Ejecutar el Proyecto

1. Clona el repositorio.
2. Instala las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Ejecuta el notebook `projecto_10.ipynb` para reproducir el análisis y los resultados.
