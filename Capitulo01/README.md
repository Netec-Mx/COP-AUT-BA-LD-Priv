# Práctica: De la rutina al prompt reutilizable

## Metadatos
| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 10 minutos |
| **Complejidad** | Fácil |
| **Nivel de Bloom** | Aplicar |

## Descripción General
En esta práctica de laboratorio, el estudiante identificará una tarea operativa recurrente (la consolidación y redacción del reporte de estatus semanal del "Proyecto Delta") para descomponerla en elementos estáticos (instrucciones, reglas de negocio y restricciones) y elementos dinámicos (datos de entrada variables). El estudiante diseñará un prompt estructurado parametrizado basado en el framework de ingeniería de prompts de Microsoft (Rol, Contexto, Instrucciones, Restricciones y Formato de salida) y lo probará directamente en el entorno de chat de Microsoft 365 Copilot para validar su consistencia y reutilización en ciclos futuros.

## Objetivos de Aprendizaje
Al finalizar este laboratorio, serás capaz de:
- [ ] Identificar una tarea operativa recurrente basada en texto para su optimización cognitiva.
- [ ] Diseñar un prompt parametrizado utilizando el framework estructurado (Rol, Contexto, Instrucciones, Restricciones y Formato de salida).
- [ ] Validar el comportamiento del prompt estructurado frente a datos variables en el chat de Microsoft 365 Copilot.
- [ ] Establecer criterios de decisión para migrar un prompt reutilizable hacia un agente personalizado o un flujo automatizado.

## Prerrequisitos
- **Conocimientos teóricos:** Comprensión de la diferencia entre datos estáticos e información dinámica explicada en la Lección 1.1.
- **Acceso a plataformas:**
  - Cuenta activa de Microsoft 365 con una licencia de **Microsoft 365 Copilot Premium** (Service Release 2411).
  - Acceso a Microsoft Teams o Microsoft Edge con la interfaz de chat de Copilot habilitada.

## Entorno de Laboratorio
Para el desarrollo de este ejercicio práctico, se requiere la siguiente configuración de software y variables de entorno:

