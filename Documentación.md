# 2ª Edición del Hackathon Legaltech - Comillas-Centro de Estudios Garrigues

# Documentación 

## Fine-Tuning del Modelo GPT-3.5 Turbo

## Resumen del proyecto
Se llevó a cabo el fine-tuning del modelo GPT-3.5 Turbo de OpenAI para optimizar su rendimiento en la interpretación y respuesta a preguntas legales específicas basadas en la legislación española actual. El objetivo era desarrollar un modelo capaz de seleccionar la respuesta correcta a preguntas de múltiple elección y proporcionar justificaciones detalladas basadas en leyes y principios jurídicos aplicables.

Estructura del dataset
El dataset utilizado para el entrenamiento y validación estaba estructurado en formato CSV, con columnas detalladas que incluyen: prompt, categoría de la pregunta, el texto de la pregunta, opciones de respuesta (a, b, c, d), la respuesta correcta y una justificación legal para la respuesta. Este formato fue diseñado para imitar la interacción natural en el sistema de chat de OpenAI,

# Formato de entrenamiento:

```
{
  "messages": [
    {"role": "system", "content": "Instrucción específica relacionada con el área legal de la pregunta."},
    {"role": "user", "content": "Pregunta formulada con opciones múltiples."},
    {"role": "assistant", "content": "Respuesta seleccionada y justificación basada en referencias legales específicas."}
  ]
}
```

# Proceso de Fine-Tuning
El modelo fue afinado utilizando un batch size de 2 y un total de 3 epochs. La pérdida de entrenamiento registrada fue de 0.8232, lo que indica un ajuste moderado del modelo a los datos proporcionados. A pesar de que se observaron mejoras, el proceso se limitó a tres epochs debido a restricciones presupuestarias.

# Implementación en notebook
Simplemente se necesita ejecutar cada celda del notebook para interactuar con el modelo y obtener respuestas a las preguntas legales presentadas. Se tiene que configurar el entorno antes de ejecutar el modelo, incluyendo la configuración de la clave API de OpenAI mediante el comando en el terminal actual: 

```
setx OPENAI_API_KEY "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" 
```

El modelo produce respuestas seleccionando la opción correcta de múltiples opciones y proporcionando una justificación que se puede ver en un archivo.txt. 
