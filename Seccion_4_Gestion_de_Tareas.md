# 4. Gestión de tareas

> ✅ Exploración en vivo completada el 12/06/2026.

La **tarea** es la unidad básica de trabajo en Delego: una entrega, recogida, visita, inspección o servicio que un agente ejecuta en campo. Este módulo (menú lateral → **Tareas**) es donde las creas, editas, das seguimiento y resuelves excepciones.

## El listado de Tareas

![Listado tareas](imagenes/web/04_gestion_tareas/listado_tareas.png)

En la parte superior, una **barra de chips de estado** muestra cuántas tareas hay en cada estado y permite filtrar el listado al hacer clic en uno (ver §4.4).

| Columna | Qué muestra |
|---|---|
| ☑️ | Selección múltiple para acciones en lote. |
| **Tipo de Tarea** | El tipo de tarea asignado. |
| **Cliente** | El punto de visita (destino). |
| **Teléfono** | Teléfono del cliente. |
| **Dirección** | Dirección de ejecución. |
| **Fecha** | Fecha programada. |
| **Nombre de la Tarea** | Nombre/identificador. |
| **Recurrencia** | Ícono si la tarea proviene de una recurrencia. |
| **Estatus** | Estado actual con su color. |
| **Opciones** | Acciones por fila (ver §4.3). |

**Botones de la cabecera:** **?** (ayuda), **+** (crear tarea), **Carga Masiva** (subir, ícono de flecha arriba) y **Exportar** (descargar).

**Paneles laterales (borde derecho):** **Geocodificación**, **Tareas Recurrentes** y **Filtros**.

---

## 4.1 Crear una tarea manualmente

1. Haz clic en el botón **+** de la cabecera.
2. Se abre el modal **Detalle de Tareas** con **seis pestañas**: **Tarea, Sitio Recolección, Cliente, Campos personalizados, Asignación, Recurrencia**.

> 📝 **Nota:** Este modal es el mismo que se documenta paso a paso en la **Sección 2.4 (Crea tu primera tarea)**. Aquí se resume; consulta 2.4 para el detalle de cada campo.

### Pestaña Tarea (campos principales)

| Campo | Obligatorio | Notas |
|---|---|---|
| **Identificador** | Opcional | Puede autogenerarse (ver "ID Delego para tareas" en Settings → Settings Generales). |
| **Nombre de la Tarea** | ✅ | |
| **Prioridad** | ✅ | NORMAL / ALTA. |
| **Modo de Tarea** | ✅ | Inmediata / Mismo día / Día siguiente / Programada (ver §5). |
| **Instrucciones** | Opcional | Texto para el agente. |
| **Fecha / Después / Antes** | ✅ | Fecha y ventana horaria de atención. |
| **Tipo de Tarea** | ✅ | |
| **Equipo** | Opcional | Se sincroniza con la pestaña Asignación. |
| **Condición de tarea** (toggle) | Opcional | Activarlo pone la tarea **En Pausa / On Hold** (ver §4.6). |
| **Tiempo de Servicio** | Opcional | Duración estimada en sitio (ej. 5 Minutos). |
| **Valor 1 a 5** | Valor 1 ✅ | Cantidades por capacidad, en las unidades configuradas (kg, m3, m, pallet, caj.). |
| **Detalle de Items** | Opcional | Ver §4.7. |

3. Completa el resto de pestañas según necesites (cliente, asignación, recurrencia).
4. Guarda con uno de los botones inferiores:
   - **Guardar** — crea la tarea y cierra.
   - **Guardar & Crear Nueva Tarea** — crea la tarea y abre un modal vacío para encadenar otra.
   - **Guardar & Crear Retorno** — (en flujos de recolección+entrega) crea la tarea inversa.
   - **Cancelar** — descarta.

![Modal detalle tarea pestana1](imagenes/web/04_gestion_tareas/modal_detalle_tarea_pestana1.png)

---

## 4.2 Crear tareas en lote (Carga Masiva)

Para crear muchas tareas a la vez desde un archivo Excel:

1. En la cabecera, haz clic en **Carga Masiva** (ícono de subir).
2. Se abre el modal **Agregar tareas desde un archivo**:
   - Formato permitido: **XLSX**.
   - **Descargue la guía para carga masiva de tareas aquí** — instrucciones.
   - **Revise el archivo de descarga modelo disponible aquí** — descarga la plantilla (`bulkPattern...xlsx`).
3. Llena la plantilla (estructura abajo).
4. Selecciona tu archivo con **Seleccione el Archivo**.
5. Haz clic en **Importar Tareas**.

