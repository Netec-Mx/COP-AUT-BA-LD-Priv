# Práctica: Investigación y consolidación de información con Researcher

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| Duración | 17 minutos |
| Complejidad | Media |
| Nivel de Bloom | Aplicar, analizar y evaluar |
| Tipo de actividad | Demostración guiada por el instructor; primera parte de una secuencia integrada del capítulo 3 |
| Aplicaciones | Microsoft 365 Copilot Chat y agente Researcher |
| Producto | Hallazgos con referencias, límites de la investigación y resumen listo para la fase de análisis |


### Distribución de tiempo (sin preparación previa)

| Paso | Trabajo | Minutos |
| :---: | :--- | ---: |
| 1 | Delimitar pregunta | 3 |
| 2 | Abrir Researcher | 2 |
| 3 | Investigar y verificar enlaces | 9 |
| 4 | Transferir hallazgos | 3 |
| **Total** | | **17** |

## Descripción General

Se utilizará Researcher para investigar prácticas actuales de seguimiento y priorización de solicitudes de trabajo, reuniendo fuentes verificables y distinguiendo hechos de recomendaciones. El resultado será una base de investigación para analizar después los datos didácticos del capítulo con Analyst. **Esta práctica no concluye el escenario:** la conversación y sus resultados deben conservarse para las dos demostraciones siguientes.


### Caso de investigación: mejorar el seguimiento de solicitudes internas

**Rol:** analista encargado de recomendar un método de clasificación y seguimiento para un conjunto didáctico de solicitudes internas. El proceso incluye solicitudes **abiertas/cerradas**, prioridades, días en seguimiento, responsables y excepciones documentales. En la práctica siguiente, Analyst procesará una tabla de **12 registros simulados** que está incluida en este capítulo. No se necesita conocer ninguna empresa, industria, presupuesto o indicador real.

| Elemento del caso | Definición para la investigación |
| :--- | :--- |
| Problema | ¿Cómo hacer un seguimiento rastreable de solicitudes sin inventar estados ni compromisos? |
| Temas a investigar | Registro, priorización, evidencias, excepciones y supervisión humana. |
| Fuentes preferidas | Documentación oficial, publicaciones institucionales y fuentes primarias accesibles. |
| Periodo | Información vigente al ejecutar la actividad; preferir últimos 12 meses cuando sea pertinente. |
| Relación con Analyst | El resultado de Researcher aportará **criterios conceptuales**; la tabla de 12 registros aportará **hechos numéricos**. |
| Entregable | Hallazgos citados, recomendaciones diferenciadas y resumen de máximo 180 palabras. |

**Instrucción de enlace:** no pegues todavía los 12 registros en Researcher si el objetivo es investigar buenas prácticas, y no le atribuyas a Researcher los recuentos que aún no ha calculado Analyst. Si solo puedes abrir cada agente en hilos distintos, guarda el resumen con sus fuentes y pégalo de forma explícita al pasar a Analyst.

**Ejemplo de hallazgo verificable:** una guía oficial que describa cómo identificar responsables o registrar el estado de una tarea, acompañada del enlace que respalde esa función. **No** se considera hallazgo comprobado una estadística o «mejora de productividad» inventada.

## Objetivos de Aprendizaje

1. Formular una investigación con objetivo, periodo, criterios y fuentes identificables.
2. Obtener y contrastar hallazgos relevantes mediante Researcher.
3. Preparar un resumen rastreable para la etapa posterior con Analyst.

## Prerrequisitos

- Licencia de Microsoft 365 Copilot que incluya Researcher y acceso al agente habilitado por la organización.
- Búsqueda web autorizada cuando se usen fuentes públicas, con tiempo suficiente para una investigación profunda.
- La tabla de **12 solicitudes didácticas** ya está incluida íntegramente en esta guía, dentro de la demostración con Analyst. No se descarga ningún archivo de recursos.

## Entorno de Laboratorio

