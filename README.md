# Proyecto: Análisis y Predicción de Ratings de Películas a partir de Reseñas

## Descripción general
Este proyecto desarrolla un pipeline de análisis de reseñas de películas del conjunto de datos IMDb, con el objetivo de comprender patrones de comportamiento en las calificaciones y explorar la posibilidad de predecir los ratings a partir del texto de las reseñas.

El enfoque principal combina **análisis exploratorio de datos (EDA)**, **limpieza**, **normalización** y **visualización estadística**, seguido de un esquema base de modelado supervisado. El pipeline permite entender cómo se distribuyen las opiniones a lo largo del tiempo, por película y por tipo de usuario, estableciendo el terreno para incorporar modelos más complejos en fases posteriores.

---

## Objetivos del análisis
- Analizar la relación entre reseñas, años de lanzamiento y popularidad de las películas.  
- Explorar la distribución de ratings y su comportamiento a lo largo del tiempo.  
- Identificar sesgos, duplicados o inconsistencias en los datos.  
- Establecer una base para modelos predictivos de rating.  

---

## Librerías utilizadas

| Propósito | Librerías |
|------------|------------|
| Manipulación de datos | pandas, numpy |
| Visualización | matplotlib, seaborn |
| Modelado y persistencia | scikit-learn, joblib |
| Conectividad y almacenamiento | sqlite3 |
| Utilidades | time, os, re |

---

## Flujo general del proyecto

### 1. Carga y validación de datos
Se cargan las reseñas desde un archivo TSV (`imdb_reviews.tsv`) especificando tipos de datos como `votes` y `rating`.  
Se eliminan duplicados y se validan columnas nulas o inconsistentes.  

### 2. Análisis exploratorio (EDA)
Se realizan análisis y gráficos para comprender la estructura del dataset:
- Cantidad de películas por año (`start_year`).
- Número de reseñas por película.
- Distribución de calificaciones en los conjuntos de entrenamiento y prueba.
- Gráficos de densidad (KDE) y barras para identificar sesgos en las puntuaciones.
- Revisión de la relación entre popularidad y cantidad de reseñas.

Estos análisis permiten visualizar tendencias como el aumento de reseñas en años recientes y la concentración de calificaciones en ciertos valores.

### 3. Preparación y segmentación
El dataset se divide en subconjuntos de entrenamiento y prueba (`ds_part`), garantizando que todas las categorías de rating estén representadas en ambos.  
Se estandarizan los tipos de variables y se generan estructuras de apoyo para modelado futuro.

### 4. Modelado base
Se plantea un esquema inicial para entrenar modelos predictivos a partir de variables numéricas y categóricas.  
Aunque el enfoque principal del proyecto es el análisis exploratorio, se sientan las bases para integrar algoritmos clásicos de clasificación o regresión sobre los ratings.

### 5. Persistencia y exportación
Los datos procesados se almacenan en una base SQLite y se habilita la exportación de modelos y métricas con `joblib` para integraciones posteriores.

---

## Resultados principales

- Se identificó un crecimiento sostenido en la cantidad de reseñas en los últimos años.  
- La mayoría de las películas concentran pocas reseñas, mientras que unas pocas acumulan la mayoría.  
- Los ratings presentan una distribución sesgada hacia valores altos (7–10), lo que sugiere sesgo positivo en las reseñas públicas.  
- El análisis confirma que los ratings extremos reflejan opiniones más homogéneas en el texto, lo que facilita la predicción futura.  

---





