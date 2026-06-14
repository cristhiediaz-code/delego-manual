# 12. Auditoría y trazabilidad

> ✅ Exploración en vivo completada el 13/06/2026.

Delego registra **quién hizo qué y cuándo**, tanto a nivel de cada tarea como a nivel de la cuenta. Esto te permite reconstruir lo que pasó ante una queja, una incidencia o una auditoría.

## 12.1 Registro de eventos (event log)

Hay dos niveles de registro de eventos:

### A) Historial de Eventos de una tarea
Es la línea de tiempo de **una tarea específica**. Se abre desde el listado de Tareas → botón **Ver eventos de la tarea** (ícono de reloj) en la fila (§4.3).

Muestra cada **cambio de estado** con:
- **Estado** (ej. NO ASIGNADO, ASIGNADA, EN TRÁNSITO, COMPLETADA…).
- **Fecha y hora** del cambio.
- **Autor**: quién o qué lo provocó (ej. "Cristhie Y Díaz (SYSTEM)").

Incluye un botón para **exportar** el historial.

![Historial eventos tarea](imagenes/web/12_auditoria/historial_eventos_tarea.png)

### B) Reporte Logs de Eventos (auditoría de la cuenta)
Es el registro de auditoría **de toda la cuenta**. Se abre desde menú lateral → **Reportes** → categoría **Logs** → **Logs de Eventos**.

**Filtros:**

| Filtro | Qué hace |
|---|---|
| **Desde / Hasta** | Rango de fechas. |
| **Tipo de Evento** | **CREAR**, **ACTUALIZAR** o **ELIMINAR**. |
| **Vista del Sistema** | El módulo/entidad afectada (tareas, agentes, etc.). |
| **Usuario** | Filtra por el usuario responsable. |

Pulsa **Buscar** para cargar. La tabla muestra: **ID de Evento, Tipo de Evento, Descripción, Usuario Responsable, Entidad Afectada, Estado Anterior, Nuevo Estado, Fecha**. Tiene buscador, columnas ordenables, paginación y botón **Exportar**.

![Logs de eventos](imagenes/web/12_auditoria/logs_de_eventos.png)

> 💡 **Tip:** Para investigar "¿quién cambió esto?", filtra por **Tipo de Evento = ACTUALIZAR** y por **Usuario**, y acota el rango de fechas al día del incidente. La columna **Estado Anterior → Nuevo Estado** te dice exactamente qué cambió.

## 12.2 Reporte de tareas planificadas no ejecutadas

Para detectar **tareas que se planificaron pero no se ejecutaron** (incumplimientos), Delego ofrece, en **Reportes → Eficiencia**:

- **Resumen de tareas planificadas vs ejecutadas por ruta**
- **Resumen de tareas planificadas vs ejecutadas por agente**

Estos reportes comparan lo planificado contra lo realmente ejecutado en un rango de fechas, dejando ver las tareas que quedaron sin completar (la brecha entre ambas curvas también se ve en el Dashboard, §8.2 "Planificadas Vs Completadas").

Complementariamente:
- En **Tareas Recurrentes** (§11.4), el chip **Vencidas** muestra recurrencias cuya vigencia terminó.
- El modal **Tareas planificadas** (§11.2) anticipa las tareas futuras que el sistema generará.

![Reporte planificadas vs ejecutadas](imagenes/web/12_auditoria/reporte_planificadas_vs_ejecutadas.png)

> 📝 **Nota:** Genera estos reportes filtrando **Por Fecha Planificada** para evaluar el cumplimiento del plan del día/semana.

## 12.3 Buenas prácticas de trazabilidad

- **Usa Cancelar en lugar de Eliminar** (§4.3): cancelar conserva la tarea con estado Cancelada y su historial; eliminar la borra y pierdes la trazabilidad.
- **Activa "ID Delego para tareas"** (Settings → Settings Generales, §3.9): cada tarea recibe un identificador único, fácil de referenciar en soporte, reportes e integraciones.
- **Captura motivos**: configura los **Motivos de Retroceso en la Tarea** (Settings → App del Agente, §3.9) y los motivos de On Hold (§4.6) para que cada excepción quede justificada en el registro.
- **Revisa los Logs de Eventos periódicamente** filtrando por ELIMINAR para detectar borrados no esperados.
- **Conserva el historial exportado** de tareas críticas (botón exportar del Historial de Eventos) como respaldo.
- **Mantén el correo y datos del agente reales**: el campo "Autor" del historial y la verificación de identidad dependen de ello (§3.3).

## Pendientes de exploración (iteración futura)

- [ ] Opciones completas del filtro **Vista del Sistema** en Logs de Eventos.
- [ ] Confirmar si existe un reporte dedicado y nombrado exactamente "tareas planificadas no ejecutadas" además de los de Eficiencia.
- [ ] Formatos de exportación de los Logs.
- [ ] Capturas de pantalla definitivas.
