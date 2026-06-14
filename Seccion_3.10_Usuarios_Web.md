# 3.10 Usuarios web y permisos

> ✅ Exploración en vivo completada el 12/06/2026 (sin crear usuarios reales para no disparar correos de credenciales).

## ¿Qué es?

Los **Usuarios Web** son las personas que acceden a la plataforma web de Delego para gestionar la operación. Cada uno tiene un **rol** y **permisos según los equipos asignados**.

> 📝 **Nota:** Los usuarios web son distintos de los **agentes**, que ejecutan tareas en campo desde la app móvil.

El modelo de permisos tiene tres piezas:

1. **Tipo de usuario** — define el rol dentro de la plataforma: **Administrador**, **Despachador (dispatcher)** o **Cliente**.
2. **Permisos por rol** — cada rol tiene capacidades de visualización y acción distintas.
3. **Equipos asignados** — segmentan los datos que verá el usuario: cada usuario ve **solo** la información de sus equipos asignados.

> 💡 **Tip:** Usa el rol **Cliente** para dar visibilidad de seguimiento a un cliente corporativo sin exponer el resto de tu operación: al asignarle solo su equipo, su vista queda limitada a esos datos.

## Acceder al módulo

1. En el menú lateral, haz clic en **Recursos operativos**.
2. Selecciona **Usuarios Web**.

> 💡 **Tip:** El botón **?** muestra el diagrama "Crea tu primer usuario web" con el resumen del modelo de permisos.

## El listado de usuarios web

![Listado usuarios web](imagenes/web/03_10_usuarios_web/listado_usuarios_web.png)

| Columna | Qué muestra |
|---|---|
| **Nombre / Apellido** | Identificación del usuario. |
| **Correo Electrónico** | Su llave de acceso a la plataforma. |
| **Tipo** | ADMINISTRADOR, DESPACHADOR o CLIENTE. |
| **Estatus** | **ACTIVO** / **INACTIVO**. |
| **¿Verificado?** | Si el usuario ya validó su cuenta e ingresó. |
| **Opciones** | **Editar** (lápiz). |

Además de las herramientas habituales (búsqueda, ordenamiento, filtros por columna, exportación), este módulo tiene una pestaña **Filtros** en el borde derecho de la pantalla que abre un panel de filtrado rápido (por búsqueda y tipo).

> 📝 **Nota:** Al igual que Agentes, los usuarios web no se eliminan desde el listado; se inactivan con el Estatus.

## Crear un usuario web

1. Haz clic en el botón **+**.
2. Se abre el modal **Detalles de Usuario Web** con dos pestañas: **Datos del usuario web** y **Campos personalizados**.

| Campo | Obligatorio | Descripción |
|---|---|---|
| **Nombre** | ✅ | Nombre de la persona. |
| **Apellido** | ✅ | Apellido. |
| **Correo Electrónico** | ✅ | Su correo de acceso (recibirá las credenciales). |
| **Tipo** | ✅ | **DESPACHADOR**, **ADMINISTRADOR** o **CLIENTE**. |
| **Estatus** | ✅ | ACTIVO / INACTIVO. |
| **Equipos** | ✅ | El o los equipos cuyos datos podrá ver el usuario. |

![Modal usuario web](imagenes/web/03_10_usuarios_web/modal_usuario_web.png)

3. Haz clic en **Guardar**. El usuario recibirá sus credenciales por correo, y aparecerá como NO VERIFICADO hasta su primer ingreso.

> ⚠️ **Advertencia:** Los seis campos son obligatorios. Si guardas incompleto verás: "Debes ingresar el nombre / el apellido / el Email / seleccionar el tipo de usuario / seleccionar el estatus / seleccionar el(los) equipo(s)".

> ⚠️ **Advertencia:** La selección de **Equipos** define qué datos verá el usuario. Revísala con cuidado especialmente para usuarios de tipo CLIENTE.

## Editar un usuario web

1. Haz clic en **Editar** (lápiz) en su fila.
2. Ajusta el rol, estatus o equipos y haz clic en **Guardar**.

## Pendientes de exploración (iteración futura)

- [ ] Detalle de qué puede ver/hacer cada rol (matriz de permisos Administrador vs Despachador vs Cliente).
- [ ] Comportamiento del panel lateral "Filtros".
- [ ] Capturas de pantalla definitivas.
