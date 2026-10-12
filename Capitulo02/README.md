# Práctica: Del briefing diario a la ejecución de una prioridad con Plan My Day

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| Duración | 15 minutos |
| Complejidad | Media |
| Nivel de Bloom | Aplicar, analizar y evaluar |
| Tipo de actividad | Demostración guiada por el instructor, reproducible por el participante con accesos equivalentes |
| Aplicaciones | Microsoft 365 Copilot, Agent Builder, plantilla Plan My Day y Galería de indicaciones |
| Producto | Briefing verificado, plan para atender una prioridad y prompt reutilizable |


## Descripción General

Se abrirá el agente **Plan My Day**, obtendrá un briefing de información a la que la cuenta tiene acceso y preparará una reunión prioritaria con preguntas, decisiones y una matriz de acuerdos. Se mostrará cómo convertir este procedimiento en un prompt que pueda reutilizarse. No se crearán tareas ni se enviarán comunicaciones sin autorización.

> [!NOTE]
> El ejemplo de **Outlook Calendar + correo a la propia cuenta**, descrito en «Escenario de trabajo y preparación controlada», da un punto de partida verificable incluso si no hay asuntos de trabajo reales. Se prepara antes del cronómetro; la visibilidad en Plan My Day sigue sujeta a licencia, indexación y permisos.

### Escenario de trabajo y preparación controlada

**Situación.** Actúas como responsable de seguimiento de solicitudes internas. Tienes que revisar un borrador de informe y llegar a una reunión con preguntas, decisiones por resolver y una plantilla vacía para registrar acuerdos. Primero pedirás a **Plan My Day** que detecte la actividad en el calendario y/o correo de tu cuenta. Después, ya en Copilot Chat, convertirás la prioridad en una agenda ejecutable. No se enviará ninguna invitación ni respuesta.

> [!IMPORTANT]
> Plan My Day no puede inventar una reunión que no existe. Si tu cuenta no tiene información apropiada, prepara **antes de iniciar el cronómetro** esta entrada didáctica directamente en Outlook; todo el texto está en esta guía.

**Preparación en Outlook (antes de clase, fuera de los 15 minutos):**

