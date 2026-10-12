# Optimización de tareas recurrentes con Microsoft 365 Copilot y agentes — Setup Guide

<p align="center"><img src="assets/LogoNetec.png" alt="NETEC" width="180" /></p>

Guía consolidada de preparación del entorno para los cinco capítulos. Solo incluye requisitos necesarios o comprobaciones concretas antes de iniciar las demostraciones. **Cada práctica comienza con un escenario completo, datos de entrada listos para copiar y resultado esperado**, dentro del propio `README.md` del capítulo. **No hay archivos auxiliares de prácticas**. Los pasos de ejecución están en cada README; esta guía solo cubre configuración y comprobaciones previas.

| Curso | Clave | Versión del material | Estado de verificación | Revisión documental |
| :--- | :--- | :--- | :--- | :--- |
| Optimización de tareas recurrentes con Microsoft 365 Copilot y agentes | COP_AUT BA_LD (Priv) | 1.3 | Revisado documentalmente; **requiere validación en el tenant de impartición** | 12 de octubre de 2026 |

> [!IMPORTANT]
> Se ha contrastado la disponibilidad **documentada** de capacidades de Microsoft, pero los archivos no proporcionan credenciales ni acceso administrativo al tenant del cliente. No es correcto declarar que un flujo o un agente funciona en una cuenta particular sin ejecutar previamente la comprobación de esta guía.

## Accesos

