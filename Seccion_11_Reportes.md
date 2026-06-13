# 11. Reportes

> ✅ Exploración en vivo completada el 13/06/2026.
> 📝 Los reportes se dividen en **Estándar de Delego** y **Personalizados**. De los personalizados, este manual documenta el flujo **BETA** (los personalizados clásicos están en proceso de **deprecación**).

El módulo **Reportes** (menú lateral → **Reportes**) permite *"consultar, analizar y exportar información operativa y de desempeño para apoyar la toma de decisiones"*. Tiene tres bloques: **Reportes Estándar**, **Reportes Personalizados** (clásicos) y **Reportes Personalizados BETA**.

## 11.1 Reportes disponibles

### Reportes Estándar de Delego
Vienen predefinidos, agrupados en **4 categorías**:

| Categoría | Reportes |
|---|---|
| **Eficiencia** | Resumen de tareas planificadas vs ejecutadas por ruta · ...por agente · Resumen de Rutas · Resumen de tareas por fecha |
| **Productividad** | Gestión del Operador (Resumen de los Agentes) · Gestión del Agente (Detalle de las Tareas) · Reporte de calidad de la geocodificación |
| **Operaciones** | Listado de Agentes · Manifiesto de Ruta · Resumen de Tareas Ejecutadas - Formularios · Listado de Clientes |
| **Logs** | Logs de Eventos |

### Reportes Personalizados (clásicos)
Reportes en **Formato Word (.docx)** y **Formato Excel (.xlsx)** diseñados a medida. *"Pueden utilizarse como adjuntos en notificaciones o descargarse bajo demanda."*

> ⚠️ **Advertencia:** Este bloque clásico está en proceso de **deprecación**. Para nuevos reportes personalizados, usa **Reportes Personalizados BETA** (§11.5).

### Reportes Personalizados BETA
La versión vigente de reportes a medida. Se organizan **por tipo de tarea / formulario**, con buscador, y son los que se adjuntan a las notificaciones BETA (§10.4).

[CAPTURA: reportes_vista_general.png]

## 11.2 Generar un reporte estándar bajo demanda

1. Haz clic en el nombre de un reporte estándar (ej. **Resumen de tareas por fecha**). Se abre un modal con dos pestañas: **Filtros y campos de informe** y **Resultado**.
2. En **Filtros y campos de informe**:
   - **Parámetros de filtros**: atajos rápidos **Hoy / Esta Semana / Este Mes**; alternar **Por Fecha Planificada / Por Fecha Ejecutada**; rango **Desde / Hasta**; y filtros por **Agente** y **Equipo**.
   - **Seleccione los campos del reporte**: marca/desmarca las **columnas** a incluir (con opción **Seleccionar Todos**). Hay decenas: Fecha/Hora Planificada y de Ejecución, Nombre y Tipo de tarea, Modalidad, Prioridad, Estatus, Ruta/Id Ruta, Equipo, Nombre Agente, Tarea N°, Secuencias planificada/ejecutada, Capacidad 1–5, Distancia, Coordenadas de Ejecución, Items/Total de Items, Duración Servicio, Ciudad, Comentarios, Instrucciones, Motivos, ID Orden, etc.
   - **Campos personalizados del reporte (TAREAS)**: añade campos personalizados del formulario.
3. Haz clic en **Cargar Datos**.
4. Se abre la pestaña **Resultado** con la **tabla** de datos: buscador, columnas ordenables y paginación (ej. "Mostrando 1 al 10 de 25 registros").
5. Haz clic en **Exportar** (tiene un desplegable para elegir el formato de salida) para descargar el reporte.

[CAPTURA: reporte_estandar_filtros.png]
[CAPTURA: reporte_estandar_resultado.png]

> 💡 **Tip:** Selecciona solo las columnas que necesitas antes de Cargar Datos: un reporte más liviano se genera y exporta más rápido, y es más fácil de leer.

## 11.5 Crear/personalizar reportes (Reportes Personalizados BETA)

Los reportes personalizados BETA se diseñan a partir de una **plantilla** asociada a un **formulario / tipo de tarea**.

1. En el bloque **Reportes Personalizados BETA**, haz clic en el botón **+**.
2. Se abre **Crear reporte personalizado** con la pestaña **Plantilla**: un listado de **Formulario Personalizado** (por tipo de tarea), con buscador y paginación. Cada uno tiene dos opciones:
   - **Descargar** (plantilla base) — bajas el archivo modelo para diseñarlo.
   - **Subir** — cargas tu plantilla ya diseñada.
3. Diseña la plantilla (Word/Excel) usando los campos del formulario y vuelve a **subirla**.

[CAPTURA: reporte_beta_crear_plantilla.png]

Una vez creado, el reporte BETA aparece bajo su tipo de tarea con acciones de **descargar**, **configurar** (engranaje) y **expandir**. Desde ahí queda disponible para:
- **Descargarse bajo demanda**.
- **Adjuntarse a notificaciones BETA** (§10.4).

> 💡 **Tip:** Como los reportes BETA se asocian a un formulario/tipo de tarea, crea uno por cada tipo de comprobante que necesites (ej. comprobante de entrega, acta de visita) y reutilízalo en las notificaciones de ese tipo de tarea.

## Pendientes de exploración (iteración futura)

- [ ] Formatos exactos del botón **Exportar** (Excel/PDF/CSV — confirmar el desplegable).
- [ ] **11.3 Programar reportes recurrentes** y **11.4 Ventana de descargas / reportes asíncronos**: no se identificó un programador de reportes ni una bandeja de descargas asíncronas en esta vista; verificar si existen (quizá vía el engranaje de un reporte BETA o un módulo aparte).
- [ ] Detalle del editor de configuración (engranaje) de un reporte BETA existente.
- [ ] Capturas de pantalla definitivas.
