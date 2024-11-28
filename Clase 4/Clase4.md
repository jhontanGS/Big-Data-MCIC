# Informe de Resultados del Modelo de Clasificación

Este informe presenta los resultados obtenidos al realizar varias pruebas para mejorar la precisión de un modelo de clasificación de imágenes (MNIST) basado en redes neuronales convolucionales (CNN).

## Cambios Realizados y Resultados Obtenidos

### 1. Cambio en el Número de Filtros

**Objetivo:** Aumentar la capacidad del modelo al agregar más filtros en las capas convolucionales.

**Cambio realizado:**
- Primer capa convolucional: Se cambió de 6 filtros a 16 filtros.
- Segunda capa convolucional: Se cambió de 16 filtros a 32 filtros.

**Resultados:** Aunque el aumento de filtros permitió que el modelo capture características más complejas, no se observó una mejora significativa en la precisión ni en la reducción de la pérdida, lo que sugiere que estos cambios no fueron lo suficientemente efectivos para resolver el problema.

### 2. Cambio en el Tamaño del Kernel

**Objetivo:** Aumentar el tamaño del kernel para capturar patrones más grandes y complejos en las imágenes.

**Cambio realizado:**
- Se cambió el tamaño del kernel de 5x5 a 3x3 en ambas capas convolucionales.

**Resultados:** Aumentar el tamaño del kernel permitió al modelo captar características a mayor escala, pero no se observó un cambio significativo en la precisión o en el comportamiento del loss. Sin embargo, este ajuste podría mejorar el modelado de características espaciales de las imágenes.

### 3. Cambio de la Función de Activación

**Objetivo:** Mejorar la capacidad del modelo para aprender patrones no lineales al cambiar la función de activación.

**Cambio realizado:**
- Se cambió la función de activación de tanh a relu en todas las capas ocultas.

**Resultados:** La función de activación relu permitió que el modelo aprendiera de manera más eficiente y no se viera afectado por el problema del gradiente desvanecido que a veces ocurre con tanh.

### 4. Evaluación de la Precisión y el Loss con Épocas Diferentes

**Con 10 épocas:** El loss alcanzó 0.3261.

**Con 22 épocas (inicio del sobreajuste):** El loss alcanzó 0.3256, y comenzó a aumentar a medida que el modelo pasó más tiempo entrenando, lo que indica que el modelo empezó a sobreajustarse a los datos de entrenamiento.

**Conclusión:** A partir de las 22 épocas, el modelo parece comenzar a memorizar los datos, lo que genera un aumento en el loss en lugar de una mejora. Es un indicio claro de que se está produciendo sobreajuste (overfitting).

**Con 21 épocas (número óptimo de épocas):** El modelo parece estar en su punto óptimo con 21 épocas de entrenamiento. Esto sugiere que esta es la cantidad de
