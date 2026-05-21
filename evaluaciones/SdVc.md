# Ingeniería del Software 2 - Sesiones de VibeCoding

> *Los materiales de la sesión están disponibles en el [repositorio de la asignatura](https://github.com/mmasias/25-26-idsw2-sdvc). Una aplicación completa de este diseño puede verse en [**pySigHor**](https://github.com/mmasias/pySigHor), un sistema construido íntegramente con este proceso, incluyendo los 19 artefactos RUP generados durante la sesión.*

## El problema de evaluar con IA en el aula

La llegada de los asistentes de código basados en IA al aula universitaria genera una tensión que la mayoría de los docentes resuelve mal: o prohíben la herramienta (inútil) o la ignoran (deshonesto) o la adoptan sin rediseñar la evaluación (peligroso).

La prohibición es inútil porque es indetectable y porque contradice la preparación para el mundo profesional. La ignorancia es deshonesta porque el alumno ya la usa y el docente lo sabe. La adopción sin rediseño es peligrosa porque convierte la evaluación en una medida de la calidad del prompt, no de la comprensión del alumno.

Hay una cuarta opción: diseñar la evaluación de forma que la IA no solo sea permitida sino requerida, y construir el instrumento de evaluación sobre lo único que la IA no puede falsificar: la comprensión.

## La arquitectura de tres fases

El diseño que se describe aquí opera en tres fases encadenadas:

**Fase 1: Requisitado previo.** Los alumnos llegan a la sesión de Ingeniería del software 2 con un proyecto de ingeniería del software 1 ya completado: modelo de dominio, casos de uso y diagrama de contexto existen antes de abrir el editor. Los artefactos del requisitado no son un prerequisito asumido: son el combustible de la sesión.

**Fase 2: Sesión de construcción.** En una sesión de trabajo (referencia: cuatro horas, sin límite superior estricto), el alumno construye un sistema funcional usando IA como herramienta principal. Todo queda en el repositorio. Todo.

**Fase 3: Examen de análisis.** En un momento posterior, el alumno responde sobre lo que construyó. No sobre lo que el sistema hace: sobre por qué tomó cada decisión, qué principios están presentes, cuáles están ausentes y qué distancia existe entre lo que describió y lo que entregó.

La cadena es deliberada. Cada fase valida la anterior.

## El primer commit como contrato

El primer artefacto que entra al repositorio es `QUE_HACE.md`. Contiene una sola frase. No describe qué gestiona el sistema: describe qué hace.

La distinción no es semántica. "Gestiona reservas de hotel" describe entidades. "Permite a un viajero encontrar y reservar habitaciones disponibles en menos de tres pasos" describe valor entregado. La capacidad de formular esa frase, antes de escribir una línea de código, diagnostica si el alumno entiende su propio proyecto.

Una vez creado en el primer commit, `QUE_HACE.md` no se modifica. Esta restricción elimina el movimiento de portería retrospectivo: el alumno no puede redefinir su sistema una vez que sabe lo que fue capaz de construir. El contrato está firmado antes de que sepa si puede cumplirlo.

## El conversation log como trazabilidad del proceso cognitivo

El segundo artefacto crítico es `conversation-log.md`. Su formato es simple:

```
## [HH:MM] Título breve de lo que se pidió

**Prompt:** lo que le dijo al AI
**Resultado:** lo que produjo
**Decisión:** qué aceptó, qué rechazó, qué modificó, y por qué
```

La restricción central: se escribe durante la sesión, no se reconstruye después.

Esta restricción convierte el log en la única evidencia real del proceso cognitivo del alumno. La decisión es el campo más importante: documentar qué se aceptó sin cuestionar, qué se rechazó y por qué, qué se modificó antes de integrar. Un alumno que acepta todo lo que produce la IA sin filtro tendrá un log que lo muestra. Un alumno que entendió cada pieza tendrá un log que también lo muestra.

En el examen posterior, el log es fuente primaria. El alumno que loggeó honestamente tiene material para analizar. El que no loggeó está respondiendo de memoria sobre horas de trabajo. La diferencia de calidad es visible sin necesidad de ningún mecanismo de detección de trampa.

## La distinción binario/gradable

Los baremos de evaluación operan en dos dimensiones con naturalezas distintas:

La dimensión **profesional** es binaria. El sistema arranca o no arranca. No "compilaría si instalas X": arranca, en el entorno del alumno, en el momento de la entrega. Lo que describe `QUE_HACE.md` es lo que el sistema hace; si no coinciden, el entregable es falso. El `conversation-log.md` fue escrito durante la sesión; si fue reconstruido después, es falso. El README lo puede leer alguien que no estuvo en la sesión; si no puede, no cumple su función.

La dimensión **académica** admite gradación. "Llegué hasta aquí" tiene valor si el análisis es bueno. La reflexión sobre la distancia entre lo descrito y lo entregado, formulada con honestidad y argumentación, es evaluable incluso si el sistema es incompleto.

Esta separación es honesta con el alumno sobre el mundo que le espera. En producción, un sistema que no arranca no existe, independientemente de la calidad del análisis que lo acompaña. En el aula, el proceso de aprendizaje tiene valor aunque el resultado sea imperfecto. Poner ambas dimensiones por escrito, con sus consecuencias, elimina la ambigüedad sobre qué se está midiendo.

## Por qué los artefactos del requisitado son el ingrediente crítico

La calidad de lo que la IA construye depende de la calidad de lo que se le describe. Esta relación no es lineal: instrucciones vagas producen código vago que el alumno no puede evaluar ni corregir porque no tiene el modelo mental para juzgarlo.

Los artefactos del requisitado son la descripción más precisa disponible del sistema. El modelo del dominio dice qué entidades existen y cómo se relacionan. Los casos de uso dicen qué hace el sistema, no qué gestiona. El diagrama de contexto describe el sistema como un conjunto de estados que solo se transitan mediante casos de uso. El prototipo describe la interacción actor-sistema paso a paso.

Un alumno que llega a la sesión con estos artefactos completos y comprendidos tiene una ventaja estructural sobre uno que llega con artefactos decorativos. La sesión de VibeCoding se convierte así en la prueba de fuego de si el trabajo de requisitado fue real: si los artefactos eran sólidos, la IA los traduce en código con dirección. Si eran huecos, la IA produce algo que el alumno no puede evaluar ni conectar con su diseño original.

## La cadena de falsificación progresivamente costosa

El diseño crea una propiedad emergente relevante: falsificar el resultado completo es más costoso que hacerlo honestamente.

Para fabricar un examen sin haber trabajado, hay que fabricar el análisis. Para fabricar el análisis sin log, hay que fabricar el log. Para fabricar el log sin commits, hay que fabricar los commits. Para fabricar los commits con coherencia narrativa del proceso... en algún punto, el trabajo real es más eficiente que la falsificación.

Ningún sistema de evaluación es inmune al fraude. Este lo hace costoso de una forma específica: cada capa de falsificación requiere la capa anterior, y cada capa adicional exige más conocimiento del dominio para resultar convincente. El umbral de conocimiento necesario para falsificar convincentemente se aproxima al umbral de conocimiento que se está evaluando.

## El sistema es el pretexto

La consecuencia más importante de este diseño es conceptual: lo que se evalúa no es el sistema. El sistema es el pretexto.

Lo que se evalúa es si el alumno entiende lo que hizo y por qué. Un alumno con un sistema complejo construido en doce horas que no puede explicar las decisiones de diseño está en peor posición que uno con un sistema modesto construido en cuatro horas con un log honesto y un análisis limpio.

Esto también cierra el incentivo perverso de invertir tiempo extra en que la IA construya más sin entender nada. Más sistema sin más comprensión es más superficie de examen que no se puede cubrir.

La IA es la herramienta. El alumno es el ingeniero. La evaluación mide al ingeniero.
