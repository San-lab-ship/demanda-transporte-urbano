# demanda-transporte-urbano
Predicción de demanda de transporte urbano usando ML, SQL y PySpark
# Predicción de Demanda de Transporte Urbano

## Objetivo
Predecir la demanda de pasajeros en rutas urbanas para optimizar flotas, evitando sobrecarga o rutas vacías. Este proyecto se enfoca en ciudades colombianas y considera variables como clima, horarios y eventos locales.

## Descripción del Problema
Conocer la demanda de transporte urbano permite planear rutas, asignar buses y personal, y mejorar la experiencia de los usuarios. El proyecto utiliza datos históricos de pasajeros y eventos relevantes para construir un modelo predictivo robusto.

## Arquitectura del Sistema
Se propone una arquitectura basada en:
- Extracción y limpieza de datos (SQL + PySpark)
- Ingeniería de características (lags, medias móviles, variables de eventos)
- Entrenamiento de modelos ML (Random Forest, XGBoost, LSTM)
- Visualizaciones interactivas (Plotly, Folium)

![Diagrama](arquitectura/diagrama_architectura.png)

## Metodología
1. **Carga y Exploración de Datos**
   - DataFrames: df_pasajeros, df_clima, df_eventos
   - Identificación de columnas clave, tipos de datos y fechas
2. **Limpieza y Preparación**
   - Conversión de fechas
   - Unión de datasets
   - Tratamiento de nulos
3. **Feature Engineering**
   - Variables temporales: lags, medias móviles
   - Variables de eventos (festivos, partidos, conciertos)
   - Variables climáticas
4. **Preprocesamiento**
   - Escalado de variables numéricas (StandardScaler)
   - Codificación de categóricas (OneHotEncoder)
   - ColumnTransformer para pipeline
5. **Entrenamiento y Optimización**
   - RandomForestRegressor, XGBoost y LSTM
   - Validación cruzada y RandomizedSearchCV
6. **Evaluación**
   - Métricas: RMSE, MAE, precisión de predicción
7. **Análisis de Errores**
   - Identificación de rutas o fechas con errores altos
   - Validación de robustez del modelo

## Visualizaciones
- Gráficos de demanda por hora, día y ruta
- Dashboard interactivo con predicción vs. realidad
- Link de ejemplo: `results/dashboard_interactivo.html`

## Tecnologías Utilizadas
- Python 3.10
- Pandas, NumPy
- Scikit-learn, XGBoost, PySpark
- Plotly, Folium
- Google Colab / Jupyter Notebook

## Resultados y Conclusiones
El modelo permite anticipar la demanda de pasajeros en diferentes horarios y rutas, mejorando la planificación de flotas y reduciendo costos operativos.
