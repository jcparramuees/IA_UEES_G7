Este es el repositorio del grupo 7, para el desarrollo de actividades de laboratorio de Aprendizaje automático para la maestría en Inteligencia Aritifical de la UEES. 
Enlace a la presentaciones por video: https://drive.google.com/file/d/1QdEz-JwAnBmeuKWIntWXZh4erYeC8BLR/view?usp=sharing
1. El Contexto de los Datos
El siguiente trabajo se basa en el análisis del archivo Arduino.CSV. Este conjunto de datos contiene una captura continua de lecturas de múltiples sensores (sensor de luz, sensor de sonido, giroscopio y acelerómetro) conectados a un microcontrolador Arduino.

El objetivo es analizar este flujo de datos para entender el comportamiento del dispositivo y cómo sus sensores reaccionaban al entorno durante el período de medición.

2. Enfoque del Análisis
Aunque se capturaron múltiples lecturas, nuestro análisis se concentrará en las tres columnas más relevantes para el movimiento y la orientación:

Giroscopio: Este sensor es fundamental para entender la orientación del dispositivo en el espacio (por ejemplo, si estaba plano, de lado o en vertical).

Acelerómetro: Este sensor mide la aceleración (cambios de velocidad). Es clave para determinar si el dispositivo estaba en reposo o en movimiento (como al ser agitado o transportado).

Tiempo: Nos permite contextualizar cuándo ocurrió cada evento.

3. ¿Por qué usar Aprendizaje No Supervisado?
El gran desafío de este conjunto de datos es que, si bien tenemos miles de lecturas de sensores, no tenemos etiquetas que nos digan qué estaba haciendo el dispositivo en cada momento. Es un flujo de datos en bruto; no sabemos cuándo estaba "sobre la mesa", "en la mano de alguien" o "siendo agitado".

Aquí es donde radica la importancia de los métodos de aprendizaje no supervisado:

En lugar de entrenar un modelo con respuestas correctas (que no tenemos), usaremos algoritmos de clustering (como K-Means y DBSCAN) para que descubran automáticamente los patrones y estados ocultos en los datos.

En esencia, le pedimos a la máquina que analice todas las lecturas del giroscopio y el acelerómetro y las agrupe en "estados" coherentes (por ejemplo, "Estado 1: quieto y plano", "Estado 2: en movimiento", "Estado 3: sostenido en vertical", etc.).

Finalmente, usaremos técnicas de reducción de dimensionalidad (PCA y t-SNE) para visualizar y validar qué tan distintos y bien definidos son esos estados que hemos descubierto.