![Modal carga masiva tareas](imagenes/web/04_gestion_tareas/modal_carga_masiva_tareas.png)

### Estructura de la plantilla

La plantilla tiene **tres hojas**:

**Hoja `Bulk tasks`** — una fila por tarea. Las columnas con `*` son obligatorias:

| Columna | Obligatoria | Qué va |
|---|---|---|
| `OrderID` | | ID externo para vincular ítems (hoja Data-Items). |
| `*TaskName` | ✅ | Nombre de la tarea. |
| `TaskInstructions` | | Instrucciones. |
| `Priority` | | Prioridad. |
| `*TaskMode` | ✅ | Modo de tarea (IMMEDIATE, APPOINTED, etc.). |
| `*RequestedDate(YYYY-MM-DD)` | ✅ | Fecha solicitada. |
| `StartTimeWindow` / `EndTimeWindow` | | Ventana horaria. |
| `*TaskType` | ✅ | Tipo de tarea (debe existir). |
| `Team` | | Equipo. |
| `*Value1` … `Value5` | Value1 ✅ | Cantidades por capacidad. |
| `*CustomerName`, `*Customeraddress`, `*CustomerCountry`, `*CustomerCity`, `*Customerphone` | ✅ | Datos del cliente. |
| `Customeremail`, `Customerlatitude`, `Customerlongitude` | | Opcionales del cliente. |
| `PickupName`, `PickupAddress`, … `PickupLongitude` | | Sitio de recolección (para flujos pickup+entrega). |
| `ServiceTime(minutes)` | | Tiempo de servicio. |
| `Item 1`, `Item 1 Qty` | | Ítem y cantidad inline. |
| `Agent` | | Agente para asignación directa. |
| `TaskConditions`, `ReasonOnHold` | | Condición/On Hold y su motivo. |
| Columnas extra | | Campos personalizados del tipo de tarea (ej. "Student Name and ID", "Pickup Location"). |

**Hoja `Data`** — catálogos de valores válidos que puedes usar como referencia/validación (países, equipos, tipos de tarea, prioridades `HIGH/STANDARD`, modos `IMMEDIATE/APPOINTED/...`, ítems, condiciones `ON_HOLD/READY`, motivos de On Hold).

**Hoja `Data-Items`** — para cargar **varios ítems por tarea**: columnas `OrderID` (debe coincidir con el de la hoja Bulk tasks), `Code`, `Item`, `Qty`.

> 💡 **Tip:** No renombres ni reordenes las columnas, y conserva los encabezados en inglés tal cual. Usa la hoja **Data** para copiar los valores exactos de TaskType, Team y modos, evitando errores de importación.

> ⚠️ **Advertencia:** Confirma que cada `*TaskType` y `Team` exista previamente en tu cuenta; de lo contrario esas filas fallarán.

---

## 4.3 Editar, duplicar, cancelar y eliminar tareas

Cada fila del listado tiene, en **Opciones**, estos botones:

| Botón | Acción |
|---|---|
| **Editar tarea** (lápiz) | Abre el modal Detalle de Tareas con los datos cargados. |
| **Ver detalles** (lupa) | Vista de **solo lectura** con tres columnas (Tarea / Cliente / Ejecución) y el ID completo de la tarea. |
| **Ver eventos de la tarea** (reloj) | Abre el **Historial de Eventos** (ver §4.4 y §12). |
| **Clonar Tarea** | Crea una copia de la tarea. |
| **Cancelar Tarea** | Cambia el estado a **Cancelada** (ver §4.4). |
| **Eliminar Tarea** | Borra la tarea del sistema. |

> 📝 **Nota — Cancelar vs Eliminar:** **Cancelar** conserva la tarea con estado Cancelada (mantiene trazabilidad); **Eliminar** la quita por completo. Para auditoría, prefiere Cancelar.

> 💡 **Tip:** Para acciones sobre varias tareas a la vez, márcalas con los **checkboxes** y usa el menú contextual (clic derecho) o las acciones en lote (ver §5 para asignación masiva).

### Ver detalles (solo lectura)

![Modal ver detalles tarea](imagenes/web/04_gestion_tareas/modal_ver_detalles_tarea.png)

Muestra, sin posibilidad de editar:
- **Tarea**: nombre, tipo, prioridad, identificador, fecha, ventana, equipo, modo, valores, condición, compartimiento, tiempo de servicio, instrucciones, recurrencia e ítems.
- **Cliente**: nombre, correo, teléfono, dirección y coordenadas.
- **Ejecución**: agente, fecha/hora y estatus.

El título del modal incluye el **ID único** de la tarea (`TAREA #...`), útil para soporte e integraciones.

---

