# 3.5 Hubs (Centros)

> ✅ Exploración en vivo completada el 12/06/2026.

## ¿Qué es?

Un **Hub** (o **centro**) define el punto de inicio o fin de una ruta. Los equipos operan desde un hub, y varios equipos pueden compartir el mismo. En la interfaz verás ambos términos: "Hubs" en el menú y "Centros" dentro de los formularios.

Tres funciones clave:

- **Define desde dónde salen las rutas:** establece el punto de inicio o fin para tus operaciones.
- **Agrupa equipos operativos:** organiza tus equipos en hubs para una mejor gestión.
- **Optimiza la planificación:** mejora la eficiencia de tus rutas y reduce costos operativos.

> ⚠️ **Advertencia:** El hub es **prerequisito para crear equipos**. Es lo primero que debes configurar junto con los tipos de tarea.

## Acceder al módulo

1. En el menú lateral, haz clic en **Recursos operativos**.
2. Selecciona **Hubs**.

> 💡 **Tip:** El botón **?** muestra el diagrama "Crea tu primer Hub".

## El listado de hubs

[CAPTURA: listado_hubs.png]

| Columna | Qué muestra |
|---|---|
| ☑️ (checkbox) | Selección múltiple para eliminación masiva. |
| **Hub** | El nombre del hub. |
| **Dirección** | Su dirección física. |
| **Última actualización** | Fecha de la última modificación. |
| **Equipos** | Todos los equipos que operan desde este hub. |
| **Opciones** | **Editar** (lápiz) y **Eliminar** (papelera). |

Las herramientas del listado (búsqueda, ordenamiento, filtros, exportación CSV/Excel/PDF y papelera masiva en la cabecera) siguen el patrón de los demás módulos.

## Crear un hub

1. Haz clic en el botón **+**.
2. Se abre el modal **Detalles del Centro**, que combina campos con un **mapa interactivo**:

| Campo | Obligatorio | Descripción |
|---|---|---|
| **Hub** | ✅ | Nombre del hub. |
| **Dirección** | ✅ | Dirección física. Al escribirla, el geocodificador ubica el punto. |
| **Latitud / Longitud** | ✅ | Se autocompletan con la dirección; también puedes ajustar el **pin rojo** directamente sobre el mapa. |

El mapa incluye controles de **zoom (+/−)**, **brújula**, **pantalla completa** y **cambio de estilo de mapa** (ícono superior izquierdo).

[CAPTURA: modal_detalles_centro.png]

3. Haz clic en **Guardar**.

> ⚠️ **Advertencia:** Los cuatro campos son obligatorios. Si guardas incompleto verás: "Debes ingresar el nombre del Hubs / la dirección / una longitud válida / una latitud válida".

> 💡 **Tip:** Verifica que el pin del mapa quede exactamente en el acceso de tu bodega o centro: ese punto se usa como inicio y fin al optimizar rutas, y un pin mal ubicado distorsiona los tiempos calculados.

## Editar un hub

1. Haz clic en **Editar** (lápiz) en la fila del hub.
2. Ajusta los datos o reubica el pin y haz clic en **Guardar**.

## Eliminar hubs

- **Individual:** papelera de la fila + confirmación.
- **Masivo:** marca los checkboxes y usa la papelera de la cabecera.

> ⚠️ **Advertencia:** Recuerda que los equipos no pueden existir sin hub. Antes de eliminar un hub, revisa la columna **Equipos** de su fila: si tiene equipos asociados, reasígnalos primero a otro hub.

## Pendientes de exploración (iteración futura)

- [ ] Comportamiento exacto al intentar eliminar un hub con equipos asociados (¿bloqueo o mensaje?).
- [ ] Capturas de pantalla definitivas.