| Componente | Verificación |
| :--- | :--- |
| [Microsoft 365 Copilot](https://m365.cloud.microsoft/chat) | El instructor ha iniciado sesión con identidad de trabajo y puede crear una conversación. |
| Researcher | Está visible en **Agentes** o aparece al escribir `@` y seleccionar Researcher en el cuadro de Copilot Chat. |
| Fuentes | Navegación y referencias a fuentes públicas permitidas; se prioriza Microsoft Learn/Support para funcionalidades de Microsoft. |
| Datos | La tabla de solicitudes simuladas se copiará desde el apartado de Analyst de este mismo README, sin descargar ningún recurso. |

> [!TIP]
> En la interfaz compatible, incorporar `@Researcher` mediante el selector en la **misma conversación de Copilot Chat** facilita conservar el hilo para Analyst. Si tu versión solo abre al agente en un hilo independiente, copia el resumen verificado al nuevo hilo: no supongas que existe transferencia automática.

## Instrucciones Paso a Paso

### Paso 1: Preparación del escenario y delimitación de la investigación

**Tiempo estimado: 3 minutos.**

1. Abre una **nueva conversación** en Microsoft 365 Copilot Chat con la cuenta autorizada.
2. Lee la ficha **«Caso de investigación: mejorar el seguimiento de solicitudes internas»**, incluida antes de Objetivos. Utiliza su pregunta central: «¿Cómo hacer un seguimiento rastreable de solicitudes sin inventar estados ni compromisos?». No tienes que proponer una empresa ni buscar un archivo.
3. Decide que las fuentes deben permitir comprobar la fecha y el respaldo de cada afirmación; si una fuente no declara su fecha, no la presentes como publicación reciente.
4. Si la interfaz dispone de **Work IQ**, revisa su estado y qué fuentes son apropiadas; este caso puede investigarse con fuentes públicas sin revelar datos internos.

**Criterio de avance:** la pregunta de investigación está delimitada y no depende de un proyecto empresarial ficticio.

### Paso 2: Acceso e inicio del Agente Researcher en Copilot

**Tiempo estimado: 2 minutos.**

1. En el cuadro de la conversación, escribe `@` y selecciona **Researcher** de la lista de herramientas/agentes, si está disponible.
2. Si el menú no contiene Researcher, abre **Agentes > Researcher** y documenta que el resultado se transferirá manualmente al continuar con Analyst.
3. Verifica que el nombre de Researcher aparece como herramienta seleccionada **antes** de enviar el prompt.

**Criterio de avance:** la solicitud será procesada por Researcher, no por el chat general sin indicarlo.

### Paso 3: Ejecución de la consulta híbrida parametrizada

**Tiempo estimado: 9 minutos.**

> [!IMPORTANT]
> **PROMPT 1 — Investigación de prácticas de seguimiento**

```text
Investiga buenas prácticas actuales para registrar, priorizar y dar seguimiento a solicitudes internas recurrentes, con apoyo de Microsoft 365 Copilot y supervisión humana.
Alcance: captura de solicitudes, evidencia del estado, seguimiento de compromisos, trazabilidad, priorización y tratamiento de excepciones.
Prioriza documentación oficial y fuentes originales; considera publicaciones de los últimos 12 meses cuando existan. No descartes automáticamente material vigente anterior, pero identifica su antigüedad.
Entrega:
1. Cuatro o cinco hallazgos verificables, con fuente y fecha cuando estén disponibles.
2. Tres recomendaciones aplicables a un proceso de seguimiento de solicitudes, claramente etiquetadas como recomendaciones.
3. Riesgos y límites de automatizar decisiones sin verificación humana.
4. Tabla Fuente | Organización | Fecha | Afirmación respaldada | Enlace.
5. Un resumen de transferencia de máximo 180 palabras para orientar el análisis de una tabla de 12 solicitudes simuladas que aparece en la sección siguiente de este mismo capítulo. El resumen solo aporta criterios conceptuales, NO recuentos no calculados.
No inventes cifras de productividad, casos de éxito, empresas ni políticas de una organización.
```

1. Envía el PROMPT 1 a Researcher y responde a preguntas de aclaración, si aparecen, manteniendo el mismo alcance.
2. Espera hasta que Researcher finalice. Una investigación profunda puede tardar más que un mensaje habitual; no declares éxito antes de ver la respuesta.
3. Abre al menos **dos** referencias citadas. Comprueba que cada enlace realmente respalda la afirmación atribuida.
4. Marca cualquier cifra sin evidencia, fuente secundaria de baja confiabilidad o dato con vigencia dudosa como «Requiere confirmación».

**Criterio de avance:** hay hallazgos respaldados por fuentes accesibles y recomendaciones identificadas como tales.

### Paso 4: Consolidar el resumen de transferencia

**Tiempo estimado: 3 minutos.**

> **PROMPT 2 — Handoff verificable**
>
> `Redacta el resumen de transferencia usando solo los hallazgos validados de esta investigación. Incluye: hallazgo | fuente | recomendación relacionada | límite de aplicación. No agregues nuevos hechos ni datos. Máximo 180 palabras.`

1. Ejecuta PROMPT 2 en el mismo hilo.
2. Copia el resumen y sus fuentes a una nota temporal autorizada, pues es el insumo para Analyst si el entorno no conserva contexto entre herramientas.
3. No cierres la conversación; continúa con la segunda demostración de este capítulo.

## Validación y Pruebas

| Criterio objetivo | Estado |
| :--- | :---: |
| La solicitud se ejecutó en Researcher. | ☐ |
| Se presentaron fuentes rastreables y al menos dos se contrastaron manualmente. | ☐ |
| El resultado separa hallazgos de recomendaciones. | ☐ |
| Se señalan limitaciones de vigencia o evidencia cuando existen. | ☐ |
| El resumen para Analyst está disponible y no incluye hechos inventados. | ☐ |


### Prueba positiva y control de errores

**Caso positivo:** se verifican manualmente al menos dos enlaces que respaldan sus afirmaciones; las recomendaciones no se presentan como fuentes ni se atribuyen cifras al CSV aún no analizado. **Fallo:** enlace inexistente, dato sin fecha presentado como reciente o recomendación tratada como compromiso real.

## Solución de Problemas

| Situación | Qué hacer |
| :--- | :--- |
| Researcher no aparece | Revisa licencia, agentes permitidos y despliegue. No sustituyas la demostración por un supuesto resultado de Researcher. |
| La investigación tarda más de lo previsto | Preinicia una ejecución de prueba antes de clase; espera la salida completa para evaluar fuentes. |
| Una cita lleva a material distinto | Descarta esa afirmación o sustitúyela por una fuente oficial comprobada y explícitamente enlazada. |
| No se conserva el mismo hilo de conversación | Copia el resumen verificado y sus referencias; pégalo en el hilo siguiente como insumo explícito. |

## Limpieza

1. Conserva temporalmente el resumen y las referencias, pues las siguientes demostraciones los utilizarán.
2. No compartas información de trabajo sin autorización ni elimines el hilo antes de completar el reporte ejecutivo.

## Resumen

Se investigó un proceso de seguimiento de solicitudes mediante Researcher, se verificaron fuentes y se generó un resumen de hallazgos listo para contrastarlo con datos estructurados en Analyst.

**Referencia oficial:** [Primeros pasos con Researcher](https://support.microsoft.com/en-us/microsoft-365-copilot/get-started-with-researcher-in-microsoft-365-copilot).

---

# Práctica: Análisis de información y gestión de excepciones con Analyst

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| Duración | 18 minutos |
| Complejidad | Media |
| Nivel de Bloom | Aplicar, analizar y evaluar |
| Tipo de actividad | Demostración guiada por el instructor; segunda parte de la secuencia integrada |
| Aplicaciones | Microsoft 365 Copilot Chat, agente Analyst y tabla de datos integrada en esta guía |
| Producto | Recuento validado, patrones, excepciones y tabla de prioridades basada en datos |


### Distribución de tiempo (sin preparación previa)

| Paso | Trabajo | Minutos |
| :---: | :--- | ---: |
| 1 | Copiar el CSV integrado | 4 |
| 2 | Activar Analyst y cargar datos | 3 |
| 3 | Analizar y validar recuentos | 8 |
| 4 | Preparar transferencia | 3 |
| **Total** | | **18** |

## Descripción General

Analyst analizará los **12 registros simulados incluidos más abajo en esta guía**, sin descargar archivos. Se aprovecharán los criterios generales investigados con Researcher sin asumir que ambos agentes comparten automáticamente fuentes. El instructor contrastará las cifras principales con las filas copiadas, identificará excepciones y distinguirá observaciones de recomendaciones.

### Caso analítico: 12 solicitudes internas simuladas

**Situación.** Continúas el estudio del seguimiento de solicitudes internas. Ahora recibes una tabla de **12 casos ficticios** (`SOL-001` a `SOL-012`) con área, tipo, estado, prioridad, responsable, días, fechas y observaciones. El objetivo es responder **qué hay en los datos**, no atribuirles causas, políticas o resultados no registrados.

**Diccionario de los campos que vas a pegar:**

| Columna | Qué significa en este ejercicio | Precaución al analizar |
| :--- | :--- | :--- |
| `ID` | Identificador único del registro. | No inventar ni modificar identificadores. |
| `Area`, `Tipo` | Clasificación descriptiva didáctica. | No inferir empresa o estructura real. |
| `Estado` | `Abierta` o `Cerrada`, literal del CSV. | No inferir cumplimiento o resolución de la causa. |
| `Prioridad` | `Alta`, `Media` o `Baja`, literal del CSV. | No deducir reglas organizacionales no especificadas. |
| `Responsable` | Rol didáctico o `Sin asignar`. | No sustituir por nombres reales. |
| `Dias_pendiente` | Días de seguimiento declarados en el dato simulado. | No recalcularlos usando la fecha actual; también pueden existir en casos cerrados. |
| `Fecha_compromiso` | Fecha anotada en el registro. | No equivale necesariamente a un acuerdo validado. |
| `Fecha_cierre` | Fecha registrada del cierre, que puede estar vacía. | Valor vacío significa *no informado*, no `0` o «hoy». |
| `Observacion` | Nota proporcionada con el registro. | No convertirla en diagnóstico causal. |

**Qué debes detectar obligatoriamente:** 12 registros; 7 `Abierta`; 5 `Cerrada`; 3 `Abierta` + `Alta` (`SOL-002`, `SOL-009`, `SOL-011`); un `Sin asignar` (`SOL-009`); y un `Cerrada` sin fecha de cierre (`SOL-003`). Entre las abiertas de prioridad alta, el orden por días descendentes es `SOL-011 (16) → SOL-009 (13) → SOL-002 (8)`.

**Fuente única de datos:** copia el bloque CSV que se encuentra **más abajo en esta práctica**, en `Entorno de Laboratorio > Datos didácticos para copiar y pegar`. No necesitas descargar ningún archivo. En casos en los que Analyst solo admita adjuntos, la guía explica cómo crear un CSV temporal con ese mismo texto, sin recursos distribuidos.

## Objetivos de Aprendizaje

1. Proporcionar a Analyst una tabla de datos reproducible, copiándola directamente de la guía y verificando su interpretación.
2. Analizar estados, prioridades y excepciones con Analyst.
3. Validar cálculos y crear un registro de hallazgos priorizados con evidencia.

## Prerrequisitos

- Capacidad de usar el agente **Analyst** con licencia de Microsoft 365 Copilot y permisos correspondientes.
- Haber terminado la investigación del apartado anterior o disponer de su resumen verificado.
- Disponer de la tabla de **12 registros** incluida en el apartado «Datos didácticos para copiar y pegar» de esta práctica. No se requieren descargas ni archivos preparados.

## Entorno de Laboratorio

| Elemento | Verificación |
| :--- | :--- |
| Analyst | Disponible en **Agentes** o como herramienta seleccionable en Copilot Chat. |
| Tabla de trabajo | Un bloque CSV de texto **dentro de esta misma guía**, con identificadores `SOL-001` a `SOL-012`. No existe recurso externo. |
| Contexto de investigación | Resumen del PROMPT 2 de Researcher, con referencias revisadas. |
| Tratamiento de datos | Son datos expresamente simulados; no contienen personas, clientes ni información real. |

<details>
<summary>Control rápido de los 12 registros antes de empezar</summary>

| Métrica verificable | Valor de control |
| :--- | ---: |
| Solicitudes totales | 12 |
| Estado `Abierta` | 7 |
| Estado `Cerrada` | 5 |
| Solicitudes abiertas con prioridad `Alta` | 3 |
| Registros con responsable `Sin asignar` | 1 |
| Registros cerrados sin `Fecha_cierre` | 1 |

No se exige que Analyst entregue siempre la misma redacción, pero sí deben coincidir estos recuentos si analiza las 12 filas correctamente.

</details>

### Datos didácticos para copiar y pegar (sin archivo de recursos)

> [!IMPORTANT]
> Este es el **único conjunto de datos de la demostración**. Son **12 solicitudes simuladas**, no registros empresariales. El bloque usa comas como separadores y la primera línea como encabezado. Las fechas son parte del escenario ficticio y **no** deben actualizarse automáticamente.

1. Expande este apartado, localiza el bloque `csv` y copia su contenido **desde `ID,Area,...` hasta `SOL-012,...`**, sin incluir los tres acentos graves (` ``` `) que delimitan el bloque Markdown.
2. Se utilizará **primero pegado directo** en el mensaje de Analyst (paso 2). Solo si el agente no interpreta los 12 registros se creará un CSV **temporalmente a partir del mismo texto** con el procedimiento alternativo del paso 2. **No se distribuye ningún archivo adicional.**

<details open>
<summary>Mostrar el conjunto de 12 solicitudes (seleccionar y copiar)</summary>

```csv
ID,Area,Tipo,Estado,Prioridad,Responsable,Dias_pendiente,Fecha_compromiso,Fecha_cierre,Observacion
SOL-001,Administracion,Reporte,Cerrada,Media,Rol A,2,2026-11-10,2026-11-09,Entregado
SOL-002,Operaciones,Seguimiento,Abierta,Alta,Rol B,8,2026-11-17,,En revision
SOL-003,Administracion,Reporte,Cerrada,Media,Rol A,4,2026-11-12,,Falta evidencia de fecha de cierre
SOL-004,Servicios,Comunicación,Abierta,Baja,Rol C,3,2026-11-19,,Pendiente de respuesta
SOL-005,Operaciones,Seguimiento,Cerrada,Alta,Rol B,5,2026-11-11,2026-11-11,Completado
SOL-006,Servicios,Reporte,Abierta,Media,Rol C,6,2026-11-20,,Falta validacion
SOL-007,Administracion,Seguimiento,Abierta,Media,Rol A,7,2026-11-18,,Pendiente de confirmacion
SOL-008,Operaciones,Comunicación,Cerrada,Baja,Rol B,1,2026-11-10,2026-11-10,Atendido
SOL-009,Servicios,Seguimiento,Abierta,Alta,Sin asignar,13,2026-11-16,,Responsable pendiente
SOL-010,Operaciones,Reporte,Cerrada,Media,Rol B,3,2026-11-13,2026-11-13,Entregado
SOL-011,Administracion,Seguimiento,Abierta,Alta,Rol A,16,2026-11-15,,Prioridad alta sin cierre
SOL-012,Servicios,Comunicación,Abierta,Baja,Rol C,2,2026-11-24,,En preparacion
```

</details>

**Comprobación visual:** debe existir una línea de encabezados y **12** líneas de datos; el primer identificador es `SOL-001` y el último `SOL-012`. Las celdas vacías entre dos comas son datos ausentes que no deben completarse por suposición.

## Instrucciones Paso a Paso

### Paso 1: Creación y carga del conjunto de datos de prueba

**Tiempo estimado: 4 minutos.**

1. En «Datos didácticos para copiar y pegar», localiza el bloque de **12 registros** de esta guía. No busques archivos descargables: **todo el contenido está aquí**.
2. Revisa la línea de encabezados (`ID,Area,Tipo,...`) y confirma el intervalo `SOL-001` a `SOL-012` y las celdas de `Fecha_cierre` vacías.
3. Copia **solo las 13 líneas** del bloque CSV (encabezado + 12 registros), sin los delimitadores Markdown. Mantén sin alteración comas, acentos, identificadores y valores vacíos.
4. Conserva los datos copiados para pegarlos en el agente Analyst en el paso 2. Si el navegador no permite copiarlos fácilmente, expande el bloque desplegable y selecciona el texto desde la primera hasta la última línea.

**Criterio de avance:** el conjunto completo está listo para pegarse y se identificaron sus 12 filas. No se necesita recurso externo ni enlace de descarga.

### Paso 2: Activación e invocación del agente Analyst en Microsoft 365 Copilot

**Tiempo estimado: 3 minutos.**

1. Abre **Analyst** desde **Agentes** de Microsoft 365 Copilot, o selecciona **Analizar datos / Analyst** en el menú de capacidades de Copilot Chat (según tu interfaz). Verifica el nombre de la capacidad activa: escribir `@Analyst` sin seleccionarla **no** asegura la invocación.
2. **Opción principal, sin archivos:** en el cuadro de entrada de Analyst escribe `Voy a proporcionarte 12 registros CSV didácticos. Úsalos como única base de datos. Indica si identificas 12 filas y 10 columnas; no infieras información faltante.`, pega a continuación las **13 líneas** copiadas del apartado «Datos didácticos», y envía el mensaje. Si trabajas en un hilo diferente al de Researcher, pega también **por separado** el resumen y las fuentes verificadas de Researcher, etiquetándolos `CONTEXTO_RESEARCHER` (solo para recomendaciones conceptuales).
3. Comprueba que Analyst reconoce **12 filas de datos**, **10 columnas** y los IDs del `SOL-001` al `SOL-012`. Si logra leerlos, continúa al paso 3; **no crees archivos**.
4. **Solo si no reconoce la tabla pegada:** abre un editor de texto sin formato (por ejemplo, Bloc de notas), pega **solo las 13 líneas CSV** de esta guía y guárdalas temporalmente como `solicitudes_simuladas.csv`, seleccionando **UTF-8** y, cuando se solicite, tipo **Todos los archivos** para evitar la extensión `.txt`. Vuelve a Analyst, elige **+ / Adjuntar contenido > Cargar desde este dispositivo** (o la opción equivalente), selecciona el archivo recién creado y verifica su nombre. Este CSV es un **archivo de trabajo generado durante la práctica**, no un recurso suministrado por el repositorio; puedes borrarlo tras el ejercicio.


**Criterio de avance:** Analyst ha reconocido los **12 registros y 10 columnas**, por texto pegado o —solo si fue necesario— mediante archivo temporal construido de esta guía. Los resultados de Researcher, si se reutilizan, están identificados como fuente conceptual independiente.

### Paso 3: Análisis de anomalías y gestión de excepciones mediante prompts avanzados

**Tiempo estimado: 8 minutos.**

> [!IMPORTANT]
> **PROMPT 1 — Análisis reproducible de los 12 registros**

```text
Analiza únicamente los 12 registros DIDÁCTICOS que acabo de proporcionarte, pegados en la conversación o mediante el archivo CSV temporal que he adjuntado si el pegado directo no funcionó. No son solicitudes de una organización real.
1. Confirma que hay exactamente 12 filas de datos y 10 columnas con los encabezados ID, Area, Tipo, Estado, Prioridad, Responsable, Dias_pendiente, Fecha_compromiso, Fecha_cierre y Observacion.
2. Calcula total de solicitudes, recuentos por Estado y solicitudes abiertas con Prioridad Alta.
3. Identifica registros cerrados sin Fecha_cierre y registros con Responsable = "Sin asignar".
4. Ordena las solicitudes abiertas de prioridad Alta por Dias_pendiente descendente. Muestra ID, Area, días, Responsable y Observacion.
5. Presenta una tabla ID | Hallazgo observable | Evidencia (columna/valor) | Riesgo sugerido | Acción propuesta.
6. Distingue las recomendaciones conceptuales de Researcher de los hechos de esta tabla: no atribuyas fuentes web o políticas empresariales a los registros.
7. No completes fechas de cierre, responsables, causas o resultados faltantes. Ante ausencia de datos escribe "Pendiente de confirmar".
Antes de concluir, muestra recuentos y los IDs usados para calcularlos.
```

1. Ejecuta PROMPT 1 con Analyst y espera el análisis completo.
2. Contrasta los resultados con «Control rápido de los 12 registros», situado inmediatamente antes del CSV. Debes obtener **12 registros, 7 abiertos, 5 cerrados, 3 abiertos de prioridad alta, 1 sin responsable y 1 cierre sin fecha**. Los casos de prioridad alta abierta deben aparecer ordenados por días: **SOL-011 (16), SOL-009 (13), SOL-002 (8)**.
3. Revisa los casos de control: `SOL-003` carece de fecha de cierre a pesar de figurar como cerrada; `SOL-009` no tiene responsable asignado; `SOL-011` es una solicitud abierta de prioridad alta con `16` días pendientes.
4. Verifica que «riesgo sugerido» no se presenta como incidente confirmado. `Dias_pendiente` es un valor de corte simulado, **no** un cálculo a realizar desde la fecha actual; tampoco demuestra incumplimiento por sí mismo.
5. Si hay error de cálculo, solicita ver las filas que generaron el recuento:

   > **PROMPT 2 — Revisión de cómputos**
   >
   > `Recalcula solo con las 12 filas que proporcioné, bien pegadas en esta conversación o mediante un CSV temporal. Muestra qué IDs integran cada recuento, verifica los filtros Estado y Prioridad y explica cualquier diferencia sin cambiar los datos originales.`

**Criterio de avance:** los recuentos concuerdan y cada excepción remite a un registro identificable.

### Paso 4: Preparar el material para el reporte ejecutivo

**Tiempo estimado: 3 minutos.**

1. En el mismo hilo solicita: `Resume en una tabla los tres hallazgos operativos más importantes, con ID, evidencia de los 12 registros didácticos, limitación del dato y próximo paso recomendado. No añadas conclusiones nuevas.`
2. Conserva la tabla y los recuentos. Si cambias de hilo, copia explícitamente el resumen con sus **IDs**, valores de control y la mención `Fuente: 12 registros didácticos incluidos en el README del capítulo 3`. No supongas que otro chat conoce automáticamente el contenido pegado.
3. Continúa con «Generación de un reporte ejecutivo a partir del trabajo de los agentes».

## Validación y Pruebas

| Comprobación | Estado |
| :--- | :---: |
| El agente utilizado fue Analyst y reconoció los 12 registros de esta guía, pegados directamente o aportados en CSV temporal. | ☐ |
| Los seis controles numéricos del cuadro desplegable coinciden. | ☐ |
| Se localizaron explícitamente `SOL-003`, `SOL-009` y `SOL-011`. | ☐ |
| Las acciones propuestas se distinguen de hechos del CSV. | ☐ |
| No se incorporaron responsables, causas o fechas inventadas. | ☐ |
| Quedó un resumen reutilizable para el reporte. | ☐ |


### Prueba positiva y control de errores

**Caso positivo:** 12 totales, 7 abiertas, 5 cerradas; las abiertas de prioridad alta son SOL-002, SOL-009 y SOL-011; SOL-003 carece de Fecha_cierre y SOL-009 de responsable asignado. **Fallo:** calcular los días desde la fecha real de la clase, completar celdas vacías o presentar causas no documentadas.

## Solución de Problemas

| Situación | Qué hacer |
| :--- | :--- |
| Analyst no interpreta los datos pegados | Utiliza el procedimiento alternativo del paso 2: crea un CSV temporal copiando **el bloque integrado en esta guía**, adjúntalo a Analyst y repite PROMPT 1. Si ambos modos fallan, registra la limitación del entorno; no presentes un análisis de Copilot Chat general como si fuera Analyst. |
| El recuento no coincide | Confirma que solo se copiaron 13 líneas (1 encabezado y 12 datos), que las comas no se perdieron y que los campos vacíos se respetaron. Ejecuta PROMPT 2. |
| Analyst toma una recomendación web como dato de la tabla | Indica «usa Researcher solo como marco conceptual; la base numérica es únicamente la tabla de 12 registros didácticos». |
| Se interpretan fechas de los registros como plazos actuales | Aclara que son fechas fijas de un conjunto didáctico y no deben actualizarse automáticamente. |

## Limpieza

1. Conserva el resumen verificado de Analyst para la demostración del reporte ejecutivo. Si necesitaste crear un CSV temporal, puedes eliminarlo al terminar de utilizarlo; **no existe un archivo original que deba conservarse**.
2. No subas datos empresariales reales a un repositorio público ni asignes acciones a personas por una simulación.

## Resumen

Se aplicó Analyst a 12 registros de solicitudes incorporados en la propia guía, se identificaron excepciones con IDs concretos y se respaldaron las recomendaciones con datos y revisión humana.

**Referencia oficial:** [Primeros pasos con Analyst](https://support.microsoft.com/es-es/microsoft-365-copilot/get-started-with-analyst-in-microsoft-365-copilot).

---

# Práctica: Generación de un reporte ejecutivo a partir del trabajo de los agentes

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| Duración | 15 minutos |
| Complejidad | Media |
| Nivel de Bloom | Analizar, evaluar y crear |
| Tipo de actividad | Demostración guiada por el instructor; tercera parte de la secuencia integrada |
| Aplicaciones | Microsoft 365 Copilot Chat, resultados de Researcher y Analyst, Copilot Pages / Word cuando estén disponibles |
| Producto | Reporte ejecutivo estructurado con hallazgos, excepciones y recomendaciones diferenciadas |


### Distribución de tiempo (sin preparación previa)

| Paso | Trabajo | Minutos |
| :---: | :--- | ---: |
| 1 | Reunir Researcher y Analyst | 4 |
| 2 | Ver estructura | 3 |
| 3 | Redactar y revisar | 5 |
| 4 | Guardar editable | 3 |
| **Total** | | **15** |

## Descripción General

A partir de la investigación de Researcher y del análisis cuantitativo de Analyst, se elaborará un reporte ejecutivo basado en una estructura previamente definida. El reporte conservará las fuentes, distinguirá hechos de recomendaciones e indicará qué aspectos requieren validación antes de utilizar el contenido.

### Contexto y traspaso entre herramientas

**Situación.** Debes informar a una persona responsable sobre cómo mejorar el seguimiento de solicitudes internas. Para ello combinas dos evidencias distintas: (a) información pública investigada con **Researcher** y validada mediante enlaces, y (b) análisis de **12 registros didácticos** realizado con **Analyst**. El reporte no representa a una empresa o cliente real.

| Información necesaria | Origen exacto | Qué hacer si falta |
| :--- | :--- | :--- |
| 3–5 hallazgos externos, organización y URL | Respuesta de Researcher de esta sección del capítulo 3. | Volver a esa conversación y copiar solo lo verificado; si no se ejecutó, marcar investigación no realizada. |
| Recuentos `12 total`, `7 abiertas`, `5 cerradas`, `3 abiertas + Alta` | Bloque CSV y salida revisada de Analyst de este capítulo. | Comprobar directamente los registros integrados en la práctica Analyst. |
| Excepciones `SOL-003`, `SOL-009`, `SOL-011` | Registros didácticos y análisis de Analyst. | Usar los IDs y valores del CSV; no inferir razones. |
| Plantilla de reporte | Tabla del Paso 2 y PROMPT 1 de esta práctica. | No buscar plantillas externas. |

**Bloque listo para transferir.** Si Researcher y Analyst aparecen en conversaciones distintas, inicia un chat nuevo y pega el siguiente bloque, sustituyendo solo el texto entre corchetes por hallazgos de Researcher que hayas verificado. Las cifras y excepciones de Analyst ya están definidas:

```text
ESTADO DEL EJERCICIO: conjunto de datos SIMULADO, no de una empresa real.
FUENTES_RESEARCHER: [PEGAR AQUÍ los hallazgos verificados, con organismo, fecha y enlace; si no se ejecutó Researcher, escribir «Investigación no realizada»].
DATOS_ANALYST: 12 solicitudes; 7 abiertas; 5 cerradas; 3 abiertas de prioridad Alta (SOL-002, SOL-009 y SOL-011).
EXCEPCION_1: SOL-003 consta Cerrada y su Fecha_cierre está vacía.
EXCEPCION_2: SOL-009 consta Abierta y tiene Responsable = Sin asignar.
EXCEPCION_3: SOL-011 consta Abierta, Alta y 16 Dias_pendiente.
LIMITACION: las fechas del CSV y los días son datos didácticos; no calcular incumplimientos con respecto a la fecha actual.
```

**Resultado esperado:** reporte con cinco secciones, números trazables e hipótesis/recomendaciones etiquetadas. Si no se pudo ejecutar Researcher, deja **sin acreditar** la sección de hallazgos externos; el bloque anterior no reemplaza la demostración del agente.

## Objetivos de Aprendizaje

1. Integrar los productos de dos agentes sin perder procedencia.
2. Presentar un resumen ejecutivo consistente con las cifras verificadas.
3. Producir y revisar un reporte que diferencie hechos, excepciones y acciones sugeridas.

## Prerrequisitos

- Haber completado los dos ejercicios anteriores de este capítulo, o contar con sus resultados debidamente verificados.
- Disponer de la conversación en la que se utilizó Researcher y Analyst, o haber copiado sus resultados a un lugar autorizado.
- Permiso para usar **Copilot Pages** y **Word** si se decide conservar el documento como archivo editable.

## Entorno de Laboratorio

| Insumo | Procedencia |
| :--- | :--- |
| Hallazgos y fuentes | Resumen verificado de la demostración Researcher de este capítulo. |
| Cifras y excepciones | Análisis de los **12 registros didácticos incluidos en esta misma guía**, en la demostración Analyst. |
| Estructura de reporte | Plantilla de secciones incluida en el PROMPT 1; no se necesita archivo externo. |
| Edición opcional | Microsoft Copilot Pages y Word web con la cuenta autorizada. |

## Instrucciones Paso a Paso

### Paso 1: Consolidar los resultados de Researcher y Analyst

**Tiempo estimado: 4 minutos.**

1. Vuelve a la conversación de las dos demostraciones anteriores.
2. Identifica qué fragmentos son resultados de Researcher (hallazgos, enlaces y fechas) y cuáles proceden de Analyst (recuentos, IDs y tablas).
3. Si ambos agentes no quedaron en el mismo hilo, abre una nueva conversación de **Copilot Chat general** y copia allí el **«Bloque listo para transferir»** del apartado «Contexto y traspaso entre herramientas», situado al principio de esta práctica. Sustituye `[PEGAR AQUÍ...]` por hallazgos verificados de Researcher, con sus URLs; conserva los datos ya completos de Analyst.
4. Comprueba los valores **12 registros, 7 abiertos, 5 cerrados, 3 abiertas y de prioridad Alta**, y las excepciones `SOL-003`, `SOL-009` y `SOL-011`. Si no se pudo ejecutar Researcher, marca esa parte del informe como **«Investigación no realizada; pendiente de completar»**, sin simular fuentes. No declares que integraste dos agentes si solo usaste uno.

**Criterio de avance:** Copilot tiene en el hilo ambos resultados o una transferencia explícita de los dos bloques.

### Paso 2: Aplicar una plantilla ejecutiva definida

**Tiempo estimado: 3 minutos.**

1. Utiliza esta estructura fija (no una plantilla inventada por Copilot):

   | Sección | Contenido exigido |
   | :--- | :--- |
   | 1. Resumen ejecutivo | Alcance y tres mensajes clave, sin cifras no verificadas |
   | 2. Hallazgos de investigación | Ideas principales con fuente web identificable |
   | 3. Resultados del análisis | Recuentos y excepciones con IDs del CSV |
   | 4. Riesgos y validaciones | Información que exige confirmación humana |
   | 5. Recomendaciones y siguientes pasos | Acciones sugeridas diferenciadas de compromisos existentes |

2. Comprueba que las fuentes de Researcher y los IDs de los 12 registros de esta guía pueden citarse sin ambigüedad.

### Paso 3: Ejecución del prompt estructurado y generación del reporte

**Tiempo estimado: 5 minutos.**

> [!IMPORTANT]
> **PROMPT 1 — Reporte ejecutivo integrado**

```text
Usa EXCLUSIVAMENTE los resultados verificados de Researcher y Analyst disponibles en esta conversación. No investigues ni agregues nuevas cifras.
Redacta un reporte ejecutivo sobre el seguimiento de solicitudes internas usando exactamente cinco secciones:
1. Resumen ejecutivo (máximo 120 palabras).
2. Hallazgos de la investigación: 3 a 5, con enlaces o referencias originales de Researcher.
3. Análisis de solicitudes: total, abiertas, cerradas, abiertas de prioridad alta y tres excepciones de los 12 registros simulados con sus IDs.
4. Riesgos, incertidumbres y puntos que requieren validación humana.
5. Recomendaciones y próximos pasos: hasta cuatro, claramente marcados como propuestas.
No presentes ejemplos simulados como hechos reales de una organización. No cambies los recuentos verificados, no inventes responsables, ahorro de tiempo, decisiones o fechas. Si falta una fuente, escribe "Fuente pendiente de verificar".
Incluye una nota al principio: "Ejercicio didáctico con datos simulados; revisar antes de cualquier aplicación real".
```

1. Desactiva la herramienta especial (Researcher o Analyst), si permanece seleccionada, para continuar con **Copilot Chat** general en el mismo hilo, o usa una conversación nueva con los dos bloques ya copiados.
2. Ejecuta PROMPT 1, revisa los cinco encabezados y verifica que se citan las fuentes correctas.
3. Contrasta que el informe contiene **12 solicitudes**, **7 abiertas**, **5 cerradas** y excepciones identificadas sin confundir recomendaciones con decisiones.

**Criterio de avance:** el reporte completo existe en el chat y su procedencia se puede revisar.

### Paso 4: Conservar el reporte como entregable editable

**Tiempo estimado: 3 minutos.**

1. Si Copilot permite **Editar en Pages**, convierte el borrador en una página y revisa las secciones.
2. Desde Copilot Pages, cuando esté disponible, selecciona **Crear > Documento > Abrir Word** para obtener un documento editable. También puedes copiar el texto validado a un documento Word en blanco y guardarlo manualmente.
3. Guarda el documento con un nombre identificable como `Reporte_Ejecutivo_Solicitudes_Simuladas.docx` en almacenamiento autorizado. Verifica que las citas y las tablas permanecen legibles.
4. No describas como generado automáticamente un documento que requirió copiar contenido manualmente.

> [!NOTE]
> La conversión de Pages a Word está documentada por Microsoft. No dependas de una conversión directa de Pages a PowerPoint: esa opción no está disponible en todos los entornos actuales.

## Validación y Pruebas

| Control | Estado |
| :--- | :---: |
| Están las cinco secciones de la plantilla. | ☐ |
| Las cifras coinciden con los 12 registros de esta guía y las excepciones conservan sus IDs. | ☐ |
| Los hallazgos externos tienen referencias o están marcados como pendientes. | ☐ |
| La sección de acciones distingue hechos y propuestas. | ☐ |
| Hay una nota visible indicando que los datos son simulados. | ☐ |
| Se conservó una copia del reporte, preferentemente editable. | ☐ |


### Prueba positiva y control de errores

**Caso positivo:** cinco secciones; 12 solicitudes (7 abiertas y 5 cerradas); cita IDs en las excepciones y URLs de Researcher solo cuando están verificadas. **Cobertura parcial:** con una única salida de agente no se considera lograda la integración de Researcher y Analyst. **Fallo:** presentar hallazgos de prueba como resultados de una empresa real.

## Solución de Problemas

| Situación | Solución |
| :--- | :--- |
| Copilot no recuerda la investigación | Copia y pega el resumen verificado de Researcher con referencias; no supongas continuidad entre hilos. |
| El reporte altera las cifras | Reenvía los recuentos verificados en la guía y solicita corrección conservando los IDs correspondientes. |
| No aparece «Editar en Pages» o «Crear documento» | Copia el resultado revisado a Word web de manera manual y conserva la estructura de cinco secciones. |
| Se omiten citas | Recupera los enlaces verificados del resultado de Researcher y marca lo no comprobado como pendiente. |

## Limpieza

1. Conserva, si procede, el reporte y las referencias en una carpeta autorizada. Si generaste un CSV temporal desde el texto de esta guía, puedes eliminarlo cuando ya no se requiera.
2. No publiques el reporte sin la nota de simulación ni lo emplees para tomar decisiones reales.
3. No borres los resultados originales de los agentes antes de verificar el reporte.

## Resumen

El instructor integró una investigación con fuentes y un análisis cuantitativo con controles en un reporte ejecutivo trazable. Se mantuvieron separados los datos documentados, sus límites y las recomendaciones.

**Referencias oficiales:** [Convertir Pages a Word](https://support.microsoft.com/es-es/microsoft-365-copilot/convert-your-microsoft-365-copilot-page-to-a-word-document) · [Respuestas de Copilot Chat](https://support.microsoft.com/en-us/microsoft-365-copilot/about-copilot-chat-responses).
