# 3.4 Vehículos

> ✅ Exploración en vivo completada el 12/06/2026 (modal mapeado sin crear registros).

## ¿Qué es?

Los **Vehículos** son recursos operativos opcionales que puedes asociar a tus agentes. Aportan capacidades de carga propias y participan en la planificación avanzada de rutas (es la única modalidad de asignación que también permite asignar tareas a vehículos).

## Acceder al módulo

1. En el menú lateral, haz clic en **Recursos operativos**.
2. Selecciona **Vehículos**.

## El listado de vehículos

[CAPTURA: listado_vehiculos.png]

| Columna | Qué muestra |
|---|---|
| **ID Vehículo** | El identificador del vehículo (ej. placa o código interno). |
| **Marca** | Marca del vehículo. |
| **Tipo de Vehículo** | **EXTERNO**, **INTERNO** o ambos. |
| **Habilidades** | Habilidades del vehículo (ej. REFRIGERADO, CARGA PESADA). |
| **Nombre y Apellido** | El agente asociado al vehículo (si tiene). |
| **Dirección del Vehículo** | Su dirección de pernocta. |
| **Opciones** | **Editar** (lápiz). |

> 📝 **Nota:** Al igual que los agentes, los vehículos **no se eliminan** desde el listado (no hay papelera). Para retirarlos de la operación cambia su Estatus a **INACTIVO** desde Editar.

Las herramientas del listado (búsqueda, ordenamiento, filtros por columna y exportación CSV/Excel/PDF) funcionan igual que en los demás módulos.

## Crear un vehículo

1. Haz clic en el botón **+**.
2. Se abre el modal **Detalles de vehículos** con **cuatro pestañas**.

### Pestaña 1: Datos del Vehículo

| Campo | Obligatorio | Descripción |
|---|---|---|
| **ID vehículo** | ✅ | Identificador único (ej. placa). |
| **Estatus** | ✅ | ACTIVO / INACTIVO. |
| **Marca** | Opcional | Lista desplegable. |
| **Modelo** | Opcional | Lista desplegable. |
| **Tipo** | Opcional | Lista desplegable (ej. Externo / Interno). |
| **Equipos** | ✅ | El o los equipos donde opera el vehículo. |

[CAPTURA: modal_vehiculo_datos.png]

### Pestaña 2: Opciones avanzadas de optimización

El mismo patrón que en Agentes:

- **Capacidad 1 (obligatoria) a Capacidad 5**: valores numéricos que representan la capacidad del vehículo en las unidades de tu cuenta (kg, m3, m, pallet, caj.).
- **Modo de movilidad** (obligatorio).
- **Habilidades** del vehículo (ej. Refrigerado): determinan qué tipos de tarea puede atender.
- **Dirección de pernocta de vehículo** (obligatoria) + **Latitud / Longitud** (se autocompletan).

### Pestaña 3: Agente asociado

Selecciona en **Nombre y Apellido** al agente que usará el vehículo; los campos **Equipos**, **Correo** y **Tipo** se completan automáticamente con los datos del agente. Es opcional y también puede hacerse desde la ficha del agente (pestaña Vehículo asociado).

### Pestaña 4: Campos personalizados

Campos adicionales definidos por el administrador para la entidad Vehículo.

3. Haz clic en **Guardar**.

> ⚠️ **Advertencia:** Si guardas con campos incompletos verás el resumen: "Debes ingresar el ID de identificación / el estatus / la capacidad 1 / indicar dirección / coordenada de latitud / coordenada de longitud / seleccionar el equipo al que pertenece". La **Capacidad 1 es obligatoria** para que el optimizador pueda trabajar.

## Editar un vehículo

1. Haz clic en **Editar** (lápiz) en la fila.
2. Ajusta los campos en el mismo modal y haz clic en **Guardar**.

## Pendientes de exploración (iteración futura)

- [ ] Opciones disponibles en las listas Marca / Modelo / Tipo (¿catálogos administrables?).
- [ ] Capturas de pantalla definitivas.
