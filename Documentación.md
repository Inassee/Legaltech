# 2ª Edición del Hackathon Legaltech - Comillas-Centro de Estudios Garrigues

# Documentación 

# Objetivo
El propósito principal del hackathon fue explorar el potencial de los LLM como herramientas de apoyo en la educación y práctica legal, identificando áreas de mejora y optimización. Para lograr esto, evaluamos la capacidad del modelo para interpretar preguntas del examen y proporcionar respuestas argumentadas, utilizando un modelo de lenguaje finamente ajustado (fine-tuned) con preguntas del examen.

# Metodología

## 1. Creación del dataset
Para entrenar y evaluar el modelo, construimos un dataset basado en preguntas y respuestas de antiguas convocatorias del examen de acceso a la abogacía, compuesto por 87 preguntas. 

Inicialmente, recopilamos y organizamos las preguntas y respuestas en un archivo excel, lo que nos permitió estructurar nuestros datos de manera clara. El formato incluía las siguientes columnas: prompts, categoría, pregunta, opciones de respuesta, la respuesta correcta y la justificación correspondiente. Cada prompt está diseñada para abordar una categoría particular del examen, para que el modelo genere respuestas pertinentes a la categoría específica de la pregunta (prompts.json).

## 2. Transformación del dataset
Para que el modelo de OpenAI pudiera ser entrenado, convertimos el dataset de Excel a un formato JSONL (JSON Lines), el cual es recomendado por OpenAI para el fine-tuning debido a su eficiencia y simplicidad en el procesamiento de datos, ya que cada línea en el archivo JSONL representa una interacción completa de entrada y salida, facilitando tanto el entrenamiento como el procesamiento de los datos y su carga.

Desarrollamos un script en python para automatizar esta conversión, asegurándonos de que cada interacción (pregunta y respuesta) estuviera correctamente formateada para el entrenamiento del modelo.

**Ejemplo del formato JSONL resultante (formatted_dataset_for_finetuning.jsonl):**

```json
{
    "messages": [
        {"role": "system", "content": "Basándote en la legislación administrativa vigente, analiza y elige la respuesta más adecuada a la pregunta. Indica 'Respuesta:' seguida por la letra de la opción y 'Justificación:' donde debes fundamentar tu elección usando artículos de ley o principios administrativos pertinentes, asegurándote de expresarlo todo en español."},
        {"role": "user", "content": "¿En qué momento se pueden efectuar alegaciones en un procedimiento administrativo?"},
        {"role": "user", "content": "a) Los interesados podrán solamente aducir alegaciones y aportar documentos u otros elementos de juicio en el trámite de audiencia b) Los interesados podrán, en cualquier momento del procedimiento anterior al trámite de audiencia, aducir alegaciones y aportar documentos u otros elementos de juicio c) Los interesados podrán, en cualquier momento del procedimiento posterior al trámite de audiencia, aducir alegaciones y aportar documentos u otros elementos de juicio d) Los interesados no pueden aducir alegaciones y aportar documentos u otros elementos de juicio en ningún momento del procedimiento."},
        {"role": "assistant", "content": "Respuesta: b. b: Los interesados podrán, en cualquier momento del procedimiento anterior al trámite de audiencia, aducir alegaciones y aportar documentos u otros elementos de juicio. Justificación: Artículo 76, apartados 1 y 2 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas."}
    ]
}
```

## Fine-Tuning del modelo
Utilizamos el modelo **gpt-3.5-turbo-0125** de OpenAI, con el archivo JSONL para entrenar el modelo.

## Implementación del código
### Proceso de Implementación
El script del notebook de entrega nos permite invocar el modelo con los prompts desarrollados por categoría y evaluar su rendimiento en un conjunto de preguntas, configurando la clave API de OpenAI. Se cargan los archivos JSON que contiene los prompts y las preguntas que se van a evaluar. La función de ejecución toma la prompt adecuada y una pregunta, y utiliza la API para generar una respuesta y su justificación, manejando la comunicación con el modelo previamente ajustado.

**Métricas del modelo:**
- Base model: gpt-3.5-turbo-0125
- Trained tokens: 107,889
- Epochs: 3
- Batch size: 1
- LR multiplier: 2
- Validation: No se utilizó un archivo de validación separado.

El entrenamiento comenzó con una tasa de pérdida inicial de 2.0472 (diferencia entre las respuestas predichas por el modelo y las respuestas correctas en nuestros datos de entrenamiento). A lo largo de las iteraciones y ajustes en el proceso de entrenamiento, esta tasa de pérdida se redujo a 0.8232, lo que nos indica que el modelo está aprendiendo y mejorando su precisión.

## Coste económico
El coste económico del fine-tuning del modelo fue de aproximadamente 8 euros.

# Mejoras
A pesar de resultados positivos, identificamos varias áreas de mejora:

- Ampliación del dataset para incluir más preguntas y respuestas, lo que mejoraría la capacidad del modelo para generalizar su conocimiento.
- Incorporación de un conjunto de validación: Implementar un conjunto de validación para evaluar el desempeño del modelo durante el entrenamiento, para asegurarnos que el modelo funcione bien no solo con los datos de entrenamiento sino también con datos nuevos.
- Modelo de mayor capacidad: Considerar el uso de un modelo de mayor capacidad para mejorar la precisión y el detalle de las respuestas. Sin embargo, debido a restricciones económicas, no se ha explorado esta opción.
- Recursos computacionales: Invertir en recursos computacionales adicionales para permitir entrenamientos más extensivos y con modelos más grandes, lo que podría mejorar significativamente el rendimiento del modelo.