- **Repositorio:** [https://github.com/Netec-Mx/261007-Temario-COP-AUT-BA-LD-Priv](https://github.com/Netec-Mx/261007-Temario-COP-AUT-BA-LD-Priv).
- **Microsoft 365 Copilot / Copilot Chat:** [https://m365.cloud.microsoft/chat](https://m365.cloud.microsoft/chat) (o acceso equivalente mostrado por el portal de la organización).
- **Outlook:** [https://outlook.office.com/mail/](https://outlook.office.com/mail/).
- **Microsoft Teams:** [https://teams.microsoft.com/](https://teams.microsoft.com/).
- **Word:** [https://word.cloud.microsoft/](https://word.cloud.microsoft/) (si el acceso cambia, entra por Microsoft 365 > Aplicaciones > Word).
- **PowerPoint:** abre la aplicación web desde Microsoft 365 > Aplicaciones > PowerPoint.
- **Administración de Microsoft 365** (solo administrador autorizado): [https://admin.microsoft.com](https://admin.microsoft.com).
- **Administración de Power Platform** (solo si procede verificar políticas): [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).

## Requisitos generales

| Categoría | Necesidad real | Verificación previa |
| :--- | :--- | :--- |
| Hardware | Equipo capaz de usar aplicaciones web de Microsoft 365, conexión estable y pantalla apta para compartir una demostración | Copilot, Outlook y Teams abren y responden con normalidad. Micrófono/altavoces para preparar reuniones de Facilitator. |
| Sistema operativo | Windows o macOS con navegador soportado; otros sistemas con navegador compatible según soporte de Microsoft 365 | Inicio de sesión y apps web operativos. No se requiere instalar una VM. |
| Navegador | Versión estable y actualizada de Edge, Chrome u otro navegador compatible | Se pueden abrir Microsoft 365 y ventanas de autenticación. No se fija un build artificial. |
| Cuenta | Identidad de trabajo o escuela de la organización | Sesión iniciada; se conocen sus permisos, políticas de manejo de información y restricciones DLP. |
| Licencia Copilot | Licencia habilitadora de **Microsoft 365 Copilot** asociada a un plan base elegible de Microsoft 365 | Copilot puede consultar contenido de trabajo y acceder a los agentes requeridos. «Copilot Premium» no debe usarse como nombre exacto de una licencia empresarial sin comprobar el SKU. |
| Servicios M365 | Exchange Online/Outlook; Teams y Loop; SharePoint/OneDrive para archivos y Pages; Word/PowerPoint para entregables | Las aplicaciones necesarias están disponibles con la cuenta de demostración. |
| Seguridad | Datos de prueba o información real expresamente autorizada | No se comparte información confidencial, no se usan cuentas personales como destino y se evita automatizar envíos externos. |

**No se requieren** Python, Node.js, SDK, CLI, bases de datos, máquinas virtuales, servicios Azure, suscripciones Pay-as-you-go ni bibliotecas adicionales. Las fechas y versiones citadas en datos didácticos son atributos del ejemplo, no requisitos de software.

## Funciones y licencias que deben comprobarse

| Capítulo | Función | Condición que bloquea la demostración |
| :--- | :--- | :--- |
| 1 | Copilot Chat y, opcionalmente, Galería de indicaciones | Copilot no permite enviar mensajes. La ausencia de guardar prompts afecta solo el guardado, no la ejecución del prompt. |
| 2 | Agent Builder + plantilla **Plan My Day**; acceso Copilot a Outlook, reuniones de Teams, Facilitator y Loop | Plantilla/creación bloqueadas, inexistencia de datos laborales accesibles o falta de notas de Facilitator para la demostración completa de reuniones. |
| 3 | **Researcher** y **Analyst**; entrada de 12 registros copiados desde el README (o CSV temporal creado desde ese texto si el pegado falla) | Agentes no licenciados/habilitados o falta de una vía compatible para proporcionar datos a Analyst. La continuidad entre agentes se valida en cada interfaz; de otro modo debe transferirse el resumen explícitamente. |
| 4 | Agent Builder, búsqueda pública autorizada y herramientas de Word/PowerPoint | Bloqueo de web grounding, construcción de agentes o creación de entregables. |
| 5 | **Workflows Agent (Frontier)**, conexión Outlook, evento por correo y acción de IA (Prompt Copilot/AI Prompt) | Frontier no habilitado o no disponible, conector/trigger de Outlook no accesible, acción de IA sin permisos o conectores bloqueados por política. |

> [!WARNING]
> **Importante sobre Workflows:** el agente Workflows de Microsoft 365 Copilot (Frontier) admite creación en lenguaje natural y se administra desde la experiencia de Copilot. No debe reemplazarse por un flujo de Copilot Studio ni por Power Automate tradicional sin cambiar y autorizar el alcance del temario. Microsoft documenta soporte de Workflows en inglés y restricciones de disponibilidad, conectores y políticas. Comprueba específicamente la opción de disparador por correo **y** la acción de IA antes de reservar los 21 minutos de práctica del capítulo 5.

## Preparación antes de la sesión (instructor)

> [!TIP]
> Los siguientes pasos no forman parte de los 151 minutos de práctica. Son preparación del entorno; ejecutarlos durante la clase distorsionaría las duraciones oficiales.

### 1. Comprobar sesión y capacidades de Copilot

1. Inicia sesión con la identidad real de demostración en Microsoft 365 Copilot.
2. Abre una conversación y envía un prompt corto sin datos personales. Comprueba que responde.
3. Confirma el acceso al contexto laboral, por ejemplo el control **Work IQ** cuando esté presente. Evita depender de instrucciones antiguas de alternar forzosamente entre pestañas «Trabajo» y «Web».
4. Abre **Agentes**. Comprueba que aparecen **Researcher**, **Analyst** y **Nuevo agente**, y que puedes seleccionar la plantilla **Plan My Day**.
5. Comprueba si la cuenta permite guardar prompts en la **Galería de indicaciones**. Si no, conserva el texto como plantilla local autorizada, sin declararlo guardado en la galería.
6. Para el **Capítulo 1**, no debes crear tareas reales: el caso de cierre semanal, sus registros A/B/C y el caso D están escritos íntegramente al inicio del README del capítulo 1.

### 2. Preparar el calendario, los correos y las reuniones del capítulo 2

1. Para **Plan My Day**, abre [Capítulo 2 — primera demo](Capitulo02/README.md#demo-del-briefing-diario-a-la-ejecución-de-una-prioridad-con-plan-my-day) y localiza **«Escenario de trabajo y preparación controlada»**. Sigue sus instrucciones: crea en Outlook Calendar **una cita de 30 minutos dentro de los siguientes tres días hábiles** con el título `LAB-COPAUT-PLAN | Revisión del borrador de solicitudes`, el texto de descripción incluido y sin invitar a terceros.
2. Desde Outlook envía a **tu propia cuenta** el correo `LAB-COPAUT-PLAN | Preparación del informe`; el cuerpo completo figura en la misma guía. Comprueba que la cita aparece en el calendario y el correo se recibió; anota la fecha/hora real que elegiste. Haz una prueba con Plan My Day para comprobar que puede consultar al menos uno de los elementos. Si no los recupera, la guía incluye transferencia manual **identificada como cobertura parcial**.
3. Para **múltiples correos**, abre [Capítulo 2 — segunda demo](Capitulo02/README.md#demo-de-múltiples-correos-a-un-estado-consolidado) y localiza «Correos de ejemplo para preparar el entorno». Copia los **tres asuntos y cuerpos completos** y envíalos a tu cuenta de laboratorio en secuencia `01`, `02` y `03`. Verifica su presencia en Outlook buscando `LAB-COPAUT-CORREOS`.
4. Comprueba si Copilot recupera los correos por asunto. Si no, el mismo README detalla el pegado manual, manteniendo la procedencia de cada texto. **Pegar el contenido no demuestra búsqueda autónoma en Outlook.**
5. Para **múltiples reuniones**, abre [Capítulo 2 — tercera demo](Capitulo02/README.md#demo-de-múltiples-reuniones-a-un-seguimiento-consolidado) y sigue las dos rutas. **Ruta A:** programa y realiza dos reuniones autorizadas de Teams con otra persona, habilita Facilitator y confirma que existen dos notas reales de Loop. **Ruta B:** si eso no es viable, utiliza las **dos notas manuales íntegramente incluidas en la guía**, con etiquetas de simulación; no acredita creación de notas por Facilitator.
6. Deja preparados los eventos, correos y reuniones **antes** de iniciar los 50 minutos de práctica del capítulo. No se requiere ningún archivo distribuido por separado.

### 3. Comprobar el escenario, los datos integrados y la transferencia del capítulo 3

1. Abre [Capítulo 3 — Analyst](Capitulo03/README.md#demo-análisis-de-información-y-gestión-de-excepciones-con-analyst) y expande «Datos didácticos para copiar y pegar». Allí está el **bloque de texto con 1 encabezado y 12 registros completos**.
2. Comprueba **12 filas de datos**, **7 abiertas**, **5 cerradas**, **3 abiertas de prioridad alta**, **1 sin responsable** y **1 cerrada sin fecha de cierre**.
3. Ensaya seleccionar la capacidad **Analyst** y **pegar los 12 registros** en el chat. Si Analyst no los reconoce, sigue el procedimiento alternativo del mismo README para **crear temporalmente** un CSV a partir del texto y adjuntarlo; **no hay CSV preelaborado en el repositorio**.
4. Confirma que Researcher y Analyst están disponibles. La práctica 5 contiene la ficha **«Caso de investigación: mejorar el seguimiento de solicitudes internas»**; la práctica 6 explica cada columna del CSV e identifica resultados esperados por ID; la práctica 7 contiene un **bloque de transferencia ya estructurado** para unir las dos salidas en un chat. Ensaya copiar los hallazgos verificados con enlaces a ese bloque; no asumas memoria entre conversaciones distintas.
5. Valida también el orden de las solicitudes abiertas de prioridad alta: `SOL-011 (16)`, `SOL-009 (13)` y `SOL-002 (8)`. No recalcules `Dias_pendiente` desde la fecha actual; es un dato simulado.

### 4. Preparar Agent Builder y entregables del capítulo 4

1. Verifica que puedes crear y guardar un agente de prueba de **Agent Builder**.
2. Revisa la ficha del agente incluida al inicio del README del capítulo 4. Verifica que puedes guardar el nombre `Monitor público Copilot - práctica`, las instrucciones persistentes y, si las políticas lo permiten, fuentes web como `https://learn.microsoft.com` y `https://support.microsoft.com`. No presupongas que esas URLs producen resultados completos en el índice de búsqueda.
3. Verifica que Word y PowerPoint se abren y permiten guardar archivos. Cuando estén disponibles, comprueba las experiencias de creación con Copilot para Word/PowerPoint; de lo contrario se documenta la creación manual a partir de contenido verificado.
4. Comprueba que el usuario tiene una carpeta de OneDrive o SharePoint autorizada para almacenar los productos, no una carpeta supuesta del tenant.

### 5. Validar Workflows (Frontier) del capítulo 5

1. En Microsoft 365 Copilot, busca y agrega **Workflows Agent (Frontier)** desde **Agentes/Tienda**, si está habilitado.
2. Comprueba que puedes crear un workflow nuevo en lenguaje natural y que el diseñador, opciones de prueba y sección **Activity/Actividad** funcionan.
3. Ensaya por separado en el **agente Workflows (Frontier), no en Copilot Studio**: un **desencadenador por correo entrante** (no recurrencia), un **filtro por asunto**, una acción de envío de Outlook a la misma cuenta y una **acción real de IA** (`Prompt Copilot` o `AI Prompt`, según esté disponible) que reciba `Body` dinámico. Son requisitos de ejecución; si falta uno, señala la imposibilidad antes de clase.
4. Revisa los conectores necesarios según documentación oficial y políticas: Outlook, Teams, SharePoint, Planner, Approvals, M365Copilot/AI actions y la configuración de AI Prompt cuando proceda. Algunas acciones pueden requerir habilitaciones específicas de Power Platform/Dataverse; solicita la revisión a un administrador autorizado.
5. Deshabilita las automatizaciones usadas para el ensayo. Las prácticas oficiales crearán nuevos flujos con marcadores distintos: `LAB-COPAUT-01` y `LAB-COPAUT-02`.
6. Si falta Frontier, el desencadenador de evento de Outlook o la acción de IA, informa la **limitación real** antes de la clase; no la ocultes sustituyendo otras tecnologías por una supuesta compatibilidad. Microsoft documenta la disponibilidad cambiante de Frontier y que Workflows acepta instrucciones en **inglés**; en los README ya se incluyen los prompts completos en ese idioma.

## Matriz de prácticas

### Capítulo 1

- [Práctica: De la rutina al prompt reutilizable](Capitulo01/README.md#práctica-de-la-rutina-al-prompt-reutilizable) — 10 minutos. Caso de pendientes A/B/C y D, copiable desde la guía; no requiere archivos previos.

### Capítulo 2

- [Demo: Del briefing diario a la ejecución de una prioridad con Plan My Day](Capitulo02/README.md#demo-del-briefing-diario-a-la-ejecución-de-una-prioridad-con-plan-my-day) — 15 minutos. Cita y correo de prueba que se preparan desde el mismo README.
- [Demo: De múltiples correos a un estado consolidado](Capitulo02/README.md#demo-de-múltiples-correos-a-un-estado-consolidado) — 17 minutos. Tres correos de preparación o mensajes reales autorizados.
- [Demo: De múltiples reuniones a un seguimiento consolidado](Capitulo02/README.md#demo-de-múltiples-reuniones-a-un-seguimiento-consolidado) — 18 minutos. Dos notas de reuniones, preferentemente generadas por Facilitator.

### Capítulo 3

- [Demo: Investigación y consolidación de información con Researcher](Capitulo03/README.md#demo-investigación-y-consolidación-de-información-con-researcher) — 17 minutos. Fuentes verificables.
- [Demo: Análisis de información y gestión de excepciones con Analyst](Capitulo03/README.md#demo-análisis-de-información-y-gestión-de-excepciones-con-analyst) — 18 minutos. **Tabla de 12 registros incluida en el propio README; sin descarga.**
- [Demo: Generación de un reporte ejecutivo a partir del trabajo de los agentes](Capitulo03/README.md#demo-generación-de-un-reporte-ejecutivo-a-partir-del-trabajo-de-los-agentes) — 15 minutos. Insumos de las dos demostraciones anteriores.

### Capítulo 4

- [Demo: Creación de un agente para monitoreo y análisis de información pública](Capitulo04/README.md#demo-creación-de-un-agente-para-monitoreo-y-análisis-de-información-pública) — 20 minutos. Agent Builder, fuentes web, Word y PowerPoint.

### Capítulo 5

- [Demo: De un evento a una acción automática](Capitulo05/README.md#demo-de-un-evento-a-una-acción-automática) — 10 minutos. Outlook + Workflows (Frontier).
- [Demo: Automatización con análisis mediante Microsoft 365 Copilot](Capitulo05/README.md#demo-automatización-con-análisis-mediante-microsoft-365-copilot) — 11 minutos. Outlook + Workflows + acción de IA.

**Control de tiempos:** capítulo 1 = 10; capítulo 2 = 15 + 17 + 18 = 50; capítulo 3 = 17 + 18 + 15 = 50; capítulo 4 = 20; capítulo 5 = 10 + 11 = 21. **Total práctico: 151 minutos (83,89 % de 180 minutos)**. El resto corresponde al contenido conceptual descrito en el temario.

## Seguridad, control y limpieza

- Trabajar solo con fuentes autorizadas; los **correos, notas y 12 registros simulados** están escritos en los README de sus capítulos, con etiquetas de carácter didáctico.
- No colocar contraseñas, tokens ni datos personales en las instrucciones o en repositorios GitHub.
- Crear correos de prueba exclusivamente dirigidos a la cuenta propia de laboratorio. Verificar el asunto de salida para impedir bucles y deshabilitar los flujos tras el ejercicio.
- Documentar qué respuestas/archivos fueron producidos por IA y qué correcciones hizo el instructor. Validar fechas, fuentes y decisiones humanas.
- Los usuarios no deben instalar software de desarrollo ni crear recursos cloud para estas guías. El editor de texto de la alternativa de Analyst no constituye software adicional obligatorio ni recurso de descarga.

## Documentación oficial de referencia

- [Workflows Agent (Frontier): requisitos, acciones y limitaciones](https://support.microsoft.com/en-us/microsoft-365-copilot/get-started-with-workflows-in-microsoft-365-copilot).
- [Plantilla Plan My Day](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-template-plan-my-day).
- [Uso de Researcher](https://support.microsoft.com/en-us/microsoft-365-copilot/get-started-with-researcher-in-microsoft-365-copilot) y [Analyst](https://support.microsoft.com/es-es/microsoft-365-copilot/get-started-with-analyst-in-microsoft-365-copilot).
- [Facilitator en reuniones de Teams](https://support.microsoft.com/es-es/teams/copilot/facilitator-in-microsoft-teams-meetings).
- [Creación de agentes en Agent Builder](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-builder-build-agents) y [fuentes de conocimiento](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-builder-add-knowledge).
- [Word y PowerPoint agents](https://support.microsoft.com/es-es/office/365-copilot-app/get-started-with-word-excel-and-powerpoint-agents-in-microsoft-365-copilot).

---

*Material didáctico preparado por Global K, S.A. de C.V.*
