# 3.9 Ajustes del sistema (Settings)

> ✅ Exploración en vivo completada el 12/06/2026.

## ¿Qué es?

El modal **Settings** concentra la configuración global de tu cuenta Delego: cómo se asignan automáticamente las tareas, qué se notifica al cliente, qué puede hacer el agente en su app, las unidades de medida, las preferencias de visualización y las integraciones externas.

## Acceder

Haz clic en el ícono de **engranaje** ⚙️ de la barra superior (junto a la lupa y el signo de ayuda). Se abre el modal **Settings** con **siete pestañas**.

> ⚠️ **Advertencia:** Estos ajustes afectan a toda la operación. Después de cambiar cualquier valor, haz clic en **Guardar**; usa **Cancelar** para descartar.

---

## Pestaña 1: Auto-Asignación

Define el método con el que Delego reparte automáticamente las tareas entre los agentes de un equipo (solo aplica a equipos con **Autoasignación** activada). Hay **cuatro métodos**, cada uno con su ilustración:

### Publicación Inteligente
Divide el área de operación en **zonas concéntricas** según los tiempos estimados de conducción desde la ubicación de la tarea. La tarea se publica primero a los agentes de la **Zona 1**; si nadie acepta durante el tiempo de espera, escala a la Zona 2, y así hasta la última zona. El proceso termina cuando un agente acepta, o cuando se agotan todas las zonas sin aceptación (la tarea pasa a **Sin asignar**).

Parámetros configurables:
- **Tiempos de conducción (min) en Zona 1 a 4** (ej. 10 / 15 / 20 / 50).
- **Tiempo de espera (seg) antes de publicar la tarea en la siguiente zona** (ej. 60).
- **Número máximo de tareas a atender por agente** (ej. 300).

### Secuencial (Round Robin)
Reparte las tareas en orden rotativo entre los agentes disponibles.

### Por tiempo de Conducción
Asigna la tarea al agente más cercano según el tiempo estimado de conducción desde su posición actual. Prioriza la eficiencia operativa reduciendo desplazamientos. Opciones:
- **Considere también los agentes que están fuera de línea** (checkbox).
- **Permitir agentes que estén activos ejecutando tarea** (checkbox).
- **Número máximo de tareas a atender por agente** (ej. 500).

### Secuencial Inteligente (Round Robin)
Combina la rotación con criterios de inteligencia (distancia/carga).

[CAPTURA: settings_auto_asignacion.png]

---

## Pestaña 2: Notificaciones

Matriz que define **qué estados de la tarea disparan notificación** y **por qué canal**. Los estados son: **Asignada, En Tránsito, En Sitio, Completada, Parcialmente Completada, Cancelada, Rechazada**. Los canales son tres columnas con checkbox: **Email, Webhook, WhatsApp** (el de Email incluye además un ícono para configurar la plantilla del correo).

Al pie: **Idioma de notificaciones** (ej. Español), independiente del idioma de la plataforma.

[CAPTURA: settings_notificaciones.png]

---

## Pestaña 3: Notificaciones BETA

Versión avanzada (en BETA) de las notificaciones personalizadas por correo según el estado de la tarea. Muestra, por cada estado, **cuántas notificaciones están activas** (ej. "2 Activas", "3 Activas") y un botón de configuración para gestionarlas. Incluye además la categoría **RECORDATORIOS**.

> 🔜 **Próximamente:** Esta pestaña está marcada como BETA; su comportamiento puede cambiar. Se documenta a nivel general; el detalle de creación de notificaciones se cubre en la Sección 9 (Notificaciones al cliente).

---

## Pestaña 4: App del Agente

Controla qué puede hacer el agente desde la app móvil, con interruptores:

| Opción | Qué hace |
|---|---|
| **Permitir múltiples tareas abiertas en la app móvil** | Permite que el agente abra y gestione más de una tarea a la vez. |
| **Permitir que los agentes se desasignen tareas desde la app** | El agente puede liberar una tarea asignada si es necesario. |
| **Guardar imágenes en la galería del dispositivo** 🆕 | Guarda en el carrete del teléfono las fotos capturadas en la tarea. |

Además, **Motivos de Retroceso en la Tarea**: define la lista de motivos que el agente debe seleccionar al revertir el estado de una tarea, para mantener trazabilidad y contexto de las decisiones operativas.

[CAPTURA: settings_app_agente.png]

---

## Pestaña 5: Settings Generales

### Definición de unidades por capacidad 🆕
Define la **unidad de medida de cada una de las 5 capacidades** que se asignan a vehículos y agentes (Capacidad 1 a 5). Esto permite que el optimizador relacione correctamente los requerimientos de las tareas con las capacidades de los recursos. Valores por defecto: **kg, m3, m, pallet, caj.**

> 📝 **Nota:** Estas son las unidades que verás junto a los campos **Capacidad 1-5** al crear/editar un **Agente** o un **Vehículo** (secciones 3.3 y 3.4).

### ID Delego para tareas
Interruptor que, al activarse, asigna automáticamente un **identificador único** generado por Delego a cada tarea. Facilita el seguimiento y la referencia de tareas en la plataforma y en los reportes.

[CAPTURA: settings_generales.png]

---

## Pestaña 6: Preferencias

Ajustes de visualización de la cuenta:

| Campo | Descripción |
|---|---|
| **Distance unit** | Unidad de distancia usada en mapas, tareas y reportes (ej. Kilómetros). |
| **Date format** 🆕 | Cómo se muestran las fechas en la plataforma y reportes (ej. DD/MM/YYYY). |
| **Platform language** | Idioma de la interfaz: **English / Español / Português**. No afecta el idioma de las notificaciones (eso se ajusta en la pestaña Notificaciones). |

[CAPTURA: settings_preferencias.png]

---

## Pestaña 7: Integraciones

Conexiones con sistemas externos, organizadas en sub-pestañas:

### API
Credenciales para consumir la API de Delego: **x-api-key**, **Tenant-ID** y **ClientId** (cada uno con botón de copiar), más un enlace a la **Documentación de APIs**.

> ⚠️ **Advertencia:** Estas credenciales son secretas. No las compartas ni las publiques; cualquiera con ellas puede operar tu cuenta vía API.

### Power BI
Dos juegos de credenciales para incrustar tableros:
- **Vista: Administrador / Despachador** — URL, Identificador y Token.
- **Vista: Cliente** — URL, Identificador y Token (vista limitada para clientes).
- Interruptor **Permitir al perfil tipo Cliente visualizar tablero de PBI**.
- Bloque **API** con el endpoint `get_report_file` para descargar reportes por rango de fechas, el header **Accept** y un enlace a la **Documentación de Power BI**.

### Webhook
- **URL** del webhook destino.
- **Tipo de Autenticación** (ej. BASIC).
- **Usuario / Contraseña**.
- Enlace a **Documentación WebHook**.

### Geotab
Integración con telemática de flota: **Base de Datos**, **Usuario**, **Contraseña** y enlace a **Documentación Geotab**.

[CAPTURA: settings_integraciones_api.png]
[CAPTURA: settings_integraciones_powerbi.png]

---

## Pendientes de exploración (iteración futura)

- [ ] Plantilla del correo de notificación (ícono junto a la columna Email).
- [ ] Flujo completo de configuración de una notificación en Notificaciones BETA (Sección 9).
- [ ] Detalle de "Motivos de Retroceso en la Tarea" (cómo se agregan).
- [ ] Capturas de pantalla definitivas.
