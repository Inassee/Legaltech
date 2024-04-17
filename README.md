# Legaltech
Hackathon Legal Tech - ICAI/Centro Garrigues 

# Objetivo
El objetivo principal es evaluar la capacidad de un LLM para comprender preguntas reales de la prueba de acceso a la abogacía, responder de manera correcta y proporcionar una justificación que permita descartar que el acierto se ha producido por azar o por memorización. Esta evaluación aplicará a preguntas del examen de acceso a la abogacía, en sus cuatro modalidades (Civil, Penal, Administrativo, y Laboral) permitiendo concluir si este tipo de inteligencias generativas son capaces de interpretar preguntas y proponer respuestas argumentadas hasta el punto de superar con éxito la prueba de acceso. Por lo tanto, con este Hackathon aspiramos a explorar el potencial de los LLM como herramientas de apoyo en la educación y práctica legal, al mismo tiempo que identificamos áreas para su mejora.

# Examen de Acceso a la Abogacía
El contenido del examen consiste en una prueba escrita objetiva de contenido técnico-práctico con respuestas múltiples.
El programa de materias del examen se fija reglamentariamente en la Orden ministerial de convocatoria de cada examen y suele repetirse en cada convocatoria. Incluye dos bloques:

## Materias comunes al ejercicio de la profesión de la Abogacía (obligatorias)
Deontología profesional, organización y ejercicio de la profesión de la Abogacía
Cuestiones generales de la asistencia letrada y del proceso
## Materias específicas (a elegir una)
Materia civil y mercantil
Materia penal
Materia administrativa y contencioso-administrativa
Materia laboral

El sistema de evaluación del examen consta de dos partes: la primera parte evalúa el conocimiento de las materias comunes con 50 preguntas, y la segunda parte evalúa la especialidad elegida por cada aspirante de las materias específicas, con 25 preguntas. Cada pregunta tiene cuatro respuestas alternativas, de las cuales solo una es correcta.

# Metodología del Hackathon
El resultado del trabajo de los grupos será un prompt para responder a todas las preguntas o una batería de prompts (uno para la parte común y cuatro para cada una de las específicas). Es decir, cada grupo participante podrá entregar de 1 a 5 prompts. Estos prompts deben poder invocarse desde el template que se proporciona en el repositorio del proyecto y que los grupos pueden modificar libremente. La entrega del grupo debe consistir no solo en el prompt o prompts necesarios para responder a las preguntas, sino también en un conjunto de instrucciones para replicar o acceder al LLM empleado por el grupo. 

# Referencias
• En esta [URL](https://github.com/lmerchante/hackathon2024/tree/main/Preguntas%20de%20entrenamiento) se encuentran las últimas seis convocatorias del examen de acceso a la abogacía además de un fichero con algunos ejemplos de (Campuzano & AlonsoMuñumer 2024) que además proporciona una justificación a cada respuesta.
•  [Prompt](https://github.com/lmerchante/hackathon2024/blob/main/Template%20de%20entrega/prompts/prompts.json) o conjunto de prompts en un archivo de tipo json. En el repositorio de recursos se proporciona un ejemplo. 
• [Jupyter Notebook](https://github.com/lmerchante/hackathon2024/blob/main/Template%20de%20entrega/hackathon_legaltech_notebook.ipynb) para la automatización de las consultas. En el Repositorio de recursos se proporciona el template del mismo. La funcionalidad de este notebook consiste en poder aplicar los prompts entregados por los grupos y el LLM empleado al conjunto confidencial de preguntas de evaluación. Simplificando al máximo la generación de resultados que evaluará el tribunal

##### Participantes: Mónica López de Paz, Antonio Luis Gómez Arroyo, Irene Hernandez Carrera, Marta Ramos Riccitelli, Inasse Tyouss
