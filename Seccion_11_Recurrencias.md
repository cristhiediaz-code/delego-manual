# 11. Recurrencias y tareas planificadas a futuro

> ✅ Exploración en vivo completada el 13/06/2026.

Una **recurrencia** hace que una tarea se **repita automáticamente** en el tiempo (diaria, semanal, mensual, etc.), generando tareas futuras sin que tengas que crearlas una por una. Es ideal para visitas periódicas, mantenimientos programados o entregas regulares al mismo cliente.

## 11.1 Crear una recurrencia

Una recurrencia se define **al crear o editar una tarea**, en la pestaña **Recurrencia** del modal de tarea (también accesible desde Editar Recurrencia, §11.3).

En **Configuración de Recurrencia**:

| Campo | Qué define |
|---|---|
| **Inicia** | Fecha de la primera ocurrencia. |
| **Modo** | La frecuencia: **Diaria, Semanal, Mensual, Anual** o **Personalizar…** |
| **Periodicidad Personalizada** (si Modo = Personalizar) | **Repetir cada** N + **Periodo** (Día / Semana / Mes / Año). Ej: "Repetir cada 2 Semanas". |
| **Termina** | Fecha de fin de la recurrencia. Si se deja vacía, la recurrencia es **indefinida**. |

[CAPTURA: recurrencia_configuracion.png]

Al guardar, Delego genera automáticamente una tarea en cada fecha de la serie, conservando los demás datos (cliente, tipo de tarea, equipo, ítems, etc.) de la tarea base.

> 💡 **Tip:** Usa **Personalizar** para cadencias que no son estándar (ej. cada 15 días, cada 3 meses). Para las comunes, **Diaria/Semanal/Mensual/Anual** es más rápido.

> 📝 **Nota:** El nombre de las tareas generadas refleja su frecuencia (ej. `...-DAILY`, `...-WEEKLY`, `...-MONTHLY`, `...-ANNUALLY`, `...-PERSONALICEMONTH`), lo que ayuda a identificarlas en el listado de Tareas (columna **Recurrencia**).

## 11.2 Vista de tareas planificadas

Para administrar todas las recurrencias en un solo lugar: menú lateral → **Tareas** → panel lateral **Tareas Recurrentes** (pestaña en el borde derecho). Se abre **Configuración de Tareas Recurrentes**.

[CAPTURA: recurrencias_listado.png]

El listado muestra una fila por recurrencia con: **Orden ID, Descripción de la tarea, Sitio de Recolección, Cliente, Recurrencia** (frecuencia, ej. "FRECUENCIA: ANUAL(1)"), **Tipo de Tarea, Equipo, Agente, Inicio de recurrencia, Finalización de recurrencia** y un **indicador de estado** por color.

Cada fila tiene tres acciones (Opciones):
- **Editar Recurrencia** (lápiz) — abre el editor de la recurrencia/tarea (§11.1).
- **Tareas planificadas** (calendario) — muestra las **tareas futuras** que generará esta recurrencia.
- **Eliminar Recurrencia** (papelera).

### Ver tareas planificadas (futuras)
El botón **Tareas planificadas** abre un modal con el horizonte de generación, en pestañas:
- **Recurrencias (próximos 7 días)**
- **Recurrencias (próximos 30 días)**
- **Recurrencias (próximos 60 días)**
- **Recurrencias hasta la fecha de vencimiento**

Cada pestaña muestra **cuántas** recurrencias caen en ese rango y las **fechas exactas** de las tareas que se crearán.

[CAPTURA: recurrencias_tareas_planificadas.png]

> 💡 **Tip:** Revisa "próximos 7/30 días" antes de un periodo crítico (ej. fin de mes) para anticipar la carga de tareas que el sistema generará y planificar recursos.

## 11.3 Edición y eliminación masiva

- **Editar una recurrencia**: botón **Editar Recurrencia** (lápiz). El editor tiene las mismas pestañas que una tarea (Recurrencia, Tarea, Sitio Recolección, Cliente, Campos personalizados, Asignación), así que puedes cambiar la frecuencia, el cliente, el equipo, etc.
- **Eliminar**: botón **Eliminar Recurrencia** (papelera) por fila.
- **Masivo**: marca los **checkboxes** de varias recurrencias para acciones en lote.
- **Buscar / filtrar / ordenar**: el listado tiene buscador, filtros (embudo) y ordenamiento por columna, igual que los demás módulos.

> ⚠️ **Advertencia:** Eliminar una recurrencia detiene la generación de **futuras** tareas de esa serie. Verifica el alcance antes de borrar, especialmente en recurrencias indefinidas con muchas tareas planificadas.

## 11.4 Recurrencias activas, por vencer y vencidas

En la parte superior, los **chips de estado** clasifican y filtran las recurrencias:

| Chip | Significado |
|---|---|
| **Vencidas** | Recurrencias cuya **fecha de finalización ya pasó** (ej. terminaron y ya no generan tareas). |
| **Por Vencer** | Recurrencias **próximas a finalizar**. |
| **Activas** | Recurrencias **vigentes**, generando tareas. |

El número entre paréntesis es el conteo en vivo (ej. Vencidas (11), Por Vencer (0), Activas (71)). Haz clic en un chip para filtrar el listado por ese estado.

> 💡 **Tip:** Revisa periódicamente las **Por Vencer** para renovar (extender la fecha de fin) las recurrencias que deban continuar, antes de que pasen a Vencidas y dejen de generar tareas.

## Pendientes de exploración (iteración futura)

- [ ] Comportamiento exacto del estado "Por Vencer" (cuántos días antes de finalizar).
- [ ] Acciones masivas disponibles al seleccionar varias recurrencias (¿eliminar en lote, cambiar fecha?).
- [ ] Relación con la **Agenda** (`#/schedule`) para tareas agendadas puntuales (no recurrentes).
- [ ] Capturas de pantalla definitivas.
