---
name: analisis-uml
description: 'Analiza diagramas UML (casos de uso, clases, etc.) escritos en texto (Mermaid, PlantUML), propone mejoras y extrae conocimiento clave para generar material de estudio.'
argument-hint: 'Indica el archivo UML o de casos de uso a analizar'
user-invocable: true
---

# Análisis de Diagramas UML y Extracción de Conocimiento

## Cuándo usar
- Revisar y mejorar diagramas UML (casos de uso, clases, secuencias) escritos en Markdown, Mermaid o texto plano.
- Extraer conceptos clave de un sistema o diagrama para estudiar.
- Buscar errores lógicos, flujos faltantes relaciones incorrectas (ej. `include` vs `extend` en casos de uso).

## Procedimiento

1. **Lectura y Análisis del Diagrama**:
   - Analiza el contexto y el contenido del diagrama proporcionado.
   - Identifica el tipo de diagrama, los actores principales, componentes y relaciones.

2. **Propuesta de Mejoras**:
   - Revisa inconsistencias lógicas o dependencias redundantes.
   - Evalúa si faltan flujos alternativos, excepciones o elementos importantes en el diseño.
   - Explica brevemente *por qué* propones los cambios y sugiere cómo modificar el diagrama.

3. **Extracción de Conocimiento (Para Estudiar)**:
   - Sintetiza los procesos o conceptos principales que representa el diagrama.
   - Lista "Puntos Clave" del sistema modelado.
   - Formula de 3 a 5 preguntas de repaso para ayudar al usuario a repasar, analizar o estudiar para una evaluación.

## Formato de Salida
- **Evaluación**: Breve resumen de la estructura actual del diagrama.
- **Mejoras**: Lista de sugerencias (y opcionalmente, la corrección del diagrama en código).
- **Material de Estudio**: Conceptos sintetizados y preguntas clave.