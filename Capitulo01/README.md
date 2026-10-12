# Práctica: De la rutina al prompt reutilizable

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| Duración | 10 minutos |
| Complejidad | Fácil |
| Nivel de Bloom | Comprender, aplicar y evaluar |
| Tipo de actividad | Práctica individual guiada |
| Aplicaciones | Microsoft 365 Copilot Chat y Galería de indicaciones |
| Producto | Prompt reutilizable, una primera respuesta revisada y una versión guardada cuando la opción esté disponible |


### Distribución de tiempo (sin preparación previa)

| Paso | Trabajo | Minutos |
| :---: | :--- | ---: |
| 1 | Identificar el caso y sus variables | 2 |
| 2 | Copiar plantilla reutilizable | 4 |
| 3 | Ejecutar con datos A–C y D | 4 |
| **Total** | | **10** |

## Descripción General

En esta práctica identificarás una tarea de seguimiento que se repite periódicamente. Distinguirás instrucciones estables de información que cambia, prepararás un prompt reutilizable, lo ejecutarás con datos didácticos y comprobarás si evita completar información inexistente. La tarea de ejemplo es un **resumen de pendientes internos**; puedes usar una tarea equivalente propia siempre que no introduzcas datos confidenciales no autorizados.

### Escenario de práctica.

**Situación.** Formas parte de un equipo de seguimiento interno. Al terminar la semana necesitas preparar para una persona responsable un resumen de actividades pendientes. Cada semana cambian los registros, pero se repiten las reglas para clasificarlos y presentar su estado. Solo has recibido los tres mensajes siguientes; nadie te ha proporcionado nombres, fechas de cumplimiento ni aprobaciones.

| Registro | Información recibida | Interpretación respaldada |
| :--- | :--- | :--- |
| Actividad A | Borrador del informe preparado; revisión pendiente; no se informó quién aprueba ni cuándo. | Existe un borrador; la revisión y la aprobación no están acreditadas. |
| Actividad B | Recopilación de datos en curso; depende de confirmación externa; sin fecha comprometida. | Está en curso y hay una dependencia; no hay fecha confirmada. |
| Actividad C | Solicitud registrada; no se informó estado de ejecución ni responsable. | Hay solicitud registrada; avance y responsable son desconocidos. |


## Objetivos de Aprendizaje

Al finalizar podrás:

1. Identificar el objetivo, las fuentes, los pasos, las variables, las excepciones y el resultado de una tarea repetitiva.
2. Redactar y ejecutar instrucciones que permitan reutilizar la misma lógica con otros datos.
3. Evaluar los resultados de Copilot mediante criterios observables y guardar el prompt para uso posterior.

## Prerrequisitos

