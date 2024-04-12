# Paso 1 : Preparar el dataset

### Conjunto de datos de preguntas en el formato especificado (preguntas.json):
ID de la pregunta.
Categoría (común, civil_mercantil, penal, administrativa).
Texto de la pregunta.
Opciones de respuesta (A, B, C, D).
Respuesta correcta.
Justificación para la respuesta.

### Recolección y preparación de los datos:
Utiliza las convocatorias anteriores y ejemplos disponibles para crear un dataset representativo.
Texto esté limpio y sin errores de codificación.

# Paso 2: Diseño de prompts y modelados

### Desarrollo de prompts:
Crea prompts que instruyan al LLM a elegir una respuesta y proporcionar una justificación.
Según la estructura de prompts.json, diseña prompts específicos para cada categoría.

### Pruebas con modelos pre-entrenados:

# Paso 4: Implementación y testeo
### Implementación en Jupyter Notebook:
Sistema que pueda leer los prompts.json y aplicarlos a las preguntas de preguntas.json.
Asegúrarnos de que el Notebook pueda ejecutar el modelo y generar respuestas basadas en los prompts.

### Testeo:
Realiza pruebas con diferentes preguntas para verificar la precisión y la relevancia de las respuestas y justificaciones.

# Paso 5: Optimización y validación
### Optimización:
Ajusta los prompts basado en los resultados de t¡las pruebas para mejorar la claridad y eficiencia del modelo.
Buscar reducir errores como respuestas incorrectas o justificaciones irrelevantes.

### Validación cruzada:
Pruebas  con un subconjunto de preguntas que no fueron usadas durante el entrenamiento o la optimización inicial para validar la generalización del modelo.

# Paso 6: Preparación de entregables

### Documentación:
Prepararinstrucciones detalladas sobre cómo utilizar el Notebook y los prompts para replicar los resultados.
Incluyir detalles sobre cualquier dependencia o configuración necesaria.
