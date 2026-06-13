# 10. Notificaciones al cliente

> ✅ Exploración en vivo completada el 13/06/2026.
> 📝 Este manual documenta el módulo **Notificaciones BETA**, que es el flujo vigente para notificaciones al cliente. La pestaña "Notificaciones" (clásica) está en proceso de **deprecación** y no se documenta como flujo oficial.

## 10.1 ¿Qué se puede notificar?

Delego puede enviar **notificaciones automáticas por correo** al cliente (y a quien definas) cada vez que una tarea **cambia de estado**. Así el cliente se entera, por ejemplo, de que su entrega fue asignada, va en camino o se completó, sin que nadie tenga que escribirle manualmente.

Los **estados** que pueden disparar notificaciones son:

- **ASIGNADA**
- **EN TRÁNSITO**
- **EN SITIO**
- **COMPLETADA**
- **PARCIALMENTE COMPLETADA**
- **CANCELADA**
- **RECHAZADA**
- **RECORDATORIOS** (recordatorios programados)

> 💡 **Tip:** Para cada estado puedes tener **varias notificaciones distintas** activas a la vez (ej. una para clientes de un tipo de tarea y otra para otro), no solo una.

## Acceder

1. Haz clic en el **engranaje** ⚙️ de la barra superior (Settings).
2. Abre la pestaña **Notificaciones BETA**.

Verás la pantalla **Notificaciones Personalizadas (BETA)**: una fila por estado, con el número de **notificaciones activas** por canal (**Email**, **Webhook**, **WhatsApp**). El ícono de **engranaje** azul de cada estado abre su lista de notificaciones.

[CAPTURA: notif_beta_matriz_estados.png]

## 10.2 Crear y configurar una notificación

1. En Notificaciones BETA, haz clic en el **engranaje** del estado que quieres notificar (ej. **COMPLETADA**).
2. Se abre **Configuración de notificaciones - [ESTADO]** con la lista de notificaciones de ese estado. Cada una tiene un **toggle** (activar/desactivar) y opciones: **configurar** (engranaje), **duplicar** (copiar), **enviar/probar** (avión) y **eliminar** (papelera).
3. Haz clic en el botón **+** para crear una nueva. Delego pide primero el **Nombre de la notificación**; escríbelo y **Guardar**.
4. Se abre el **editor de la notificación** con **cuatro pestañas**: **Filtros**, **Formato de Correos**, **Adjuntos** y **Destinatarios**.

[CAPTURA: notif_beta_lista_estado.png]

### Pestaña Formato de Correos
Define el contenido del correo:
- **Asunto de Correo** (obligatorio).
- **Editor de texto enriquecido** (negrita, cursiva, listas, alineación, enlaces, imágenes, color, e incluso edición de **código HTML**).
- **Campos Dinámicos**: menú para insertar datos de la tarea en el asunto o el cuerpo, de modo que cada correo se personaliza solo. Campos disponibles: **Identificador, Nombre de la tarea, Instrucciones, Fecha planificada + hora, Modo de Tarea, Prioridad, Valor 1…** (y, según la descripción, también ventana de atención y **enlace de seguimiento**, ver §10.6).

[CAPTURA: notif_beta_formato_correo.png]

5. Completa las demás pestañas (§10.3, §10.4, §10.6) y haz clic en **Guardar**.

> 💡 **Tip:** Usa los Campos Dinámicos en lugar de texto fijo: así un mismo formato sirve para todas las tareas y el cliente siempre ve sus datos correctos.

## 10.3 Condiciones (pestaña Filtros)

La pestaña **Filtros** define **cuándo** se dispara esta notificación, además del estado. Puedes acotarla por:

| Filtro | Para qué |
|---|---|
| **Tipo de tarea** (obligatorio) | Solo notifica para ese tipo de tarea. |
| **Equipos** | Limita a uno o varios equipos (por defecto TODOS). |
| **Agentes** | Limita a agentes específicos. |
| **Prioridad** | Solo tareas de cierta prioridad. |
| **Modo de tarea** | Inmediata, Programada, etc. |
| **Clientes** | Solo ciertos clientes. |

Así puedes tener, por ejemplo, un correo de "COMPLETADA" distinto para el tipo de tarea "Entregas" que para "Visita Médica".

[CAPTURA: notif_beta_filtros.png]

## 10.4 Adjuntar reportes a notificaciones (pestaña Adjuntos)

La pestaña **Adjuntos** permite **adjuntar hasta 5 reportes** al correo de la notificación (ej. comprobante de entrega, reporte fotográfico).

> ⚠️ **Advertencia:** Los reportes deben estar **creados previamente en Reportes Personalizados** (Sección 11) y solo aparecerán en la lista los **asociados al tipo de tarea** seleccionado en Filtros. Si no ves tu reporte, revisa que exista y esté asociado a ese tipo de tarea.

[CAPTURA: notif_beta_adjuntos.png]

## 10.5 Probar antes de activar

Antes de dejar una notificación activa para todos los clientes, **pruébala**:

- En la lista de notificaciones del estado, cada notificación tiene un botón de **enviar/probar** (ícono de avión ✈️) que te permite disparar un envío de prueba para revisar cómo llega el correo.
- El **toggle** de cada notificación controla si está **activa** (enviando) o no. Déjala desactivada mientras la ajustas y actívala solo cuando el formato y los destinatarios estén verificados.

> 💡 **Tip:** Envíate la prueba a ti mismo (agrégate en Destinatarios) y revisa que los Campos Dinámicos se reemplacen bien y que los adjuntos lleguen, antes de activarla para el cliente real.

## 10.6 Destinatarios, links de tracking y ETA

### Destinatarios (pestaña Destinatarios)
Define **quién recibe** el correo:
- **Destinatarios**: selecciona **usuarios de la plataforma**.
- **Usar correos asociados a la tarea** (toggle): envía al **correo del cliente** de la tarea (lo más común para notificar al cliente final).
- **Agregar correos adicionales** (toggle): permite escribir **direcciones de correo manuales** extra.

[CAPTURA: notif_beta_destinatarios.png]

### Links de tracking y ETA
Para que el cliente pueda **seguir su tarea en tiempo real**, inserta el **enlace de seguimiento** desde los **Campos Dinámicos** (§10.2) en el cuerpo del correo. Ese link lleva a una página de tracking con la ubicación/estado y la **hora estimada de llegada (ETA)**.

> 💡 **Tip:** Combina el enlace de seguimiento con un correo de estado **EN TRÁNSITO**: el cliente recibe el aviso "tu pedido va en camino" con el botón para rastrearlo en vivo.

## Pendientes de exploración (iteración futura)

- [ ] Confirmar el contenido exacto de la página de tracking/ETA que abre el enlace de seguimiento.
- [ ] Lista completa de Campos Dinámicos (puede haber más bajo scroll).
- [ ] Configuración de notificaciones por **Webhook** y **WhatsApp** (esta sección cubre el canal Email; los otros canales se activan desde la matriz de estados).
- [ ] Detalle de **RECORDATORIOS**.
- [ ] Capturas de pantalla definitivas.
