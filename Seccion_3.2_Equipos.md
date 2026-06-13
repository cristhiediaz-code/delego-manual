# 3.2 Equipos

> ✅ Exploración en vivo completada el 12/06/2026.

## ¿Qué es?

Un **Equipo** agrupa agentes para ejecutar tareas. Puedes organizarlos por zona, por operación o por tipo de servicio. El equipo es la unidad a la que asignas tareas cuando no quieres elegir un agente específico, y es la base de la autoasignación y de las zonas geográficas.

Tres reglas clave:

- **Pertenecen a un hub:** los equipos operan desde un hub (centro). Un equipo no puede existir sin estar asociado a uno.
- **Autoasignación de tareas (opcional):** si la activas, Delego asigna automáticamente las tareas del equipo entre sus agentes disponibles.
- **Agentes en múltiples equipos:** un agente puede pertenecer a varios equipos al mismo tiempo.

## ¿Cuándo se usa?

- En la configuración inicial, después de crear tu primer hub (es prerequisito).
- Cuando tu operación crece y necesitas separar agentes por ciudad, zona o tipo de servicio.
- Cuando quieres que Delego reparta tareas automáticamente (activando **Autoasignación**).

## Acceder al módulo

1. En el menú lateral, haz clic en **Recursos operativos**.
2. Selecciona **Equipos**.

[CAPTURA: menu_recursos_equipos.png]

> 💡 **Tip:** El botón **?** de la esquina superior derecha muestra el diagrama "Crea tu primer equipo" con el resumen visual Hub → Equipo → Agentes.

## El listado de equipos

[CAPTURA: listado_equipos.png]

| Columna | Qué muestra |
|---|---|
| ☑️ (checkbox) | Selección múltiple para eliminar varios equipos a la vez. |
| **Descripción** | El nombre del equipo. |
| **Autoasignación** | Si el equipo tiene la asignación automática activada o no. |
| **Centros** | El hub al que pertenece el equipo. |
| **Opciones** | Botones de **Editar** (lápiz) y **Eliminar** (papelera). |

Las herramientas del listado funcionan igual que en Tipos de Tareas: búsqueda en vivo, ordenamiento por columnas, filtros avanzados (embudo) y exportación a CSV / Excel / PDF. Los equipos recién creados aparecen al inicio de la lista.

Botones de la esquina superior derecha: **?** (diagrama), **+** (nuevo equipo), **papelera** (eliminación masiva, se activa al marcar checkboxes) y **descargar** (exportación).

## Crear un equipo

> 📝 **Nota previa:** Necesitas al menos un **hub** creado (Recursos operativos → Hubs). Sin hub no podrás guardar el equipo.

1. Haz clic en el botón **+**.
2. Se abre el modal **Detalles de Equipo** con dos pestañas.

### Pestaña "Datos del equipo"

| Campo | Obligatorio | Descripción |
|---|---|---|
| **Nombre** | ✅ | Nombre identificador del equipo. Se usa para agrupar agentes, configurar reglas de asignación y filtrar resultados en reportes. |
| **Centros** | ✅ | El hub (centro logístico) al que pertenece el equipo. Define desde qué ubicación operan sus agentes y se usa para respetar las reglas de optimización de rutas. Lista desplegable con buscador. |
| **Autoasignación** | Opcional (checkbox) | Al activarse, cualquier tarea asignada a este equipo se distribuye automáticamente entre sus agentes, según la lógica configurada en **Configuraciones (engranaje) → Auto Assignment**. |
| **Zona Geográfica** | Opcional (checkbox) | Si una tarea no tiene equipo asignado pero su ubicación cae dentro de la zona geográfica dibujada por este equipo, el sistema le asigna automáticamente este equipo al momento de geocodificarse. |

[CAPTURA: modal_detalles_equipo.png]

### Pestaña "Campos personalizados"

Muestra los campos adicionales que el administrador haya definido para la entidad Equipo en **Configuraciones → Campos Personalizados** (por ejemplo, un campo de texto "Instrucciones" o un interruptor personalizado). Si no hay campos configurados, la pestaña aparece vacía. Siempre son opcionales.

3. Completa el **Nombre**, selecciona el **Centro** y marca los checkboxes que necesites.
4. Haz clic en **Guardar**. Verás el mensaje **"¡Datos guardados exitosamente!"** y el equipo aparecerá al inicio del listado.

> ⚠️ **Advertencia:** Si guardas sin completar los campos obligatorios, aparecerá el mensaje "Debes ingresar la descripción del equipo / Debes ingresar el nombre del Hubs". Corresponden a los campos **Nombre** y **Centros**, respectivamente.

## Editar un equipo

1. Haz clic en el botón **Editar** (lápiz) en la fila del equipo.
2. Se abre el mismo modal **Detalles de Equipo** con los datos precargados.
3. Ajusta lo necesario y haz clic en **Guardar**.

## Eliminar equipos

Tienes dos caminos:

**Individual:** haz clic en la **papelera** de la fila y confirma.

**Masivo:**
1. Marca el checkbox de cada equipo que quieras eliminar (o el checkbox del encabezado para seleccionar todos).
2. Haz clic en el botón de **papelera** de la esquina superior derecha.
3. Confirma en el diálogo "Eliminar Equipos — ¿Estás seguro de querer eliminar los equipos seleccionados?" con **Sí**.

> 📝 **Nota:** Delego protege tu configuración de notificaciones: al eliminar en masa, el sistema informa "Se eliminaron los equipos que no estaban asociados a ninguna notificación". Es decir, **los equipos vinculados a alguna notificación al cliente no se eliminan**. Desvincúlalos primero desde el módulo de Notificaciones si realmente necesitas borrarlos.

## Pendientes de exploración (iteración futura)

- [ ] Comportamiento del checkbox **Zona Geográfica**: dónde se dibuja la zona en el mapa (módulo Operaciones).
- [ ] Eliminar un equipo con agentes asignados: ¿advertencia adicional?
- [ ] Capturas de pantalla definitivas.
