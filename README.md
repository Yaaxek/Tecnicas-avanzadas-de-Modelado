# Regresión Lineal - Técnicas avanzadas de modelado

Este cuaderno de Jupyter aborda un proyecto de **evaluación inmobiliaria** utilizando técnicas de regresión lineal y machine learning. A lo largo del proyecto, se exploran y aplican diversas herramientas y conceptos clave para la construcción y evaluación de modelos predictivos.

## Puntos clave cubiertos:

*   **Exploración y Análisis Preliminar de Datos**: Se inicia con la carga de un dataset inmobiliario (`dataset.csv`) que incluye variables como `Valor` (precio en USD), `Área` (en m²), `Dist_Playa` (distancia a la playa en km) y `Dist_Farmacia` (distancia a la farmacia más cercana en km). Se realizan análisis descriptivos, se visualizan las distribuciones de las variables (usando box plots y distribuciones de frecuencia) y se calcula la matriz de correlación entre ellas.

*   **Transformación de Datos**: Se explica la importancia de la **distribución normal** en el modelado paramétrico y se aplica una **transformación logarítmica** a las variables para mejorar la linealidad de las relaciones y la distribución de la variable dependiente. Se verifica la relación lineal de las variables transformadas mediante gráficos de dispersión.

*   **Preparación de Datos para el Modelado**: Se dividen los datos en conjuntos de entrenamiento y prueba (80/20) utilizando `train_test_split` de `scikit-learn`, preparando las variables explicativas (X) y la variable dependiente (y).

*   **Estimación y Evaluación del Modelo Lineal con `statsmodels`**:
    *   Se estima un modelo de regresión lineal utilizando la librería `statsmodels`. Se analiza el `summary()` del modelo para evaluar métricas clave como el **coeficiente de determinación (R²)**, el **F-statistic** (para la significancia conjunta de los parámetros) y los **P-valores** de los coeficientes individuales.
    *   Se identifica y se modifica el modelo, eliminando variables no significativas (como `Dist_Farmacia`), para obtener un ajuste más robusto.

*   **Estimación del Modelo Lineal con `scikit-learn`**:
    *   Se implementa el modelo de regresión lineal utilizando `LinearRegression` de `scikit-learn` con el conjunto de variables explicativas refinado.
    *   Se obtiene el **coeficiente de determinación (R²)** tanto para los datos de entrenamiento como para las previsiones en los datos de prueba, permitiendo una evaluación del rendimiento predictivo del modelo.

*   **Generación de Previsiones Puntuales y Simulador**: Se demuestra cómo generar predicciones puntuales para nuevas entradas de datos y cómo **invertir la transformación logarítmica** (`np.exp`) para obtener el valor estimado en la escala original (USD). Se construye un **simulador simple** para facilitar la predicción de precios de inmuebles basados en nuevas áreas y distancias a la playa.

*   **Interpretación de Coeficientes**: Se detallan los métodos para obtener el **intercepto** y los **coeficientes de regresión** del modelo. Se ofrece una interpretación profunda de estos coeficientes en el contexto de un modelo log-lineal, explicando cómo los cambios porcentuales en las variables explicativas (Área y Distancia a la Playa) impactan el precio del inmueble.

*   **Análisis Gráfico de Resultados**: Se visualizan los resultados del modelo mediante un gráfico de dispersión de valores previstos vs. valores reales y la distribución de frecuencias de los residuos, para evaluar la bondad del ajuste y la calidad de las predicciones.

En resumen, este cuaderno proporciona una guía práctica y detallada sobre cómo construir, evaluar e interpretar un modelo de regresión lineal para la predicción de precios de inmuebles, cubriendo desde la exploración inicial de datos hasta el análisis avanzado de resultados.
