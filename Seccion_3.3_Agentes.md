# 3.3 Agentes

> ✅ Exploración en vivo completada el 12/06/2026 (sin crear agentes reales para no disparar correos de credenciales).

## ¿Qué es?

Los **Agentes** son las personas que ejecutan las tareas en campo a través de la app móvil de Delego. Pueden pertenecer a múltiples equipos al mismo tiempo y tienen habilidades que determinan qué tipos de tareas pueden realizar.

> 💡 **Tip:** Asigna agentes a los equipos que necesites y asegúrate de que tengan las habilidades para las tareas que van a realizar: más flexibilidad, mejor operación. Podrás asignarlos a equipos y habilidades después de crearlos.

## Acceder al módulo

1. En el menú lateral, haz clic en **Recursos operativos**.
2. Selecciona **Agentes**.

[CAPTURA: menu_recursos_agentes.png]

## El listado de agentes

[CAPTURA: listado_agentes.png]

| Columna | Qué muestra |
|---|---|
| ☑️ (checkbox) | Selección múltiple. |
| **Nombre / Apellido** | Identificación del agente. |
| **Correo Electrónico** | Su llave de acceso a la app móvil (única). |
| **Habilidades** | Las habilidades asignadas (o `N/A`). |
| **Estatus** | **ACTIVO** / **INACTIVO**. |
| **¿Verificado?** | **VERIFICADO** (verde) si el agente ya validó su cuenta e ingresó a la app; **NO VERIFICADO** (gris) si aún no lo hace. |
| **Opciones** | **Editar** (lápiz) siempre; **Reenviar Credenciales** solo mientras el agente está NO VERIFICADO. |

> 📝 **Nota:** Los agentes **no se eliminan** desde el listado: no existe botón de papelera. Para retirar a un agente de la operación, edítalo y cambia su Estatus a **INACTIVO**. Así conservas la trazabilidad de las tareas que ejecutó.

> 💡 **Tip:** ¿El agente no recibió su contraseña o la perdió antes de entrar por primera vez? Haz clic en **Reenviar Credenciales** en su fila. El botón desaparece cuando el agente ya está verificado.

Las herramientas del listado (búsqueda, ordenamiento, filtros y exportación CSV/Excel/PDF) funcionan igual que en los demás módulos. El botón **?** muestra el diagrama "Agrega tu primer agente".

## Crear un agente

1. Haz clic en el botón **+**.
2. Se abre el modal **Detalles de Agente** con **cuatro pestañas**.

### Pestaña 1: Datos del Agente

| Campo | Obligatorio | Descripción |
|---|---|---|
| **Nombre** | ✅ | Nombre del agente. |
| **Apellido** | ✅ | Apellido del agente. |
| **Estatus** | ✅ | ACTIVO / INACTIVO. |
| **Equipos** | ✅ | Uno o varios equipos operativos que agrupan a los agentes según su función o zona. Facilita la gestión y asignación de tareas por grupo. |
| **Tipo Agente** | Opcional | Etiqueta de clasificación (ej. Motorizado, Técnico, Médico). Permite clasificar a los agentes disponibles en las vistas y reportes. |
| **Correo Electrónico** | ✅ | Correo principal del agente. Se usa para el acceso a la app, recepción de notificaciones y verificación de identidad. **No se puede editar después.** |

[CAPTURA: modal_agente_datos.png]

### Pestaña 2: Opciones avanzadas de optimización

| Campo | Obligatorio | Descripción |
|---|---|---|
| **Modo de Movilidad** | ✅ | Cómo se moviliza el agente: **Peatonal, Bicicleta, Vehículo, Camión, Motocicleta**. Es clave para el cálculo de rutas y asignaciones optimizadas. |
| **Capacidad 1 a 5** | ✅ (al menos la capacidad aplicable) | Capacidades de carga del agente en las unidades configuradas en tu cuenta (ej. kg, m3, m, pallet, caj.). El optimizador las usa para no sobrecargar al agente. |
| **Habilidades** | Opcional | Selección múltiple de las habilidades del agente. Determinan qué tipos de tarea puede atender. |
| **Dirección de pernocta de agente** | ✅ | La dirección desde donde parte y regresa el agente. Se usa para calcular rutas desde su ubicación base. |
| **Latitud / Longitud** | ✅ | Se autocompletan al ingresar la dirección. |

[CAPTURA: modal_agente_optimizacion.png]

> 💡 **Tip:** Este modal resalta en rojo los campos faltantes después de un intento de guardado, además del mensaje resumen ("Debes ingresar el nombre / el apellido / el correo electrónico / el estatus / la dirección / el tipo de movilidad / la capacidad / el equipo al que pertenece").

### Pestaña 3: Vehículo asociado

Totalmente opcional. Selecciona el **ID Vehículo** de la lista (el vehículo debe existir en **Recursos operativos → Vehículos**); los campos **Marca**, **Modelo** y **Tipo Vehículo** se completan con los datos del vehículo.

[CAPTURA: modal_agente_vehiculo.png]

### Pestaña 4: Campos personalizados

Muestra los campos adicionales definidos por el administrador para la entidad Agente en **Configuraciones → Campos Personalizados** (ej. "Número de Teléfono"). Son opcionales.

3. Completa las pestañas y haz clic en **Guardar**.

> 📝 **Nota:** Al crear el agente, Delego le envía automáticamente sus **credenciales temporales** al correo registrado para que entre a la app móvil. Por eso el correo debe ser real y único. Mientras no entre, su columna ¿Verificado? mostrará **NO VERIFICADO**.

## Editar un agente

1. Haz clic en **Editar** (lápiz) en la fila del agente.
2. Se abre el mismo modal con los datos precargados (recuerda: el **Correo Electrónico no es editable**).
3. Guarda los cambios con **Guardar**.

## Pendientes de exploración (iteración futura)

- [ ] Confirmar el comportamiento exacto de "Reenviar Credenciales" (mensaje de confirmación, correo que llega).
- [ ] Verificar si la selección múltiple (checkboxes) habilita alguna acción masiva en este módulo.
- [ ] Lista completa de opciones de Modo de Movilidad (puede haber más bajo scroll).
- [ ] Capturas de pantalla definitivas.
