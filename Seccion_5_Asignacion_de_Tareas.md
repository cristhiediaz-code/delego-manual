# 5. Asignación de tareas

> ✅ Exploración en vivo completada el 12/06/2026 (menú y panel mapeados sin asignar para no alterar la data demo).

Asignar una tarea es ponerla en manos del recurso que la ejecutará (un agente o, en planificación avanzada, un vehículo). La mayor parte del trabajo de asignación se hace desde la pantalla **Operaciones** (menú lateral → **Operaciones**), que combina un **listado lateral** de tareas con un **mapa** y los paneles **Recursos**, **Agregar Tareas**, **Vistas Personalizadas** y **Geocodificación**.

## 5.1 Modos de ejecución (Modo de Tarea)

El **Modo de Tarea** (campo obligatorio al crear la tarea, §4.1) define la temporalidad con la que debe ejecutarse y condiciona qué modalidades de asignación tienen sentido:

| Modo | Cuándo usarlo |
|---|---|
| **Inmediata** (IMMEDIATE) | Debe atenderse ya, en el momento. Ideal para publicación/asignación inmediata. |
| **Mismo día** (SAME DAY) | Debe completarse hoy, sin hora fija. |
| **Día siguiente** (NEXT DAY) | Programada para el día siguiente. |
| **Programada / Con cita** (APPOINTED) | Tiene fecha y ventana horaria específicas; se planifica con anticipación. |

> 📝 **Nota:** Estos mismos códigos (`IMMEDIATE`, `APPOINTED`, etc.) son los que usas en la columna `*TaskMode` de la carga masiva (§4.2).

## Seleccionar tareas

Antes de asignar, selecciona una o varias tareas:

- **Desde el listado lateral:** marca el **checkbox** de cada tarea. El contador "(n/60)" y los totales de capacidad (kg, m3, m, pallet, caj.) se actualizan arriba. **Seleccionar todas las tareas** marca el lote completo.
- **Desde el mapa:** usa **shift + arrastrar** para seleccionar por área todos los pines dentro de un rectángulo.

> 💡 **Tip:** Al seleccionar una tarea, el mapa hace zoom a su ubicación. Verifica ahí que el pin esté bien geocodificado antes de asignar.

## Las 6 modalidades de asignación

Con tareas seleccionadas, haz **clic derecho** sobre la selección para abrir el **menú contextual**. Las modalidades se agrupan en inmediatas y planificadas:

### Inmediatas (asignan sin optimizar ruta)

| Modalidad | Qué hace |
|---|---|
| **Asignación Directa** | Tú eliges el agente y la tarea se le asigna directamente. |
| **Publicar** | Publicas la tarea a **varios agentes que tú eliges**; el primero que la acepta se queda con ella. |
| **Publicación Inteligente** | Estilo Uber: publica por **zonas de tiempo de conducción** y va ampliando el radio hasta que alguien acepta (configurable en Settings → Auto-Asignación, §3.9). |

### Planificadas (optimizan ruta / agenda)

| Modalidad | Qué hace |
|---|---|
| **Agendar** | Abre un calendario para programar la tarea a una fecha/hora futura. |
| **Planif. Rutas** | Optimizador básico; premisa: la **ruta más corta**. |
| **Planif. Avanzada de Rutas** | Optimizador avanzado: considera capacidades, tiempos de servicio, ventanas de atención y más. **Única modalidad que también permite asignar a vehículos** (ver §6). |

![Menu contextual asignacion](imagenes/web/05_asignacion/menu_contextual_asignacion.png)

> 📝 **Nota:** El menú contextual también incluye acciones que **no** son de asignación: **Desasignar Tarea, Cancelar Tarea, Eliminar Tareas, Invalidar Localización de Tarea** y **Edición Masiva** (editar varias tareas a la vez). Ver §5.4.

## 5.2 Asignación directa (paso a paso)

1. Selecciona la(s) tarea(s) en el listado o el mapa.
2. **Clic derecho** → **Asignación Directa**.
3. Se abre el panel **Recursos** a la derecha, con dos pestañas: **Agentes** y **Vehículos**. Cada **agente** muestra su avatar, nombre, **Capacidad**, **Equipos**, **Habilidades** y número de **Tareas** asignadas.
4. Marca el **checkbox** del agente y haz clic en **Siguiente**.
5. Se abre el modal **Seleccionar para asignar** con la lista de tareas y una **previsualización de la ruta** en el mapa → **Asignar**.
6. Confirma en el modal **Asignar Tareas** → **Asignar**.
7. Aparece un mensaje de éxito (toast); en el listado, la tarea cambia de color (de blanco a **azul = Asignada**) y muestra **"Asignado a: [Nombre]"**.

![Panel recursos agentes](imagenes/web/05_asignacion/panel_recursos_agentes.png)
![Modal seleccionar asignar](imagenes/web/05_asignacion/modal_seleccionar_asignar.png)

> 📝 **Nota:** Para las modalidades **inmediatas** (Directa, Publicar, Publicación Inteligente) solo se asigna a **Agentes**. La pestaña **Vehículos** del panel Recursos solo aplica en **Planif. Avanzada de Rutas**.

> 💡 **Tip:** Usa las columnas de **Capacidad** y **Habilidades** del panel para no asignar una tarea a un agente que no puede ejecutarla (ej. sin la habilidad requerida o sin capacidad suficiente).

## 5.3 Publicación a varios agentes (Publicar / Publicación Inteligente)

- **Publicar:** clic derecho → **Publicar** → en el panel Recursos marca **varios agentes** → confirma. La tarea les llega a todos en su app; **el primero que acepta** se la queda y desaparece para el resto.
- **Publicación Inteligente:** clic derecho → **Publicación inteligente**. No eliges agentes uno a uno: Delego publica por **zonas concéntricas de tiempo de conducción** y va escalando de zona si nadie acepta dentro del tiempo de espera. Los parámetros (tiempos por zona, tiempo de espera, máximo de tareas por agente) se configuran en **Settings → Auto-Asignación** (§3.9). Si se agotan todas las zonas sin aceptación, la tarea vuelve a **Sin asignar**.

## 5.4 Reasignación y cambios

| Acción (menú contextual) | Para qué |
|---|---|
| **Desasignar Tarea** | Quita el agente actual; la tarea vuelve a **No Asignada** para reasignarla. |
| **Edición Masiva** | Edita en bloque varias tareas seleccionadas (ej. cambiar equipo, fecha). |
| **Invalidar Localización de Tarea** | Marca la geocodificación como inválida (para corregir una dirección mal ubicada). |
| **Cancelar Tarea / Eliminar Tareas** | Cancelar conserva la tarea (estado Cancelada); Eliminar la borra. Ver §4.3. |

**Reasignar a otro agente:** desasigna primero (Desasignar Tarea) y vuelve a asignar con cualquier modalidad. **Cambiar de equipo:** usa Edición Masiva o edita la tarea (pestaña Tarea → Equipo).

> ⚠️ **Advertencia:** No puedes asignar una tarea que está **En Pausa (On Hold)**. Libérala primero desactivando su condición (§4.6).

## Pendientes de exploración (iteración futura)

- [ ] Flujo completo de Publicación Inteligente con vista de zonas en el mapa.
- [ ] Modal de **Agendar** (calendario).
- [ ] Comportamiento de **Edición Masiva** (qué campos permite cambiar).
- [ ] Detalle de **Invalidar Localización de Tarea**.
- [ ] Capturas de pantalla definitivas.
