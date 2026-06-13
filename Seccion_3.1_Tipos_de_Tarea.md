# 3.1 Tipos de tarea

> ✅ Exploración en vivo completada el 12/06/2026. Pendientes menores listados al final.

## ¿Qué es?

El **Tipo de Tarea** es la clasificación que define la naturaleza del trabajo que tus agentes ejecutan en campo: una entrega, una instalación, un mantenimiento, una visita comercial. Cada tarea que crees en Delego debe tener un tipo de tarea asignado, y de él dependen tres cosas:

1. **Actividad** — define qué tipo de trabajo realizarán tus agentes en cada visita o ruta.
2. **Formulario** — indica qué formulario se mostrará en la app móvil para ese tipo de tarea.
3. **Habilidades** — establece qué habilidades debe tener el recurso (agente o vehículo) para poder ejecutarla.

> 📝 **Nota:** Múltiples tipos de tarea pueden usar el mismo formulario. La asociación del formulario no se hace desde aquí, sino desde **Configuraciones → Formularios Personalizados**.

## ¿Cuándo se usa?

- Al configurar tu cuenta por primera vez (es el primer paso del orden de configuración mínima).
- Cada vez que tu operación incorpora un nuevo tipo de actividad de campo (ej. empiezas a hacer recolecciones además de entregas).
- Cuando necesitas controlar ítems y cantidades dentro de una tarea (ej. los productos de una entrega).

## Acceder al módulo

1. En el menú lateral, haz clic en **Configuraciones**.
2. Selecciona **Tipos de Tareas**.

[CAPTURA: menu_configuraciones_tipos_tareas.png]

> 💡 **Tip:** Si es tu primera vez en el módulo, verás un diagrama de bienvenida que explica los tres conceptos (Actividad, Formulario, Habilidades). Puedes volver a verlo en cualquier momento con el botón **?** de la esquina superior derecha; para regresar al listado haz clic en **«**.

## El listado de tipos de tarea

[CAPTURA: listado_tipos_tareas.png]

La pantalla principal muestra una tabla con todos tus tipos de tarea:

| Columna | Qué muestra |
|---|---|
| **Descripción** | El nombre del tipo de tarea. |
| **Items** | Chips con los ítems asociados (formato `código - nombre`). |
| **Estatus** | **ACTIVO** (verde) o **INACTIVO** (rojo). |
| **Opciones** | Botones de **Editar** (lápiz) y **Eliminar** (papelera). |

### Herramientas del listado

- **Valor de búsqueda**: filtra el listado en vivo mientras escribes, buscando sobre la descripción.
- **Ordenamiento**: haz clic en las flechas junto al nombre de la columna (Descripción, Items, Estatus).
- **Filtro avanzado** (ícono de embudo junto a Descripción): abre un panel donde puedes combinar reglas:
  - Condición: *Starts with, Contains, Not contains, Ends with, Equals, Not equals*.
  - **+ Add Rule** agrega reglas adicionales (combinadas con *Match All / Match Any*).
  - **Apply** aplica el filtro (el embudo se convierte en un indicador azul) y **Clear** lo limpia.
- **Paginación** al pie: 50 registros por página, con selector de tamaño y botones `«  ‹  ›  »`.

### Botones de la esquina superior derecha

| Botón | Acción |
|---|---|
| **?** | Reabre el diagrama explicativo del módulo. |
| **+** | Crea un nuevo tipo de tarea. |
| **Descargar** (flecha + desplegable) | Exporta el listado a **CSV**, **Excel** o **PDF**. |

## Crear un tipo de tarea

1. Haz clic en el botón **+** de la esquina superior derecha.
2. Se abre el modal **Detalle de Tipo de Tarea** con estos campos:

| Campo | Obligatorio | Descripción |
|---|---|---|
| **Descripción** | ✅ | El nombre con el que identificarás el tipo de tarea. Asegúrate de que sea claro para los usuarios que deberán seleccionarlo (ej. "ENTREGAS", "VISITA MÉDICA"). |
| **Estatus** | ✅ | **ACTIVO** o **INACTIVO**. Define si el tipo de tarea está disponible: si está Inactivo, no aparecerá como opción en formularios ni en cargas masivas. |
| **Habilidades** | Opcional | Selección múltiple con buscador. Solo los agentes o vehículos que posean estas habilidades serán considerados elegibles para tareas de este tipo. |

[CAPTURA: modal_detalle_tipo_tarea.png]

3. (Opcional) Agrega los **ítems** del tipo de tarea (ver siguiente apartado).
4. Haz clic en **Guardar**. Verás brevemente la pantalla "Guardando los datos…" y luego el mensaje **"¡Datos guardados exitosamente!"**. El nuevo tipo aparece de inmediato en el listado.