## 4.4 Estados de una tarea y sus transiciones

El estado de una tarea se ve en la columna **Estatus** y en los **chips superiores** (que también filtran). Cada estado tiene un color:

| Estado | Color del indicador | Significado |
|---|---|---|
| **En Pausa** | gris tenue | Tarea pausada (On Hold), no asignable hasta reactivar. Ver §4.6. |
| **No Asignadas** | blanco | Creada pero sin agente. |
| **Asignadas** | azul (`#2E67FA`) | Asignada a un agente, pendiente de iniciar. |
| **En Tránsito** | amarillo (`#FEFF02`) | El agente va en camino. |
| **En Sitio** | verde claro (`#AAD6AB`) | El agente llegó al punto. |
| **Completadas** | verde (`#81CB74`) | Ejecutada con éxito. |
| **Parcialmente Completadas** | verde (`#81CB74`) | Completada en parte (ver §4.5). |
| **Rechazadas** | rojo (`#F34C3E`) | El agente la rechazó. |
| **Canceladas** | rojo (`#F34C3E`) | Cancelada desde la web. |

> 💡 **Tip:** Haz clic en cualquier chip para filtrar el listado por ese estado; el número entre paréntesis es el conteo en vivo.

### Historial de Eventos (trazabilidad)

El botón **Ver eventos de la tarea** (reloj) abre el **Historial de Eventos**: una línea de tiempo de cada cambio de estado, con **estado, fecha/hora y autor** (ej. "NO ASIGNADO — 31/05/2026 17:18 — Cristhie Y Díaz (SYSTEM)"). Incluye botón para **exportar** el historial. Es la base de la auditoría (ver Sección 12).

![Modal historial eventos](imagenes/web/04_gestion_tareas/modal_historial_eventos.png)

---

## 4.5 Tareas relacionadas, devoluciones y completados parciales

- **Completado parcial:** cuando el agente entrega/atiende solo una parte de los ítems, la tarea queda en **Parcialmente Completada**. El detalle de qué ítems y cantidades se cumplieron se ve en **Ver detalles → Ejecución** y en los reportes.
- **Retorno / devolución:** al crear una tarea, el botón **Guardar & Crear Retorno** genera la tarea inversa (intercambia sitio de recolección ↔ cliente), útil para logística inversa.
- **Tareas relacionadas:** las tareas que comparten `OrderID` (carga masiva) o que provienen de la misma recurrencia quedan vinculadas para seguimiento.

> 🔜 **Próximamente / por confirmar:** El detalle exacto de la vista de tareas relacionadas se ampliará en una próxima iteración del manual.

---

## 4.6 Estado "On Hold" (En Pausa) y manejo de excepciones

Una tarea puede pausarse para que **no entre en asignación** hasta resolver una condición (ej. falta confirmar con el cliente, documentación incompleta).

**Cómo poner una tarea On Hold:**
1. Al crear/editar, en la pestaña **Tarea**, activa el toggle **Condición de tarea**.
2. Selecciona/indica el **motivo** (los motivos se gestionan en Settings → App del Agente → "Motivos de Retroceso en la Tarea", y en la carga masiva con la columna `ReasonOnHold`).
3. Guarda. La tarea aparece en el chip **En Pausa**.

> ⚠️ **Advertencia:** Una tarea **En Pausa no se puede asignar**. Desactiva la condición para liberarla y que vuelva a **No Asignada**.

---

## 4.7 Ítems y cantidades dentro de una tarea

En la pestaña **Tarea**, la sección **Detalle de Items** lista los ítems que el agente debe gestionar (productos a entregar, componentes de una inspección, etc.), con **Código, Descripción y Cantidad**, y un **Total**.

- Los ítems disponibles provienen del **Tipo de Tarea** seleccionado (los configuras en Tipos de Tareas → Ítems, Sección 3.1).
- En la **carga masiva**, los ítems se cargan con `Item 1`/`Item 1 Qty` (inline) o en la hoja **Data-Items** (varios por tarea, vinculados por `OrderID`).
- El cumplimiento parcial de estos ítems es lo que produce el estado **Parcialmente Completada** (§4.5).

![Detalle items tarea](imagenes/web/04_gestion_tareas/detalle_items_tarea.png)

---

## Pendientes de exploración (iteración futura)

- [ ] Menú contextual (clic derecho) con sus acciones en lote.
- [ ] Paneles laterales Geocodificación / Tareas Recurrentes / Filtros del listado.
- [ ] Flujo de exportación de tareas (botón descargar de la cabecera).
- [ ] Vista de tareas relacionadas en detalle.
- [ ] Capturas de pantalla definitivas.