1. Abre [Outlook Calendar](https://outlook.office.com/calendar/) con la cuenta que utilizarás con Plan My Day. Selecciona **Nuevo evento**.
2. Crea una cita de **30 minutos** para el **próximo día hábil**, dentro de los **siguientes tres días hábiles**; elige una hora libre. No invites a terceros. Usa estos campos:

   | Campo en Outlook | Valor que debes introducir |
   | :--- | :--- |
   | Título | `LAB-COPAUT-PLAN | Revisión del borrador de solicitudes` |
   | Asistentes | Ninguno; cita personal de prueba |
   | Descripción / cuerpo | Copia íntegro el bloque siguiente |

   ```text
   ACTIVIDAD DIDÁCTICA — No es una reunión real con un cliente.
   Objetivo: preparar la revisión del borrador del informe de solicitudes internas.
   Temas a revisar: solicitudes abiertas y cerradas; excepciones; fuentes del estado.
   Pendientes: confirmar quién aprueba el informe y si existe una fecha de entrega acordada.
   No se ha realizado ninguna aprobación.
   La reunión se utilizará únicamente para practicar la preparación de una agenda.
   ```

3. Guarda el evento y comprueba que aparece en tu calendario. Anota la **fecha y hora reales** que elegiste: estas son variables del entorno y no se deben inventar en la respuesta.
4. Abre [Outlook Mail](https://outlook.office.com/mail/), elige **Nuevo correo**, envíalo **solo a tu propia dirección de laboratorio** y usa:

   **Asunto:** `LAB-COPAUT-PLAN | Preparación del informe`

   **Cuerpo:**

   ```text
   EJERCICIO DIDÁCTICO. Debo preparar la revisión del borrador de solicitudes internas.
   Necesito una agenda breve con preguntas sobre pendientes, excepciones y evidencias.
   No se ha confirmado responsable de aprobación ni fecha de entrega del informe.
   No existe autorización para enviar el informe a otras personas.
   ```

5. Confirma que recibiste el correo. Si la cuenta permite búsqueda de contenido laboral, ensaya localizar `LAB-COPAUT-PLAN`. La aparición de la cita o del correo en Outlook no garantiza su recuperación automática en Plan My Day; verifica esta última por separado.

**Lo que debes conseguir:** identificar una prioridad *con origen visible* (evento/correo), crear una agenda con cuatro bloques y conservar un prompt reutilizable. Si Plan My Day no recupera esos elementos por límites del tenant, podrás practicar la preparación de la agenda pegando sus datos directamente, pero **no debes marcar como superada la prueba de recuperación de Plan My Day**.

## Objetivos de Aprendizaje

1. Utilizar el agente Plan My Day creado desde una plantilla de Agent Builder.
2. Validar prioridades del briefing contra sus fuentes y seleccionar una prioridad existente.
3. Preparar un entregable de seguimiento y extraer instrucciones reutilizables.

## Prerrequisitos

- Licencia de Microsoft 365 Copilot asignada, Agent Builder habilitado y plantilla **Plan My Day** visible en la cuenta.
- Autorización para consultar correo, calendario y, cuando corresponda, Teams/SharePoint/OneDrive.
- La cita `LAB-COPAUT-PLAN` y el correo de prueba preparados con el texto incluido en esta guía (o una prioridad real autorizada equivalente), verificando su existencia en Outlook **antes** del cronómetro.

## Entorno de Laboratorio

| Recurso | Verificación previa |
| :--- | :--- |
| [Microsoft 365 Copilot](https://m365.cloud.microsoft/chat) | La sesión reconoce la cuenta de trabajo y permite consultar contenido laboral, con Work IQ si la interfaz lo ofrece. |
| Agent Builder | Aparece la opción **Agentes > Nuevo agente**, y dentro de plantillas se encuentra **Plan My Day**. |
| Calendario y Outlook | La cita `LAB-COPAUT-PLAN` de los siguientes tres días hábiles y el correo de preparación existen en la cuenta de laboratorio. |
| Insumos | No se necesitan archivos adjuntos. Los textos y guiones de los ejercicios posteriores están íntegramente en este mismo README. |

## Instrucciones Paso a Paso

### Paso 1: Acceso e inicialización del agente 'Plan My Day'

**Tiempo estimado: 4 minutos.**

1. Abre [Microsoft 365 Copilot](https://m365.cloud.microsoft/chat). Confirma que estás usando la cuenta corporativa autorizada.
2. En el panel lateral, selecciona **Agentes**. Si el agente **Plan My Day** ya está agregado y funciona, ábrelo directamente.
3. Abre **Plan My Day** y confirma que aparece una caja para escribir solicitudes.


### Paso 2: Ejecución del prompt estructurado para la consolidación de la agenda

**Tiempo estimado: 4 minutos.**

> [!IMPORTANT]
> **PROMPT 1 — Briefing y prioridades verificables**

```text
Prepara un briefing de mi trabajo de HOY y un panorama de los próximos TRES DÍAS HÁBILES, basado únicamente en información de Microsoft 365 a la que tengo permiso de acceso.
Incluye: 1) reuniones y eventos relevantes, con fecha/hora y referencia; 2) comunicaciones pendientes relacionadas; 3) hasta tres prioridades para preparar o ejecutar tareas, indicando por qué son importantes; 4) información no confirmada.
Si existe contenido asociado a «LAB-COPAUT-PLAN», inclúyelo con su referencia real; no afirmes haberlo encontrado si no está accesible.
No inventes reuniones, aprobaciones, responsables ni plazos. Si no encuentras contenido adecuado, indícalo. Conserva las fuentes consultables.
```

1. Envía el PROMPT 1 al agente y espera su respuesta.
2. Abre al menos una referencia (correo, reunión o archivo) y comprueba fecha, asunto y estado. Si los elementos son de prueba, señala que son datos didácticos.
3. Elige, preferentemente, el evento `LAB-COPAUT-PLAN` (o una prioridad real autorizada que el agente haya identificado). Abre el evento o correo original y copia **título, fecha/hora reales, objetivo, pendientes y referencia**, exclusivamente desde esa fuente.
4. Si el agente no recupera los datos preparados, verifica que sí están en Outlook y deja anotado **«Plan My Day no recuperó el contenido de prueba»**. No inventes una cita: para continuar con la parte de preparación de agenda utiliza el bloque de transferencia manual del paso siguiente.

**Criterio de avance:** una prioridad seleccionada tiene un origen verificable.

### Paso 3: Conversión de la prioridad en un entregable accionable

**Tiempo estimado: 5 minutos.**

1. Si Plan My Day encontró el evento/correo, copia los campos validados: título, fecha y hora de Outlook, objetivo, pendientes y referencia. Si no los encontró, utiliza **solo para la preparación de la agenda** el bloque manual siguiente y conserva la marca de limitación de Plan My Day:

   ```text
   PRIORIDAD DIDÁCTICA — Transferencia manual; NO recuperada por Plan My Day.
   Asunto: LAB-COPAUT-PLAN | Revisión del borrador de solicitudes.
   Objetivo: preparar una reunión sobre el estado de solicitudes abiertas y cerradas.
   Temas: excepciones, evidencia del estado y preguntas para revisión.
   Decisión pendiente: confirmar quién aprueba el informe y qué fecha de entrega se acepta.
   Aprobación existente: ninguna acreditada.
   Fecha/hora: pendiente de copiar del calendario de Outlook; no inventar.
   ```

2. Abre **Copilot Chat** (no presupongas que una conversación distinta conserva lo que viste en Plan My Day). Pega el PROMPT 2 completo y sustituye `[PRIORIDAD_VERIFICADA]` por los datos que acabas de copiar: **bien los campos originales accesibles, bien el bloque manual etiquetado**. No envíes el marcador sin sustituir.

   > [!IMPORTANT]
   > **PROMPT 2 — Preparación de reunión prioritaria**

   ```text
   A partir únicamente de la prioridad verificada que pego abajo, prepara una guía breve para su ejecución.
   Entrega cuatro bloques: (1) objetivo de la reunión; (2) temas que revisar y preguntas abiertas; (3) decisiones que es necesario obtener; (4) tabla vacía para capturar acuerdos con columnas Acuerdo | Responsable por confirmar | Fecha por confirmar | Seguimiento.
   Distingue los antecedentes acreditados de tus propuestas. No asignes responsables, plazos o decisiones que aún no existan.

   PRIORIDAD_VERIFICADA:
   [PRIORIDAD_VERIFICADA]
   ```

3. Revisa que el resultado mantenga la información original y que la tabla de acuerdos no presente aprobaciones inexistentes.
4. Conserva el resultado en la conversación o en un documento autorizado. No envíes una invitación ni marques tareas como realizadas.

**Criterio de avance:** existe una agenda ejecutable con decisiones pendientes y un formato de captura de acuerdos.

### Paso 4: Convertir el método en un prompt reutilizable

**Tiempo estimado: 2 minutos.**

1. Copia el PROMPT 2 con su marcador original `[PRIORIDAD_VERIFICADA]`; elimina datos específicos.
2. Guarda el prompt genérico en **Galería de indicaciones > Tus prompts** mediante **Guardar prompt**, si está disponible. Si no, consérvalo como texto en un lugar autorizado.
3. Comprueba que la versión guardada permite cambiar la prioridad sin reescribir las cuatro secciones.

## Validación y Pruebas

| Criterio | Estado |
| :--- | :---: |
| Plan My Day se abrió desde una plantilla o un agente previamente creado. | ☐ |
| El briefing distingue prioridades y conserva fuentes verificables. | ☐ |
| Se contrastó al menos una prioridad con su fuente de Outlook, o se documentó que solo se pudo continuar por transferencia manual. | ☐ |
| El entregable contiene objetivo, preguntas, decisiones y matriz de acuerdos. | ☐ |
| Las fechas y los responsables desconocidos no se dan por confirmados. | ☐ |
| Quedó disponible una plantilla reutilizable, guardada o copiada. | ☐ |


### Prueba positiva y control de errores

**Caso positivo:** Plan My Day muestra una cita o correo consultable de Outlook y la agenda usa esos datos. **Caso alterno (cobertura parcial):** si solo lograste pegar el bloque manual, la agenda puede aprobarse como ejercicio de preparación, **pero no** la recuperación del agente. **Fallo:** presentar información manual como si el agente la hubiera recuperado.

## Solución de Problemas

| Situación | Solución |
| :--- | :--- |
| No aparece la plantilla Plan My Day | Revisa disponibilidad de Agent Builder, licencias y despliegue del tenant. No sustituirla silenciosamente por otro agente. |
| Briefing vacío o incompleto | Comprueba que existan datos accesibles y que la cuenta y Work IQ permitan acceder a ellos. No inventes una agenda. |
| La reunión no tiene referencia o contexto | Abre la reunión directamente en Outlook y copia sus datos validados al PROMPT 2. |
| No se puede guardar el prompt | Conservar el texto genérico y registrar la limitación de la galería; la demostración principal puede completarse. |

## Limpieza

1. Conserva el prompt genérico y los datos de la prioridad únicamente en su ubicación autorizada.
2. No borres el agente Plan My Day si se utiliza en otras actividades.
3. Evita compartir el briefing si contiene información real de correo o calendario.

## Resumen

Se utilizó Plan My Day para identificar una prioridad, se comprobó su procedencia y se creó una estructura reproducible para preparar su ejecución sin asumir que Copilot Chat conoce automáticamente la conversación del agente.

**Referencia oficial:** [Plantilla Plan My Day en Agent Builder](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-template-plan-my-day).

---

# Práctica: De múltiples correos a un estado consolidado

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| Duración | 17 minutos |
| Complejidad | Media |
| Nivel de Bloom | Aplicar, analizar y evaluar |
| Tipo de actividad | Demostración guiada por el instructor |
| Aplicaciones | Outlook, Microsoft 365 Copilot Chat y Galería de indicaciones |
| Producto | Cronología, estado vigente de un asunto y prompt reutilizable |


### Distribución de tiempo (sin preparación previa)

| Paso | Trabajo | Minutos |
| :---: | :--- | ---: |
| 1 | Comprobar los mensajes | 4 |
| 2 | Delimitar fuentes | 4 |
| 3 | Reconstruir cronología | 6 |
| 4 | Conservar prompt | 3 |
| **Total** | | **17** |

## Descripción General

Se reconstruirá un asunto a partir de varias comunicaciones, diferenciando antecedentes, cambios, propuestas, decisiones y puntos sin evidencia suficiente. El ejercicio usa correos reales autorizados o un conjunto de tres correos didácticos, cuyos asuntos y cuerpos están incluidos a continuación en esta guía. No requiere crear un workflow: la automatización se aborda en el capítulo 5.

### Escenario de trabajo y resultado que se va a comprobar

**Situación.** Un equipo necesita conocer el estado actual del **borrador de un informe de solicitudes**. La información está repartida en **tres correos consecutivos**: solicitud inicial (01), propuesta de fecha (02) y cambio de esa propuesta (03). Debes reconstruir la secuencia, no simplemente resumir el último correo.

| Mensaje | ¿Qué aporta? | ¿Qué NO permite concluir? |
| :--- | :--- | :--- |
| 01 — Solicitud inicial | Se solicita elaborar un informe; falta asignación. | Que ya exista aprobación o persona responsable. |
| 02 — Propuesta de seguimiento | Se propone revisar un borrador el **20/11/2026**. | Que esa fecha sea un compromiso aprobado. |
| 03 — Cambio en la revisión | La fecha anterior se sustituye por la propuesta **23/11/2026**; el informe sigue sin aprobar. | Que el borrador esté terminado o que haya una aprobación. |

**Material de entrada:** los tres asuntos y cuerpos íntegros aparecen en `Entorno de Laboratorio > Correos de ejemplo`, inmediatamente más abajo. La forma de trabajar preferida es enviarlos a **tu propia cuenta** antes de la práctica, encontrarlos en Outlook y consultarlos con Copilot. Si Copilot no los recupera por permisos o indexación, se pueden pegar los tres textos con sus identificadores; esa ruta evalúa **consolidación de texto**, no búsqueda autónoma en Outlook.

**Resultado esperado:** cronología `01 → 02 → 03`, fecha anterior y nueva fecha marcadas como *propuestas*, **aprobación pendiente**, ausencia de responsable de aprobación y próximo paso recomendado identificado como sugerencia. Ningún mensaje contiene una aprobación del informe.

## Objetivos de Aprendizaje

1. Acotar un asunto a partir de correos identificables.
2. Diferenciar la información vigente de los antecedentes y contradicciones.
3. Obtener un estado consolidado con referencias trazables y próximos pasos sujetos a confirmación.

## Prerrequisitos

- Microsoft 365 Copilot con acceso al contenido laboral de Outlook mediante la cuenta de demostración.
- Dos o más correos relacionados, preferentemente tres, consultables desde esa cuenta.
- Si no hay correos de trabajo apropiados, preparar **antes de clase** los tres mensajes didácticos de la sección «Correos de ejemplo para preparar el entorno» incluida en esta práctica, sin utilizar destinatarios externos.

## Entorno de Laboratorio

| Componente | Preparación |
| :--- | :--- |
| Outlook | [Abrir Outlook web](https://outlook.office.com/mail/) y localizar el asunto común de la conversación. |
| Copilot Chat | [Abrir Copilot](https://m365.cloud.microsoft/chat), mantener habilitado el acceso laboral que requiera la versión de la interfaz. |
| Datos de prueba opcionales | Tres asuntos y cuerpos completos, listos para copiar desde el apartado siguiente. No hay archivos auxiliares. |

> [!WARNING]
> La recuperación depende de indexación y permisos; copiar el texto de un correo **no** prueba que Copilot haya podido localizarlo por sí mismo. Diferencia claramente «búsqueda sobre Outlook» de «análisis de texto proporcionado».

### Correos de ejemplo para preparar el entorno (antes del tiempo de práctica)

> [!IMPORTANT]
> Los tres correos siguientes son **material simulado**. Están incluidos aquí para que cualquier participante pueda reproducir la demostración sin descargar recursos. Enviarlos e indexarlos debe realizarse **antes** de los 17 minutos previstos para el análisis.

1. Abre [Outlook](https://outlook.office.com/mail/) con la misma cuenta de trabajo que usarás en Microsoft 365 Copilot.
2. Selecciona **Correo nuevo**. En **Para**, escribe únicamente **tu propia dirección de correo de laboratorio**; no agregues otros destinatarios.
3. Copia el valor **Asunto** del Correo 1 en el campo Asunto. Copia **solo el contenido del bloque de texto** en el cuerpo. Envía el correo y comprueba que lo recibiste.
4. Repite el procedimiento para los correos 2 y 3 **en ese orden**. Espera a que aparezcan los tres en la Bandeja de entrada.
5. En la búsqueda de Outlook introduce `LAB-COPAUT-CORREOS`. Comprueba los asuntos `01`, `02` y `03`. Si Copilot no los recupera, los mismos textos pueden pegarse manualmente al chat, indicando su procedencia.

<details>
<summary>Correo 1 — Solicitud inicial (ver asunto y copiar cuerpo)</summary>

**Asunto:** `LAB-COPAUT-CORREOS | 01 | Solicitud inicial`

**Cuerpo listo para copiar:**

```text
EJEMPLO DIDÁCTICO. Solicitud interna: preparar un informe consolidado de solicitudes abiertas y cerradas para revisión.
No se ha confirmado todavía un responsable del informe ni una fecha de revisión.
Estado: solicitud recibida, trabajo pendiente de asignación.
```

</details>

<details>
<summary>Correo 2 — Definición preliminar (ver asunto y copiar cuerpo)</summary>

**Asunto:** `LAB-COPAUT-CORREOS | 02 | Propuesta de seguimiento`

**Cuerpo listo para copiar:**

```text
EJEMPLO DIDÁCTICO. Para el mismo informe de solicitudes, se propone que el equipo de seguimiento prepare un primer borrador.
La fecha propuesta para revisar el borrador es el 20 de noviembre de 2026.
La persona que dará la aprobación final sigue sin confirmarse.
Estado: borrador por preparar. La fecha sigue siendo una propuesta.
```

</details>

<details>
<summary>Correo 3 — Actualización más reciente (ver asunto y copiar cuerpo)</summary>

**Asunto:** `LAB-COPAUT-CORREOS | 03 | Cambio en la revisión`

**Cuerpo listo para copiar:**

```text
EJEMPLO DIDÁCTICO. Actualización: la revisión del primer borrador ya NO está prevista para el 20 de noviembre de 2026.
La nueva fecha propuesta es el 23 de noviembre de 2026.
El informe todavía NO ha sido aprobado y el responsable de aprobación permanece por confirmar.
No se indica que el borrador se haya terminado.
```

</details>

> [!NOTE]
> Las fechas de noviembre de 2026 son parte del escenario ficticio; no deben reemplazarse automáticamente por fechas actuales. Las **fechas de recepción** de los tres mensajes dependen del día real en que se envíen. Si Copilot recupera solo algunos, comprueba la indexación o pega los textos con sus asuntos y fechas reales de recepción. No presentes el análisis de texto pegado como recuperación automática de Outlook.

**Control previo:** existen exactamente tres mensajes con el identificador común; el 20/11/2026 es una propuesta anterior, el 23/11/2026 es la propuesta posterior y no existe aprobación acreditada.

## Instrucciones Paso a Paso

### Paso 1: Verificación de los Datos de Entrada en Outlook

**Tiempo estimado: 4 minutos.**

1. Abre Outlook con la misma identidad que usarás en Copilot.
2. Si preparaste los tres correos del apartado **«Correos de ejemplo para preparar el entorno»**, busca `LAB-COPAUT-CORREOS` y verifica los mensajes **01, 02 y 03**. Si no fueron enviados o todavía no están indexados, identifica la ruta de **texto pegado** del Paso 2 y documenta que no se comprobó la recuperación de Outlook. Todos los mensajes están completos en esta guía.
3. Abre los mensajes y anota asunto, fecha/hora de recepción y enlace si la interfaz permite copiarlo. Ordena por fecha y no confundas fecha de envío con fecha de un compromiso descrito dentro del correo.
4. Revisa si hay mensajes duplicados o un hilo reenviado. Define el criterio de alcance: solo tres mensajes didácticos o los correos seleccionados explícitamente.

**Criterio de avance:** has delimitado los tres mensajes didácticos **01, 02 y 03**. Si provienen de Outlook, anota fechas de recepción reales; si no, trabaja por identificador de secuencia y registra «entrada manual».

### Paso 2: Creación y Configuración del Alcance de Trabajo en Copilot

**Tiempo estimado: 4 minutos.**

1. Abre Copilot Chat en la cuenta corporativa. Comprueba que la experiencia tenga acceso a datos laborales (por ejemplo, **Work IQ** habilitado, si aparece).
2. En una conversación nueva pide primero identificar las fuentes; no pidas todavía conclusiones. Para los correos didácticos copia el PROMPT 1 tal como aparece; si usas correos de trabajo autorizados, reemplaza el identificador `LAB-COPAUT-CORREOS` por el asunto exacto de esos mensajes antes de enviarlo:

   > [!IMPORTANT]
   > **PROMPT 1 — Localizar comunicaciones del asunto**

   ```text
   Busca entre mis correos de Outlook los mensajes cuyo asunto contiene exactamente "LAB-COPAUT-CORREOS".
   Usa solo los mensajes relacionados con ese asunto y el período que efectivamente muestran las fuentes.
   Devuelve una tabla con: asunto exacto | fecha de recepción | remitente | enlace o referencia de origen.
   No reconstruyas el asunto todavía. Si no tienes acceso a los mensajes o faltan resultados, dilo expresamente y solicita que los adjunte o pegue.
   ```

3. Compara la lista generada con lo que localizaste en Outlook. No des por verdaderos mensajes que no puedes abrir.
4. Si Copilot no puede recuperarlos, vuelve a «Correos de ejemplo para preparar el entorno» y copia **los tres cuerpos, asuntos y fechas reales de recepción** dentro del mismo chat, distinguiendo `CORREO 01`, `CORREO 02` y `CORREO 03`. Indica: «Entrada manual de mensajes didácticos; no se validó la búsqueda automática en Outlook». Si no enviaste los correos, declara «Fecha de recepción no disponible»; ordena entonces por los identificadores de secuencia `01` a `03`, **no** por una fecha inventada.

**Criterio de avance:** los mensajes realmente analizados y su origen son conocidos; no se exige que Copilot encuentre todos los correos si el tenant lo impide.

### Paso 3: Ejecución de la Consolidación mediante Prompt Estructurado

**Tiempo estimado: 6 minutos.**

> [!IMPORTANT]
> **PROMPT 2 — Cronología y estado consolidado**

```text
Utiliza ÚNICAMENTE los correos que acabas de identificar o que he pegado en esta conversación.
1. Genera una cronología por fecha real de recepción de cada correo, cuando esté disponible (no por las fechas propuestas dentro del texto). Si se pegaron ejemplos sin fechas de recepción verificadas, utiliza solo el orden explícito 01, 02 y 03 e indica «Fecha de recepción no disponible»; no inventes marcas de tiempo.
2. Para cada solicitud, acuerdo, propuesta o cambio, cita el asunto/fecha del correo que lo respalda.
3. Indica cuál es la información más reciente y qué información anterior reemplaza; si se trata de una propuesta, NO la describas como aprobación definitiva.
4. Señala contradicciones, ausencias de responsables, aprobaciones o fechas.
5. Concluye con: Resuelto | Pendiente | Decisión confirmada | Cambio informado | Requiere confirmación | Próxima acción sugerida.
6. Conserva enlaces a los mensajes cuando estén disponibles; si solo recibiste texto pegado, cita identificadores o asuntos, sin fabricar hipervínculos.
No inventes correos, responsables ni decisiones.
```

1. Envía PROMPT 2 en la misma conversación.
2. Si estás usando los tres correos didácticos, verifica que la fecha del **20/11/2026** aparezca como propuesta anterior y **23/11/2026** como propuesta más reciente, **no** como aprobación.
3. Revisa que «informe aprobado» no aparezca como hecho; el tercer correo indica lo contrario.
4. Pide corregir cualquier conclusión sin fuente: `Vuelve a marcar como pendiente todo dato que no pueda sustentarse en un correo identificado.`

**Criterio de avance:** el estado distingue expresamente hechos, propuestas y aspectos no confirmados.

### Paso 4: Guardar el patrón de consulta

**Tiempo estimado: 3 minutos.**

1. Copia el PROMPT 2 y prepara una versión independiente del caso, reemplazando la referencia a los correos identificados por `[ASUNTO_O_REFERENCIAS_DEL_CASO]`.
2. Guárdala en la Galería de indicaciones si la función está habilitada o en una nota autorizada; no incluyas conversaciones confidenciales dentro de una plantilla compartida.
3. Confirma que la misma estructura funcionaría con otro asunto o período.

## Validación y Pruebas

| Criterio de aceptación | Estado |
| :--- | :---: |
| Se identificaron los tres mensajes y su procedencia; las fechas de recepción solo se anotaron si realmente existen. | ☐ |
| La cronología no confunde fecha del correo con fecha propuesta de revisión. | ☐ |
| La información vigente está diferenciada de versiones anteriores. | ☐ |
| Las conclusiones tienen referencia al mensaje original, o identificadores si se pegó el texto. | ☐ |
| No se infieren responsables ni aprobaciones inexistentes. | ☐ |
| Se obtuvo un estado consolidado y un prompt generalizable. | ☐ |


### Prueba positiva y control de errores

**Caso positivo:** cronología 01, 02 y 03; 20/11/2026 era propuesta anterior, 23/11/2026 es propuesta posterior; aprobación y aprobador permanecen sin confirmar. **Fallo:** clasificar la nueva fecha como aprobación o inventar un enlace de Outlook cuando los correos solo se pegaron manualmente.

## Solución de Problemas

| Situación | Qué hacer |
| :--- | :--- |
| Copilot no halla mensajes existentes | Verifica cuenta, permisos, capacidad Work IQ, asunto exacto y tiempo de indexación. Si persiste, pega la información manualmente y declara esta limitación. |
| Aparecen correos ajenos al caso | Usa un identificador exacto y proporciona los asuntos seleccionados; elimina resultados no autorizados. |
| Una propuesta se trata como decisión | Pide una tabla «Confirmado / Propuesto / Por confirmar» con fuente por fila y revisa el original. |
| No hay enlaces clicables | Conserva asunto y fecha como referencia manual; no fabriques URLs ni digas que el enlace existe. |

## Limpieza

1. Elimina solo los correos didácticos enviados a la propia cuenta cuando ya no los necesites y la política lo permita.
2. Conserva la estructura del prompt sin texto privado y los resultados solo en una ubicación aprobada.
3. No es necesario eliminar workflows; este ejercicio no crea ninguno.

## Resumen

Copilot consolidó —por recuperación de Outlook o por entrada manual expresamente señalada— varias comunicaciones en un seguimiento del asunto, conservando cambios y evidencia. Se evitó presentar propuestas como decisiones definitivas.

**Referencia oficial:** [Microsoft 365 Copilot Chat: fuentes y respuestas](https://support.microsoft.com/en-us/microsoft-365-copilot/about-copilot-chat-responses). Los tres mensajes del ejemplo están incluidos en esta guía.

---

# Práctica: De múltiples reuniones a un seguimiento consolidado

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| Duración | 18 minutos |
| Complejidad | Media |
| Nivel de Bloom | Aplicar, analizar y evaluar |
| Tipo de actividad | Demostración guiada por el instructor |
| Aplicaciones | Teams, Facilitator, Loop y Microsoft 365 Copilot Chat |
| Producto | Vista unificada de acuerdos, responsables y fechas, con vínculos a las reuniones |


## Descripción General

Consolidarás acuerdos y compromisos documentados en **dos reuniones diferentes**. Como fuente principal se usarán las notas de Loop generadas por **Facilitator**; se consultarán transcripciones y chats cuando estén disponibles y autorizados. Cada acuerdo conservará su origen, y la guía distinguirá la evolución del compromiso de su estado realmente confirmado.

### Escenario de trabajo: dos reuniones sobre el mismo informe

**Situación.** Dos reuniones sucesivas trataron la revisión de un borrador de informe de solicitudes. En la primera se propuso una revisión para el **20/11/2026**. En la segunda se sustituyó esa propuesta por **23/11/2026**. Ninguna reunión confirma la persona aprobadora ni aprueba el informe. Tu tarea consiste en leer las **dos** notas y generar una sola vista de compromisos, citando el origen de cada afirmación.

| Fuente | Decisión o información contenida | Aspectos abiertos |
| :--- | :--- | :--- |
| Reunión didáctica 1 | Preparar borrador; propuesta inicial 20/11/2026. | Aprobador no confirmado; aprobación inexistente. |
| Reunión didáctica 2 | Cambia la propuesta de revisión al 23/11/2026. | Borrador no demostrado como terminado; aprobación pendiente. |

**Entrada exacta:** en `Entorno de Laboratorio > Guion de las reuniones y notas de contingencia` están los textos completos. Selecciona **Ruta A** si tienes dos reuniones reales programadas y notas de Facilitator generadas en Loop; selecciona **Ruta B** para pegar dos notas simuladas directamente desde esta guía. No llames «nota creada por Facilitator» a un texto pegado manualmente.

**Salida esperada:** una matriz con dos fuentes diferenciadas, el cambio de fecha explicado, los campos `Responsable` y `Aprobación` como *pendientes de confirmar* y propuestas de seguimiento separadas de los acuerdos. No se envían correos ni se asignan tareas a terceros.

## Objetivos de Aprendizaje

1. Localizar fuentes de reunión verificables y comprobar su accesibilidad.
2. Integrar compromisos procedentes de más de una reunión, evitando duplicados y contradicciones.
3. Preparar una matriz de seguimiento con responsables, fechas y elementos pendientes de confirmación.

## Prerrequisitos

- Dos reuniones de Teams ya realizadas, con notas de Facilitator accesibles en Loop mediante la cuenta de demostración. **Estas reuniones se preparan antes de clase**, no dentro de los 18 minutos.
- Licencia y configuración de Teams/Facilitator apropiadas, junto con una licencia de Microsoft 365 Copilot y permisos sobre las reuniones.
- Preparación previa: seguir el guion y las instrucciones para crear las dos reuniones que aparecen **en esta práctica**, inmediatamente después de «Entorno de Laboratorio».

## Entorno de Laboratorio

| Elemento | Comprobación |
| :--- | :--- |
| Microsoft Teams | El instructor puede abrir los dos chats de reunión. |
| Facilitator / Loop | Cada reunión cuenta con una página de notas generada por Facilitator, con contenido que el instructor revisó. |
| Transcripciones o chat | Únicamente si fueron habilitados/recopilados y son accesibles; no son obligatorios si las notas ya documentan el caso. |
| Alternativa didáctica | Dos notas simuladas, listas para copiar desde el apartado siguiente y **etiquetadas como manuales**. No acreditan el uso de Facilitator. |

> [!IMPORTANT]
> Facilitator se habilita en reuniones de Teams programadas y las notas generadas se consultan en el chat/Resumen y se almacenan en Loop. No atribuyas a Facilitator una página manual ni supongas que cualquier reunión genera automáticamente transcripción.

### Guion de las reuniones y notas de contingencia (preparación previa)

> [!IMPORTANT]
> Para demostrar **Facilitator realmente**, el instructor debe producir las notas antes de los 18 minutos de práctica. Los textos de esta sección son guiones didácticos, **no** notas generadas por el agente; las notas reales pueden variar y deben comprobarse.

#### Ruta A — Demostración con Facilitator y fuentes auténticas

1. En [Teams](https://teams.microsoft.com/) crea **dos reuniones programadas** separadas con una segunda persona autorizada. No uses una llamada ni una reunión instantánea como sustituto de este escenario.
2. En las opciones de cada reunión, comprueba la configuración de **Copilot** y activa **Facilitator**, siempre que la licencia y la política de la organización lo permitan. Verifica que las notas estén disponibles para las personas que participarán.
3. En la **reunión 1**, lee y comenta con el otro participante este guion (texto íntegro listo para copiar a tu invitación o agenda, si lo deseas):

   ```text
   Reunión didáctica 1: necesitamos preparar un borrador del informe de solicitudes.
   La fecha propuesta para revisar el borrador es el 20/11/2026.
   No hemos confirmado la persona que aprobará el informe.
   No existe una aprobación del informe en esta reunión.
   ```

4. En la **reunión 2**, lee y comenta este segundo guion:

   ```text
   Reunión didáctica 2: la revisión prevista originalmente para el 20/11/2026
   se sustituye por una nueva fecha PROPUESTA: 23/11/2026.
   El informe no está aprobado y el responsable de aprobación sigue sin confirmar.
   No afirmamos que el borrador esté terminado.
   ```

5. Finalizadas ambas reuniones, abre **Teams > Chat de la reunión > Resumen/Recap > Notas** (o la entrada de notas visible según la interfaz), abre la página de **Loop** correspondiente a cada reunión y comprueba su contenido y permisos.
6. Conserva los dos enlaces reales para emplearlos en el paso 1. Revisa las notas generadas: no supongas que Facilitator transcribió exactamente el guion.

#### Ruta B — Contingencia identificada como simulación manual

Si las notas de Facilitator no existen o el acceso está bloqueado, copia el contenido de **cada bloque** en páginas separadas de Loop cuando tengas acceso a Loop, tituladas `Simulación manual — no generada por Facilitator — Reunión 1` y `Simulación manual — no generada por Facilitator — Reunión 2`. Si Loop tampoco está disponible, usa ambos bloques directamente en Copilot Chat bajo sus títulos respectivos y registra que **no se demostró** ni Facilitator ni la recuperación de Loop.

<details>
<summary>Nota simulada 1 — lista para copiar</summary>

```text
FUENTE: Simulación manual — no generada por Facilitator — Reunión 1
Reunión didáctica 1. Se propuso preparar un borrador del informe.
Fecha de revisión propuesta: 20/11/2026.
Responsable de aprobación: sin confirmar.
No consta aprobación.
```

</details>

<details>
<summary>Nota simulada 2 — lista para copiar</summary>

```text
FUENTE: Simulación manual — no generada por Facilitator — Reunión 2
Reunión didáctica 2. La fecha de revisión anterior se reemplaza por una nueva propuesta: 23/11/2026.
El informe permanece sin aprobación.
La persona aprobadora sigue por confirmar.
```

</details>

> [!WARNING]
> No atribuyas a Facilitator el contenido que se copió manualmente, aunque esté almacenado en Loop. La ruta B permite practicar la **consolidación de información**, pero deja pendiente la comprobación técnica de la **generación de notas mediante Facilitator**. Ambas rutas conservan los mismos criterios de revisión de fechas y aprobaciones.

## Instrucciones Paso a Paso

### Paso 1: Localización y verificación de las notas y fuentes de Teams

**Tiempo estimado: 5 minutos.**

1. Decide qué fuentes tienes **antes de empezar**: **Ruta A** cuando existen dos reuniones programadas, realizadas y con notas de Facilitator; **Ruta B** si utilizarás las **dos notas simuladas listas para copiar** de esta guía. Si usas Ruta B, no necesitas abrir un chat real de Teams y puedes ir al Paso 2 tras copiar ambas notas con sus títulos.
2. **Solo Ruta A:** en Teams, abre el chat de la primera reunión y entra en **Resumen / Recap > Notas** (o la entrada equivalente); abre las notas que Facilitator generó en Loop y copia el vínculo si se ofrece.
3. **Solo Ruta A:** repite con la segunda reunión. Anota fecha real, título y enlace de ambas fuentes; no inventes la fecha cuando trabajes con textos manuales.
4. **Cualquiera de las rutas:** lee las dos notas y reconoce el cambio de fecha **20/11/2026 → 23/11/2026**; comprueba que ambas son propuestas y que la aprobación permanece pendiente. Si hay transcripciones auténticas accesibles, utilízalas para contrastar expresiones dudosas.
5. **Ruta B:** copia las dos notas del apartado **«Guion de las reuniones y notas de contingencia»**. Consérvalas con los rótulos `Simulación manual — Reunión 1` y `Simulación manual — Reunión 2` y pégalas en Copilot Chat en el Paso 2; no les atribuyas enlaces, fechas de reunión o autoría de Facilitator inexistentes.

**Criterio de avance:** están delimitadas dos fuentes y su procedencia real o simulada.

### Paso 2: Interrogación cruzada multi-reunión mediante Copilot Chat

**Tiempo estimado: 6 minutos.**

1. Abre una nueva conversación de Copilot Chat con la misma identidad y acceso laboral disponible.
2. **Ruta A:** adjunta o referencia las dos notas de Loop si el selector del chat las encuentra; si el selector no las localiza, pega el texto exacto verificado de cada página y su referencia. **Ruta B:** pega los dos bloques completos de esta guía con los títulos `Simulación manual — Reunión 1/2`, sin fechas ni enlaces inventados.
3. Ejecuta el siguiente prompt; conserva las referencias indicadas:

   > [!IMPORTANT]
   > **PROMPT 1 — Consolidación trazable de reuniones**

   ```text
   Consolidar los acuerdos y compromisos de estas DOS reuniones de Teams, utilizando exclusivamente las notas de Loop y las transcripciones/chats que haya seleccionado o pegado.
   Genera una tabla: Compromiso | Reunión de origen | Responsable acreditado | Fecha acreditada | Estado | Evidencia | Dato por confirmar.
   Unifica elementos equivalentes sin borrar su historia. Si una reunión posterior modifica una fecha o decisión, distingue el valor anterior del más reciente y comprueba si el cambio quedó confirmado.
   Separa: compromisos propios, compromisos de otras personas y compromisos sin responsable definido. No inventes participantes ni vencimientos; usa «Pendiente de confirmar» cuando falte evidencia.
   ```

4. Revisa la salida junto a las notas. Cuando un dato no aparezca en ninguna fuente, solicita `Indica que el dato está pendiente y no lo infieras.`
5. Si hay un enlace que Copilot no puede consultar y pegaste manualmente la información, no declares que el sistema recuperó la reunión.

**Criterio de avance:** la matriz identifica por lo menos dos fuentes diferenciadas y no inventa aprobaciones.

### Paso 3: Consolidación en una minuta estructurada para distribución ejecutiva

**Tiempo estimado: 5 minutos.**

> [!IMPORTANT]
> **PROMPT 2 — Vista priorizada y próximos pasos**

```text
Toma exclusivamente la matriz de compromisos verificada en esta conversación.
Crea una minuta consolidada con cuatro secciones:
1. Resumen de las dos reuniones (máximo cuatro líneas).
2. Acuerdos vigentes, con origen de cada uno.
3. Tabla de seguimiento: Acuerdo | Responsable | Fecha | Estado | Prioridad propuesta | Fuente.
4. Asuntos que requieren confirmación y acciones de seguimiento sugeridas.
La prioridad es una recomendación, no una instrucción emitida en la reunión. No inventes responsables, decisiones ni fechas. No redactes ni envíes correos automáticamente.
```

1. Ejecuta PROMPT 2 sin abrir otra conversación, para mantener el contexto analizado.
2. Contrasta dos filas de la minuta con las fuentes. Si hay una fecha anterior y otra más reciente, explica su relación.
3. Si trabajas con las notas de preparación, confirma que el informe **no** aparece como aprobado y que la fecha 23/11/2026 es una propuesta posterior, no un acuerdo probado.
4. Copia la minuta verificada a una página o documento autorizado, si necesitas conservarla; la práctica no incluye enviarla.

### Paso 4: Preparar un prompt reutilizable

**Tiempo estimado: 2 minutos.**

1. Guarda el PROMPT 1 como patrón genérico en Galería de indicaciones o consérvalo como texto autorizado.
2. Sustituye referencias particulares por `[REUNIONES_SELECCIONADAS]` antes de compartir una plantilla.

## Validación y Pruebas

| Criterio de aceptación | Estado |
| :--- | :---: |
| Se localizaron dos reuniones o dos fuentes manuales identificadas honestamente. | ☐ |
| Cada acuerdo tiene su fuente o está marcado sin evidencia. | ☐ |
| Los responsables y fechas no informados quedan como «Pendiente de confirmar». | ☐ |
| Las modificaciones entre reuniones se muestran sin borrar el dato anterior. | ☐ |
| La vista final diferencia acuerdos, prioridades sugeridas y pendientes. | ☐ |
| No se enviaron comunicaciones ni se actualizaron tareas reales. | ☐ |


### Prueba positiva y control de errores

**Caso positivo:** aparecen dos fuentes, ambas propuestas de fecha y un cambio entre ellas, sin aprobación confirmada. **Caso alterno:** dos notas manuales pueden servir para consolidación si están etiquetadas, pero no demuestran generación de Facilitator. **Fallo:** borrar el antecedente del 20/11/2026 o atribuir autoría de IA a notas pegadas.

## Solución de Problemas

| Situación | Qué hacer |
| :--- | :--- |
| No aparecen notas de Facilitator | Confirma que fueron reuniones programadas con Facilitator habilitado y que la cuenta tiene acceso. Sin notas reales, aplica la contingencia manual y señala cobertura parcial. |
| No hay transcripciones | Usa las notas disponibles; no afirmes que se revisó una transcripción inexistente. |
| Copilot no localiza Loop o mezcla reuniones | Adjunta/pega las dos notas por separado con identificador y fecha; pide referencias por fila. |
| Copilot asigna compromisos a una persona equivocada | Abre la nota de origen, corrige el registro y marca la atribución como pendiente si es ambigua. |

## Limpieza

1. Conserva enlaces y minuta exclusivamente en el espacio autorizado. No modifiques las notas históricas de Facilitator para ajustarlas a una respuesta de IA.
2. Elimina las páginas manuales de simulación si no se requieren más y cuentas con permisos.
3. Si guardaste un prompt, retira nombres o referencias privadas antes de compartirlo.

## Resumen

El instructor mostró cómo convertir información de varias reuniones en un seguimiento verificable, cómo detectar cambios en compromisos y cómo preparar una matriz de próximas acciones con validación humana.

**Referencia oficial:** [Facilitator en reuniones de Microsoft Teams](https://support.microsoft.com/es-es/teams/copilot/facilitator-in-microsoft-teams-meetings).