> ⚠️ **Advertencia:** Si intentas guardar sin Descripción o sin Estatus, Delego mostrará el mensaje "Debes ingresar la descripción del tipo de tarea / Debes seleccionar el estatus". Completa ambos campos y vuelve a intentar.

> 📝 **Nota:** Delego permite crear dos tipos de tarea con la misma Descripción. Para evitar confusiones al asignar tareas, usa nombres únicos y descriptivos.

## Ítems relacionados al tipo de tarea

Los ítems son los componentes que el agente gestiona dentro de la tarea (productos a entregar, actividades de una inspección, repuestos, etc.). Permiten controlar cantidades y completados parciales en campo.

### Agregar ítems uno por uno

1. Dentro del modal **Detalle de Tipo de Tarea**, haz clic en el botón **+** azul (sección Ítems).
2. Se abre el sub-modal **Ítem del Tipo de Tarea** con dos campos:
   - **Código**: identificador corto del ítem (ej. `01`, `2208-1`).
   - **Ítem**: nombre del ítem (ej. `PRODUCTO DEMO`).
3. Haz clic en **Guardar** del sub-modal. El ítem aparece en la grilla con el formato `código - nombre`.
4. Repite para cada ítem que necesites.

[CAPTURA: submodal_item_tipo_tarea.png]

> ⚠️ **Advertencia:** Agregar ítems a la grilla **no guarda todavía el tipo de tarea**. Cuando termines de agregar ítems, haz clic en **Guardar** del modal principal. Si cierras con **Cancelar** o con la **X**, perderás los cambios.

Cada ítem de la grilla tiene sus propios botones de **Editar** (lápiz) y **Eliminar** (papelera). Al editar, el sub-modal se abre con el Código y el Ítem precargados.

### Cargar ítems en lote (desde archivo)

1. Dentro del modal **Detalle de Tipo de Tarea**, haz clic en el botón con el ícono de **carga** (flecha hacia arriba), junto al **+**.
2. Se abre el modal **Agregar elementos Tipo de tarea desde archivo**:
   - El formato permitido es **XLSX** (Excel).
   - Haz clic en el ícono de **descarga** para bajar el **archivo de plantilla** (`BulkPatternItems.xlsx`) y úsalo como base.
3. Llena la plantilla: tiene una sola hoja llamada **Data-Items** con dos columnas que no debes renombrar:

   | Columna | Qué va ahí | Equivale a |
   |---|---|---|
   | **Code** | Identificador corto del ítem (ej. `01`) | Campo Código |
   | **Item** | Nombre del ítem (ej. `PRODUCTO DEMO`) | Campo Ítem |

   Escribe un ítem por fila, comenzando en la fila 2 (la fila 1 son los encabezados).
4. Selecciona tu archivo con **Seleccione el Archivo**.
5. Haz clic en **Importar Items de Tipo de Tareas**.

[CAPTURA: modal_carga_masiva_items.png]

> 📝 **Nota:** Los encabezados de la plantilla están en inglés (Code, Item) aunque la plataforma esté en español; consérvalos tal cual para que la importación funcione.

## Editar un tipo de tarea

1. En el listado, ubica el tipo de tarea (usa la búsqueda si es necesario).
2. Haz clic en el botón **Editar** (lápiz) de la columna Opciones.
3. Se abre el mismo modal **Detalle de Tipo de Tarea** con todos los datos precargados: puedes cambiar la Descripción, el Estatus, las Habilidades y gestionar los ítems.
4. Haz clic en **Guardar** para aplicar los cambios.

> 💡 **Tip:** Para **inactivar** un tipo de tarea sin perder su historial, edítalo y cambia el Estatus a **INACTIVO**. Dejará de aparecer como opción al crear tareas y en cargas masivas, pero las tareas ya creadas conservan su clasificación.

## Eliminar un tipo de tarea

1. Haz clic en el botón **Eliminar** (papelera) de la columna Opciones.
2. Confirma en el diálogo "¿Está seguro que desea eliminar este tipo de tarea?" haciendo clic en **Eliminar** (o **Cancelar** para abortar).
3. El registro desaparece del listado.

> ⚠️ **Advertencia:** La eliminación es definitiva y no se puede deshacer desde la interfaz. Si el tipo de tarea ya fue usado en tu operación, la recomendación es **inactivarlo** en lugar de eliminarlo, para conservar la trazabilidad de las tareas históricas.

## Pendientes de exploración (iteración futura)

- [ ] Estructura interna de la plantilla XLSX de carga masiva de ítems y validaciones de importación (requiere descargar la plantilla).
- [ ] Comportamiento al eliminar un tipo de tarea que está siendo usado por tareas existentes (¿bloqueo? ¿advertencia?).
- [ ] Capturas de pantalla definitivas (marcadas con [CAPTURA: ...]).