### Requisitos de Software
| Software / Herramienta | Versión Requerida | Enlace de Descarga / Acceso |
| :--- | :--- | :--- |
| **Microsoft Edge (64-bit)** | Versión 131.0.2903.86 o superior | [https://www.microsoft.com/edge](https://www.microsoft.com/edge) |
| **Microsoft 365 Copilot** | Service Release 2411 | Acceso mediante [https://copilot.microsoft.com](https://copilot.microsoft.com) o app integrada. |

### Configuración de Variables del Tenant de Demostración
- **Dominio de SharePoint:** `https://contosolabs.sharepoint.com/sites/OptimizacionTareas` [ENLACE OFICIAL: https://admin.microsoft.com]
- **Contexto del Proyecto:** El proyecto de ejemplo unificado se denomina **"Proyecto Delta"**.

## Instrucciones Paso a Paso

### Paso 1: Identificación y Desglose de la Tarea Recurrente
**Objetivo:** Analizar y separar el "esqueleto" estructural (instrucciones y reglas) de la "carga útil" (datos que cambian semanalmente) en una tarea común de reporte de estatus.

1. Abre un editor de texto plano en tu equipo de cómputo local (por ejemplo, Bloc de notas o VS Code).
2. Copia y analiza el siguiente escenario de negocio simulado:
   > **Escenario:** Cada viernes, debes tomar las notas informales de estatus enviadas por dos ingenieros del "Proyecto Delta" (Ana Gómez y Carlos Ruiz) en un chat, consolidarlas en un reporte estructurado y entregárselo a la gerencia en un formato profesional, omitiendo la jerga excesivamente técnica pero identificando las alertas críticas.
3. Clasifica la información identificando qué componentes de esta tarea son estables (siempre se repiten) y cuáles son variables (cambian cada viernes). Completa mentalmente o en tu editor el siguiente mapeo lógico:
   * **Componentes Estables (Estructura):** Rol del redactor, audiencia del reporte, restricciones de confidencialidad, estructura de la salida (Alertas, Avances, Próximos pasos).
   * **Componentes Variables (Datos de Entrada):** Las notas de avance específicas redactadas por Ana y Carlos cada semana.

**Resultado Esperado:** Haber conceptualizado la estructura de un prompt que acepta variables sin necesidad de reescribir las reglas corporativas en cada ejecución.

**Verificación:** Confirma que tienes clara la separación entre las instrucciones fijas que le darás a Copilot y el marcador de posición donde se inyectarán los datos semanales (`{{DATOS_DE_ENTRADA}}`).

---

### Paso 2: Diseño del Prompt Estructurado (Plantilla Reutilizable)
**Objetivo:** Construir el prompt parametrizado utilizando etiquetas estructurales claras y delimitadores para evitar que Copilot confunda las instrucciones con los datos de entrada.

1. En tu editor de notas, escribe el siguiente prompt estructurado utilizando el framework oficial de Microsoft. Asegúrate de respetar las etiquetas delimitadoras para estructurar la semántica:

```text
## ROL
Actúa como un Especialista en Comunicación de Proyectos de TI con alta capacidad de síntesis y redacción ejecutiva.

## CONTEXTO
Eres el responsable de procesar los insumos semanales de los ingenieros de desarrollo del "Proyecto Delta". Tu tarea es convertir notas informales de chat en un reporte de estatus consolidado para la dirección de operaciones.

## INSTRUCCIONES
Procesa la información provista en la sección de [DATOS_ENTRADA]. Debes consolidar los estados de avance en un único reporte organizado exactamente según el [FORMATO_SALIDA].

## RESTRICCIONES
- No asumas ni inventes hitos, fechas o entregables que no estén explícitamente listados en los datos de origen. Si faltan datos de un ingeniero, colócalo bajo observación.
- No uses términos excesivamente coloquiales que provengan de las notas de chat. Tradúcelos a un lenguaje corporativo neutro.
- Mantén la confidencialidad de los datos. No agregues referencias a otros proyectos ajenos al "Proyecto Delta".
- Si se detecta un retraso o bloqueo en las notas, resáltalo en la sección "Alertas Críticas" con un indicador visual (emoji de alerta).

## FORMATO_SALIDA
El reporte final debe estructurarse estrictamente en tres secciones separadas por líneas divisorias (---):
1. **Resumen Ejecutivo:** Una breve síntesis de 3 líneas sobre el estado actual del Proyecto Delta.
2. **Estatus de Actividades:**
   - **Avances Logrados:** Lista con viñetas que resuma los éxitos de la semana.
   - **Próximos Pasos:** Lista con viñetas de las tareas programadas para la siguiente semana.
3. **Alertas Críticas y Bloqueos:** Tabla con dos columnas (Descripción de la Alerta | Responsable Asignado). Si no hay alertas, escribe: "No se reportan alertas activas esta semana."

## DATOS_ENTRADA
---
{{DATOS_DE_ENTRADA}}
---
```

**Resultado Esperado:** Un prompt estructurado completo que implementa variables y directrices rígidas de diseño que garantizan la consistencia del resultado.

**Verificación:** Revisa que el prompt cuente con secciones diferenciadas para Rol, Contexto, Instrucciones, Restricciones, Formato de salida y un bloque contenedor bien delimitado para los Datos de Entrada.

---

### Paso 3: Ejecución y Validación con Datos de Prueba en Microsoft 365 Copilot
**Objetivo:** Ejecutar el prompt reutilizable en la interfaz web de Copilot, inyectando datos de prueba reales para evaluar el apego a las restricciones y el formato de salida.

1. Abre tu navegador **Microsoft Edge** (Versión 131.0.2903.86).
2. Dirígete a la interfaz de chat de Microsoft 365 Copilot ingresando a [https://copilot.microsoft.com](https://copilot.microsoft.com) e inicia sesión con tu cuenta organizativa del tenant de pruebas. Asegúrate de que el selector de chat esté en la opción estándar de conversación/chat de trabajo de M365 Copilot.
3. Copia el prompt diseñado en el **Paso 2**.
4. Antes de enviarlo, sustituye el marcador `{{DATOS_DE_ENTRADA}}` por los siguientes datos reales de ejemplo de la semana en curso (copia y pega exactamente este texto):

```text
- Notas de Ana Gómez (Ingeniera de QA): "Hola equipo. Esta semana terminé de correr el plan de pruebas de regresión para la versión 1.2 del core de automatización del Proyecto Delta. Encontré 3 bugs menores, pero ninguno bloquea la entrega. La próxima semana planeo automatizar las pruebas de estrés para el módulo de sincronización. Necesitamos que Carlos me entregue la compilación final el lunes temprano para no retrasarme."
- Notas de Carlos Ruiz (Desarrollador Principal): "Qué tal. Logré completar la refactorización del API de conexión a la base de datos de SharePoint para el Proyecto Delta. No obstante, tengo un bloqueo importante: el acceso al tenant de pruebas en 'https://contosolabs.sharepoint.com/sites/OptimizacionTareas' sigue sin permisos de escritura por parte de TI de infraestructura. Necesito que liberen esto urgente para poder subir la compilación de la versión 1.2. La otra semana estaré integrando los webhooks si me dan el acceso."
```

5. Presiona **Enter** o haz clic en el botón de **Enviar** para procesar la consulta en Copilot.

[VISUAL: 01-01-0004 - Captura de pantalla de la interfaz de Microsoft 365 Copilot mostrando el prompt largo estructurado en el cuadro de texto y los datos de entrada perfectamente delimitados por líneas de guiones "---".]

6. Espera la respuesta de Copilot y analiza detalladamente el formato entregado.

**Resultado Esperado:** Copilot devolverá un reporte de estatus consolidado para el Proyecto Delta que sigue rigurosamente el formato de tres secciones:
- Un resumen ejecutivo coherente.
- El estatus estructurado de avances y próximos pasos (QA y API).
- Una tabla de "Alertas Críticas" que contenga el bloqueo de Carlos Ruiz (permisos de SharePoint en la URL proporcionada) con un emoji de advertencia visual, asignándole la responsabilidad respectiva.

**Verificación:** Verifica visualmente que el formato de salida se compone exactamente de tres secciones separadas por líneas divisorias (`---`), y que la alerta de permisos de Carlos fue extraída y colocada correctamente en la tabla estructurada con su respectivo emoji de alerta.

---

## Validación y Pruebas
Para asegurar que tu prompt es realmente robusto y reutilizable, realiza las siguientes pruebas de consistencia técnica y manejo de excepciones:

1. **Prueba de Apego a Restricciones:** Revisa minuciosamente el reporte generado por Copilot. Verifica que **no** se hayan inventado fechas de entrega exactas de la liberación del tenant ni nombres de otros ingenieros que no figuraban en las notas originales de Ana Gómez o Carlos Ruiz.
2. **Caso de Prueba Adversario (Información Contradictoria e Insuficiente):**
   * Haz clic en **"Nuevo tema"** (icono de escoba) para limpiar el contexto del chat.
   * Envía el mismo prompt estático del Paso 2, pero esta vez introduce los siguientes datos de entrada inconsistentes dentro del bloque `[DATOS_ENTRADA]`:
     ```text
     - Notas de Carlos Ruiz: "No logré avanzar nada esta semana por problemas personales."
     ```
   * Ejecuta el prompt.
   * **Criterio de Aceptación:** Copilot debe generar el reporte indicando que no hay avances reportados por Carlos Ruiz, colocar bajo observación la falta de estatus de Ana Gómez (ya que el prompt estipula que si faltan datos de algún ingeniero debe reportarse como observación), e indicar en la tabla de Alertas Críticas el bloqueo de actividades por causas operativas. No debe inventar ninguna actividad o hito ficticio.

## Solución de Problemas

### Problema 1: Copilot ignora la tabla de salida o la genera como texto plano sin formato estructurado.
* **Síntoma:** El reporte se genera como párrafos continuos sin la estructura de tres secciones ni la tabla en formato Markdown para las alertas críticas.
* **Causa:** El volumen de instrucciones o la ambigüedad en el bloque `[FORMATO_SALIDA]` confunde al modelo de lenguaje.
* **Solución:** Reestructura el prompt utilizando delimitadores explícitos de Markdown para forzar la tabla de salida. Puedes sustituir la definición del formato en tu prompt por:
  `| Alerta Crítica | Responsable Asignado |` seguido de la línea de separación `| :--- | :--- |` para garantizar que el motor renderice una tabla HTML/Markdown limpia.

### Problema 2: El modelo de IA alucina soluciones técnicas que no se mencionaron en el reporte de origen.
* **Síntoma:** Copilot sugiere soluciones al problema de red del tenant o estima fechas de resolución que los ingenieros no colocaron en sus chats.
* **Causa:** Un exceso de libertad creativa debido a que la restricción de "No inventar datos" no se redactó con suficiente peso imperativo.
* **Solución:** Refuerza la sección `# RESTRICCIONES` en tu prompt plantilla utilizando palabras en mayúsculas sostenidas: *"RESTRICCIÓN ABSOLUTA: Está estrictamente prohibido adivinar o proponer planes de acción. Limítate de manera exclusiva a resumir los datos reales descritos en los datos de entrada."*

## Limpieza
Para evitar que las variables de esta simulación afecten futuras interacciones de análisis durante tu jornada de estudio, sigue estos pasos de limpieza del entorno de trabajo:

1. En la interfaz de chat de Microsoft 365 Copilot, localiza el botón **"Nuevo tema"** (representado comúnmente por un icono de escoba o un signo más `+` de reiniciar conversación) en la parte inferior izquierda de la caja de chat.
2. Haz clic sobre él. Esto purgará el contexto de memoria del modelo, borrando los datos de estatus del "Proyecto Delta" y las variables utilizadas de Ana y Carlos.
3. Cierra tu editor de texto local o guarda el prompt estructurado como `plantilla_reporte_delta.txt` en un directorio local seguro para su consulta futura durante los siguientes módulos de diseño de agentes de IA.

## Resumen
En este laboratorio, has completado de manera exitosa la transición de una tarea operativa repetitiva y manual (procesamiento de notas para reportes semanales) a una solución estructurada mediante el uso de ingeniería de prompts. 

Durante el ejercicio, lograste:
1. **Analizar** un caso de negocio rutinario, logrando catalogar qué componentes permanecen inalterables (formato corporativo, rol y restricciones) y cuáles fluyen dinámicamente semana tras semana (las notas de avance).
2. **Construir** un prompt parametrizado altamente profesional utilizando el framework de Microsoft, estableciendo límites claros para la IA a través de directrices de formato y estrictas restricciones de veracidad.
3. **Validar** su consistencia al ejecutarlo con datos heterogéneos y escenarios adversos, garantizando que el modelo actúe como un copiloto confiable y ordenado.

Este prompt estructurado servirá como la base lógica conceptual y metodológica que utilizarás más adelante para parametrizar las instrucciones de sistema dentro del desarrollo de tus agentes personalizados con Microsoft Agent Builder.
