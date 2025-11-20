README – Proyecto de Explicabilidad (XAI) y Análisis de Sensores Arduino

Descripción del Proyecto
Este proyecto implementa un modelo de Machine Learning aplicado al análisis de datos reales obtenidos desde sensores Arduino (ruido, luz, acelerómetro y giroscopio). El objetivo principal es:

Detectar anomalías en los sensores.

Evaluar la transparencia mediante técnicas de Explicabilidad (XAI).

Identificar posibles sesgos del entorno (baja luz, ruido alto).

Aplicar técnicas de mitigación y evaluación ética.

Este repositorio contiene los notebooks, visualizaciones, métricas, código de entrenamiento y experimentos de explicabilidad desarrollados durante el curso de Modelos Avanzados en Análisis de Datos.
** Estructura del Repositorio**

📁 Proyecto_XAI_Arduino/ │ ├── data/ │ ├── ArduinoSensorValues.csv │ ├── notebooks/ │ ├── Analisis_Sensores_Arduino_XAI.ipynb │ ├── SHAP_LIME_Explicabilidad.ipynb │ ├── Sesgos_y_Fairness.ipynb │ ├── images/ │ ├── shap_summary.png │ ├── lime_example.png │ ├── correlacion_sensores.png │ ├── matriz_confusion.png │ ├── README.md └── reporte/ ├── Informe_Final_XAI.pdf └── Presentación.pptx

Metodología del Proyecto
El flujo metodológico seguido es:

Carga y revisión inicial del dataset
Lectura de 113 registros provenientes del Arduino.

Limpieza de valores nulos.

Análisis exploratorio de sensores: ruido, luz, aceleración y gravedad.

Ingeniería de etiquetas
Se generó una variable objetivo Is_Anomaly utilizando el método IQR aplicado a la columna decibles.

Definición de “atributos sensibles”
Para replicar metodologías de fairness, se crearon grupos de riesgo:

grupo_luz_baja → condiciones de baja iluminación

grupo_ruido_alto → condiciones de alto ruido

Entrenamiento del modelo supervisado
Modelo seleccionado: Random Forest (200 árboles) Justificación:

Robusto al ruido

Maneja no linealidades

Buen rendimiento en sensores

Explicabilidad (XAI)
Se implementaron dos técnicas:

✔ SHAP

BeeSwarm global

Importancia media de variables

Explicación del impacto de cada característica

✔ LIME

Explicaciones individuales

Identificación de variables determinantes en un caso específico

Evaluación de sesgos
Se midió la tasa de anomalías predichas por:

baja luz vs luz normal

alto ruido vs ruido normal

Mitigación de sesgo
Eliminación de variables sensibles

Fairlearn (Demographic Parity con Logistic Regression)

Comparación antes/después
