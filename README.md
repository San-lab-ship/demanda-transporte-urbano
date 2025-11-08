[Predecir la demanda de pasajeros en rutas urbanas - Colab.html](https://github.com/user-attachments/files/23427018/Predecir.la.demanda.de.pasajeros.en.rutas.urbanas.-.Colab.html)# prediccion-demanda-transporte-urbano
Predicción de demanda de transporte urbano usando ML, SQL y PySpark
# Predicción de Demanda de Transporte Urbano

## Objetivo
Predecir la demanda de pasajeros en rutas urbanas colombianas para optimizar la asignación de flotas, evitando tanto la sobrecarga de vehículos como los trayectos con baja ocupación.  
El modelo considera factores como condiciones climáticas, horarios, patrones históricos de viaje y eventos locales que afectan la movilidad urbana.

## Descripción del Problema
Anticipar la demanda de transporte urbano es fundamental para planificar operaciones eficientes, reducir costos y mejorar la experiencia de los usuarios.  
Este proyecto emplea datos históricos de pasajeros combinados con variables externas (clima y eventos) para construir un modelo predictivo de alta precisión, capaz de apoyar la toma de decisiones en empresas de transporte público.

## Arquitectura del Sistema
La solución se basa en un pipeline modular de analítica y machine learning que integra:

- **Extracción y limpieza de datos:** SQL + PySpark para procesamiento distribuido.  
- **Ingeniería de características:** generación de variables derivadas (lags, medias móviles, indicadores de eventos).  
- **Entrenamiento de modelos predictivos:** Random Forest, XGBoost y LSTM para estimar la demanda diaria.  
- **Evaluación y validación:** métricas RMSE, MAE y R² para medir el desempeño del modelo.  
- **Visualizaciones interactivas:** dashboards dinámicos con Plotly y mapas geoespaciales con Folium.

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

## Datos Iniciales del Proyecto
| fecha      | ruta        | pasajeros | clima   | evento |
| ---------- | ----------- | --------- | ------- | ------ |
| 2024-01-01 | Ruta Norte  | 269       | Nublado | 0      |
| 2024-01-01 | Ruta Sur    | 234       | Nublado | 0      |
| 2024-01-01 | Ruta Centro | 257       | Nublado | 0      |
| 2024-01-01 | Ruta Este   | 203       | Soleado | 0      |
| 2024-01-01 | Ruta Oeste  | 230       | Soleado | 0      |


## Visualizaciones
- Demanda Real vs Predicha (muestra de 200 días)
- Top 10 Variables Más Relevantes para la Predicción
- Tendencia Mensual de Demanda Promedio
- Mapa Interactivo de Demanda por Ruta y Zona
- Comparación de Modelos con Pipeline

<img width="1404" height="525" alt="newplot (2)" src="https://github.com/user-attachments/assets/1ea3eab5-92f9-4df6-a592-dfe5916baa6c" />

<img width="1404" height="525" alt="newplot" src="https://github.com/user-attachments/assets/7019da26-dcae-4cbe-8d42-e8fab83729eb" />

<img width="1404" height="525" alt="newplot (1)" src="https://github.com/user-attachments/assets/85335137-a728-40b1-9212-16ae46f9ec77" />

<img width="841" height="551" alt="image" src="https://github.com/user-attachments/assets/e6e34963-5f8e-4bcc-993b-8032a9100d0b" />




## Tecnologías Utilizadas
Python 3.10 ✔️ Jupyter Notebook / Google Colab ✔️ Pandas ✔️ NumPy ✔️ PySpark ✔️ SQL ✔️ Scikit-learn 
✔️ XGBoost ✔️ RandomForestRegressor ✔️ Joblib ✔️ Plotly ✔️ Folium ✔️ Draw.io ✔️ Git / GitHub

## Resultados y Conclusiones
✔️ El modelo Random Forest alcanzó un R² de 0.93, con errores promedio menores a 50 pasajeros.
✔️ Las variables más influyentes fueron: día de la semana, tendencia temporal y condiciones climáticas.
✔️ Los dashboards interactivos permiten explorar demanda por ruta, mes y clima.
✔️ El mapa Folium visualiza las zonas con mayor demanda de transporte urbano.
