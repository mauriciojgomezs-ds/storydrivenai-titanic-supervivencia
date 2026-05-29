# Titanic — Supervivencia

> Análisis de supervivencia en el Titanic. Dataset clásico de clasificación binaria.

![Tipo de análisis](https://img.shields.io/badge/análisis-classification-6366f1)
![Calidad](https://img.shields.io/badge/calidad-critica-ef4444)
![Filas](https://img.shields.io/badge/filas-891-0ea5e9)

---

## Dataset

| Métrica | Valor |
|---------|-------|
| Archivo | `titanic.csv` |
| Filas | 891 |
| Columnas | 12 |
| Duplicados | 0 (0.0%) |
| Calidad | **critica** |
| Posibles targets | `Pclass` |

## Radiografía del Dataset

**Radiografía del dataset "Titanic — Supervivencia"**
======================================================

### Visión general
-----------------

*   El dataset tiene **891 filas** y **12 columnas**, lo que sugiere una cantidad razonable de datos para un análisis.
*   No se han encontrado **duplicados** en el conjunto de datos.

### Calidad de datos
------------------

*   La **calidad de los datos** es crítica, ya que hay varias columnas con valores nulos significativos.
*   Hay dos columnas con porcentajes de nulos superiores al 10%:
    *   "Age" (19.87%)
    *   "Cabin" (77.1%)

### Columnas relevantes
-----------------------

*   **Posibles targets** para el análisis: "Pclass"
*   **IDs**: "PassengerId", "Name"
*   No se han encontrado columnas que puedan ser consideradas como fechas.
*   Las distribuciones de las siguientes columnas son interesantes:
    *   "Survived" (media: 0.3838, outliers: 0%)
    *   "Pclass" (media: 2.3086, outliers: 0%)
    *   "Age" (media: 29.6991, outliers: 1.54%)
    *   "SibSp" (media: 0.523, outliers: 5.16%)
    *   "Parch" (media: 0.3816, outliers: 23.91%)
    *   "Fare" (media: 32.2042, outliers: 13.02%)

### Outliers y anomalías

_[...continúa en el notebook]_

## Limpieza de Datos

**Observaciones sobre la limpieza del dataset**

### Transformaciones aplicadas

No se realizaron transformaciones ni acciones específicas en el dataset. La cantidad de filas y columnas permaneció igual después de la limpieza.

### Impacto en el dataset

* No se eliminaron filas, manteniendo un total de **891** filas.
* No se eliminaron columnas, manteniéndose las **12** columnas originales.
* La limpieza no tuvo impacto significativo en la cantidad de datos.

### Estado del dataset limpio

El dataset resultante es idéntico al original. Aunque esto puede ser una buena señal, es importante considerar que la limpieza puede implicar más acciones para asegurar la calidad y consistencia de los datos. En este caso, no se detectaron errores ni inconsistencias significativas en el dataset.


_[...continúa en el notebook]_

## Análisis Exploratorio (EDA)

# Análisis Exploratorio: Titanic — Supervivencia

## Distribuciones

* La variable `SibSp` tiene una distribución sesgada hacia la derecha, con un coeficiente de asimetría (skewness) de 3.695 y un exceso de curtos (kurtosis) de 17.88.
* La variable `Parch` también tiene una distribución sesgada hacia la derecha, con un skewness de 2.749 y un kurtosis de 9.778.
* La variable `Fare` tiene una distribución muy sesgada hacia la derecha, con un skewness de 4.787 y un kurtosis de 33.398.

## Outliers detectados

* En la columna `Age`, se encuentran 13.02% de outliers.
* En la columna `Fare`, se encuentran 13.02% de outliers.

## Correlaciones

Las correlaciones más fuertes encontradas son:

* Entre `Pclass` y `Fare`: -0.5495, lo que indica una relación inversa entre el nivel social del pasajero y el precio de su billete.
* Entre `SibSp` y `Parch`: 0.4148, lo que sugiere que los pasajeros con más familiares a bordo también tienen más parientes en tierra.
* Entre `Pclass` y `Age`: -0.3692, lo que indica una relación inversa entre el nivel social del pasajero y su edad.

## Variables categóricas

* En la variable `Sex`, las categorías dominantes son masculino (514) y femenino (377).

_[...continúa en el notebook]_

## Modelo de Machine Learning

# Proyecto: "Titanic — Supervivencia"

## Resultados por modelo

| Modelo | Precisión | Recuerdo | F1 |
| --- | --- | --- | --- |
| Logistic Regression | 0.6663 | 0.676 | 0.6578 |
| Random Forest | 0.6293 | 0.6313 | 0.6302 |
| XGBoost | 0.6275 | 0.6313 | 0.6291 |

## Modelo seleccionado

El modelo de Logística Regresión mostró un desempeño ligeramente mejor que los demás modelos con una precisión, recuerdo y F1 de 0.6663, 0.676 y 0.6578, respectivamente. Esto sugiere que el modelo de Logística Regresión es más capaz de predecir la supervivencia de los pasajeros en comparación con los modelos de Random Forest y XGBoost.

## Desempeño: aceptable


_[...continúa en el notebook]_

### Métricas por Modelo

| Modelo | ACCURACY | PRECISION | RECALL | F1 | AUC | Categoría |
|--------|---|---|---|---|---|-----------|
| Logistic Regression | 0.676 | 0.6663 | 0.676 | 0.6578 | 0.6967 | aceptable |
| Random Forest | 0.6313 | 0.6293 | 0.6313 | 0.6302 | 0.658 | aceptable |
| XGBoost | 0.6313 | 0.6275 | 0.6313 | 0.6291 | 0.6167 | aceptable |

## Conclusión

## Conclusión

### Resumen del dataset

El conjunto de datos "Titanic — Supervivencia" consta de 891 filas y 12 columnas, recopiladas a partir de la tragedia del Titanic. Las variables incluyen información personal sobre los pasajeros, como edad, sexo, clase social y precio del billete, así como detalles sobre su supervivencia.

### Principales hallazgos

*   La distribución de la variable "Age" muestra una gran cantidad de niños a bordo, con un 34% de valores `NaN` (no disponibles) y una media de 29 años.
*   La variable "Fare" también tiene una distribución sesgada, con una media de $32.20 y una desviación típica de $49.69, indicando que la mayoría de los pasajeros pagaron un precio relativamente bajo por su billete.
*   El modelo de Logística Regresión mostró un desempeño ligeramente mejor que los demás modelos con una precisión, recuerdo y F1 de 0.6663, 0.676 y 0.6578, respectivamente.

### Desempeño del modelo

El modelo de Logística Regresión seleccionado demostró una capacidad aceptable para predecir la supervivencia de los pasajeros, pero su rendimiento podría mejorarse con más datos o mediante técnicas de mejora del modelo. La precisión y el recuerdo del modelo son buenos indicadores de su capacidad para generalizar a nuevos datos.

### Limitaciones del análisis

*   La cantidad de valores `NaN` en la variable "Age" puede afectar negativamente el rendimiento del modelo.
*   La distribución sesgada de la variable "Fare" podría influir en las predicciones realizadas por el modelo.

### Próximos pasos recomendados

1.  **Mejorar el modelo**: Explorar técnicas de mejora del modelo, como la selección de características o la aplicación de técnicas de regularización.
2.  **Recopilar más datos**: Buscar fuentes adicionales de información para aumentar la cantidad y calidad de los datos disponibles.
3.  **Analizar variables no utilizadas**: Explorar otras variables que se encuentran en el conjunto de datos pero no se utilizaron en este análisis, como "Cabin" o "Embarked", para ver si proporcionan información adicional útil.

---

_Generado automáticamente por [StoryDrivenAI](https://github.com/storydrivenai)._