- Cuenta corporativa o educativa con acceso a [Microsoft 365 Copilot](https://m365.cloud.microsoft/chat) y autorización para trabajar con los datos seleccionados.
- Conocer los elementos básicos de un prompt y el manejo de información empresarial.
- Confirmar que Copilot puede recibir mensajes. La disponibilidad de la Galería de indicaciones depende de la aplicación y las políticas del entorno.

## Entorno de Laboratorio

| Componente | Preparación comprobable |
| :--- | :--- |
| Equipo | Computadora con conexión a Internet y navegador actualizado |
| Microsoft 365 Copilot | Iniciar sesión con la cuenta de trabajo y abrir una conversación nueva |
| Información | Usar exclusivamente los datos didácticos incluidos aquí o información real autorizada |
| Archivos | No se requiere preparar ninguno |

> [!TIP]
> En versiones actuales de Copilot el acceso al contenido laboral puede controlarse mediante **Work IQ**. Comprueba que esté habilitado solo si trabajarás con contenido de tu organización; para los datos pegados directamente en el prompt no necesitas localizar información en otros servicios.

## Instrucciones Paso a Paso

### Paso 1: Identificación y Desglose de la Tarea Recurrente

**Tiempo estimado: 2 minutos.**

1. Lee el caso **«Escenario de práctica»**, situado en la Descripción General de **esta misma práctica**.
2. Antes de abrir Copilot, identifica las reglas que permanecen iguales todas las semanas y los datos que cambiarán. Usa esta tabla resuelta como referencia:

   | Componente | Contenido del ejemplo |
   | :--- | :--- |
   | Objetivo | Resumir el estado de pendientes para dar seguimiento |
   | Constantes | Clasificar estado, detectar bloqueos y pedir datos faltantes sin inventarlos |
   | Variables | Actividades, estados, responsables y fechas informadas en cada ejecución |
   | Excepciones | Responsable no indicado, fecha no confirmada, información contradictoria |
   | Resultado | Tabla de estado más tres próximos pasos respaldados por los datos |

3. Comprueba la diferencia: son **constantes** «no inventar datos» y «entregar resumen + tabla + propuestas»; son **variables** los registros A, B y C, sus estados y la posible información de responsable/fecha.

**Criterio de avance:** los datos variables no están escritos como hechos permanentes en la plantilla.

### Paso 2: Diseño del Prompt Estructurado (Plantilla Reutilizable)

**Tiempo estimado: 4 minutos.**

1. Copia íntegramente el siguiente prompt en el editor de Copilot, sin enviarlo aún.
2. Revisa las secciones y sustituye **únicamente** el marcador `[PEGAR_DATOS_ACTUALES]` cuando vayas a ejecutar una instancia.

> [!IMPORTANT]
> **PROMPT 1 — Plantilla para consolidar pendientes.** Mantén el marcador en la versión que guardarás para reutilizarla.

```text
Tarea: elaborar un estado consolidado de pendientes a partir de la información de entrada.

Contexto: los datos proceden de actualizaciones de trabajo. Usa solo el contenido incluido en DATOS_ENTRADA; no supongas acceso a correos, calendarios o conversaciones que no se hayan proporcionado.

Procedimiento:
1. Identifica cada actividad y su estado explícito.
2. Señala dependencias, bloqueos y cambios, si aparecen.
3. Conserva el responsable y la fecha SOLO cuando estén indicados.
4. Distingue hechos informados de acciones propuestas.
5. Señala los campos faltantes como "Pendiente de confirmar".

Restricciones: no inventes nombres, responsables, fechas, aprobaciones ni avances. Si dos datos se contradicen y no es posible establecer cuál es vigente, marca "Requiere verificación".

Formato de salida:
A. Resumen de máximo tres oraciones.
B. Tabla con columnas: Actividad | Estado informado | Responsable | Fecha | Bloqueo o dato faltante.
C. Próximos pasos: hasta tres acciones sugeridas, identificadas como propuestas, nunca como acuerdos existentes.

DATOS_ENTRADA:
[PEGAR_DATOS_ACTUALES]
```

3. Confirma que el prompt incluye objetivo, contexto, procedimiento, restricciones, excepciones implícitas y estructura de salida. No elimines las advertencias sobre datos faltantes.

**Criterio de avance:** existe una plantilla copiable que no depende de nombres o archivos imaginarios.

### Paso 3: Ejecución y Validación con Datos de Prueba en Microsoft 365 Copilot

**Tiempo estimado: 4 minutos.**

1. En [Microsoft 365 Copilot](https://m365.cloud.microsoft/chat) inicia una conversación nueva y pega el **PROMPT 1**.
2. Sustituye el marcador por el bloque **«Datos de la primera semana»**, ubicado en **Escenario de práctica**, antes de los Objetivos de Aprendizaje. Es el conjunto de entrada de esta guía, no un ejemplo que debas crear tú mismo. El bloque se reproduce aquí para facilitar la copia:

   ```text
   - Actividad A: borrador del informe preparado; revisión pendiente; no se informó responsable de aprobación ni fecha.
   - Actividad B: recopilación de datos en curso; depende de una confirmación externa; no existe fecha comprometida.
   - Actividad C: solicitud registrada; estado de ejecución no indicado; responsable no indicado.
   ```

3. Envía el prompt. Identifica las secciones A, B y C; revisa si se distinguen estados y propuestas.
4. Comprueba que **no** aparecen nombres, fechas ni aprobaciones inventadas. Si un campo se completó sin evidencia, envía este ajuste:

   > **PROMPT 2 — Corrección de la respuesta**
   >
   > `Revisa tu respuesta usando solo los datos que pegué. Reemplaza cualquier responsable, fecha o estado no acreditado por "Pendiente de confirmar" y distingue todas las propuestas de los hechos.`

5. Para probar la reutilización, conserva todo el PROMPT 1 y sustituye únicamente el bloque `DATOS_ENTRADA` por el texto **«Datos para comprobar la reutilización»** que aparece en el escenario didáctico (Actividad D). Ejecuta de nuevo y comprueba que ahora existe **una sola fila de actividad** sin pendientes nuevos, pero se conservan las mismas tres secciones A, B y C.
6. Si la opción está visible, guarda la **versión genérica** del PROMPT 1 en la Galería de indicaciones: sobre el mensaje enviado usa **Guardar prompt/Guardar indicación**, o abre la galería desde Copilot Chat y selecciona la opción correspondiente. Revisa lo guardado y elimina los datos didácticos si se hubieran incluido al guardar el mensaje ejecutado.



## Validación y Pruebas

| Comprobación objetiva | Estado |
| :--- | :---: |
| La plantilla distingue instrucciones fijas de `DATOS_ENTRADA`. | ☐ |
| La respuesta tiene resumen, tabla y próximos pasos. | ☐ |
| Los responsables y fechas ausentes se marcan «Pendiente de confirmar». | ☐ |
| Los pasos recomendados se presentan como propuestas, no acuerdos. | ☐ |
| Una segunda entrada produce un resultado diferente sin reescribir las reglas. | ☐ |
| El prompt genérico queda guardado cuando la función está disponible. | ☐ |

> [!NOTE]
> Las respuestas de IA generativa pueden variar. Se validan campos, evidencias y restricciones; no se exige una redacción idéntica.


### Prueba positiva y control de errores

**Caso positivo:** la primera ejecución tiene tres filas A, B y C y marca responsables/fechas no proporcionados como pendientes. **Caso de reutilización:** al pegar únicamente D aparecen las mismas secciones y una fila, sin introducir responsables. **Fallo:** cualquier fecha, aprobador o avance no presente en el texto de entrada.

## Solución de Problemas

| Situación | Acción de recuperación |
| :--- | :--- |
| No aparecen las tres secciones | Reenvía el PROMPT 1; aclara «conserva literalmente los encabezados A, B y C». |
| Copilot inventa responsables o fechas | Aplica el PROMPT 2; elimina los datos no acreditados antes de continuar. |
| No aparece «Guardar prompt» | Conserva el texto genérico en un archivo personal autorizado o en una nota local; no declares que quedó guardado en la galería. |
| Copilot intenta buscar información empresarial ajena | Indica «trabaja exclusivamente con DATOS_ENTRADA» y verifica que no se estén añadiendo fuentes no previstas. |

## Limpieza

1. No compartas respuestas que pudieran incluir datos reales sensibles. Elimina únicamente los mensajes de prueba si las políticas lo requieren; abrir otra conversación **no equivale** a eliminar el historial previo.
2. Conserva la plantilla genérica sin datos reales y, si procede, la versión guardada en Galería de indicaciones.
3. No necesitas borrar aplicaciones, cuentas ni archivos del entorno.

## Resumen

Convertiste una tarea repetitiva en una plantilla con instrucciones estables y datos variables. Comprobaste que Copilot ofrece una salida estructurada, que hay criterios para detectar información no respaldada y que el prompt puede aplicarse de nuevo a otro conjunto de pendientes.

**Documentación oficial:** [Cómo guardar prompts en Copilot](https://support.microsoft.com/en-us/microsoft-365-copilot/managing-saved-prompts-for-uninstalled-agents) · [Respuestas de Copilot Chat](https://support.microsoft.com/en-us/microsoft-365-copilot/about-copilot-chat-responses).
