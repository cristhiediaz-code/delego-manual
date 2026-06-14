# 8. Dashboard (Tablero de Indicadores)

> ✅ Exploración en vivo completada el 13/06/2026 (con filtro de rango amplio para poblar los gráficos).

## 8.1 ¿Qué muestra el Dashboard?

El **Tablero de Indicadores** (menú lateral → **Tablero de Indicadores**) resume el desempeño de tu operación en un periodo: cuántas tareas hubo, cómo terminaron, por equipo, por agente, por prioridad y a lo largo del tiempo. Es la vista para gerencia y supervisión (no para operar tarea por tarea).

En la cabecera, el ícono de **refrescar** (junto al título) recarga los datos.

> 📝 **Nota:** Los gráficos reflejan el **rango de fechas filtrado**. Con el rango por defecto (solo el día actual) muchos gráficos de "ejecutadas" aparecen vacíos porque las tareas del día aún no se han completado. **Filtra un rango pasado amplio para ver datos históricos** (§8.3).

## 8.2 Indicadores principales

### Tarjetas KPI (parte superior)

| Tarjeta | Qué mide |
|---|---|
| **Total Tareas** | Total de tareas en el periodo. |
| **Completadas** | Cantidad y **% del total**. |
| **Parcialmente Completadas** | Cantidad y %. |
| **Rechazadas** | Cantidad y %. |
| **Canceladas** | Cantidad y %. |
| **Completadas a Tiempo** | Cantidad y % (cumplimiento de ventana / On Time). |

![Dashboard kpis](imagenes/web/08_dashboard/dashboard_kpis.png)

### Gráficos

| Gráfico | Tipo | Qué muestra |
|---|---|---|
| **Distribución % de tareas ejecutadas por estatus** | Pastel | Reparto entre Completada, Rechazada, Parcialmente, Cancelada (ej. Completada 84.3%, Rechazada 7.2%, Cancelada 4.6%, Parcialmente 3.8%). |
| **Distribución % de tareas ejecutadas por prioridad** | Dona | Reparto Normal vs Alta (ej. Normal 90.7%, Alta 9.3%). |
| **Cantidad de tareas ejecutadas por equipos** | Barras horizontales | Tareas por equipo, segmentadas por estado (Completada / Parcialmente / Rechazada / Cancelada / Pendiente por ejecutar). |
| **Cantidad de tarea planificadas Vs Completadas** | Líneas en el tiempo | Compara la curva de **Planificada** contra **Completada** por fecha. |
| **Cantidad de tareas ejecutadas por estatus** | Área en el tiempo | Volumen diario por estado a lo largo del periodo. |
| **Cantidad de tareas por agentes** | Barras horizontales | Tareas por agente, segmentadas por estado (incluye **Asignada**). Tiene scroll para recorrer todos los agentes. |
| **Cantidad de tareas planificadas y completas por modo** | Barras | Desglose por Modo de Tarea (Inmediata, Programada, etc.). |

![Dashboard graficos estatus prioridad](imagenes/web/08_dashboard/dashboard_graficos_estatus_prioridad.png)
![Dashboard graficos equipos tiempo](imagenes/web/08_dashboard/dashboard_graficos_equipos_tiempo.png)
![Dashboard grafico agentes](imagenes/web/08_dashboard/dashboard_grafico_agentes.png)

> 💡 **Tip:** El gráfico **Planificadas Vs Completadas** es el más útil para detectar brechas de cumplimiento: cuando la línea Completada queda muy por debajo de la Planificada en una fecha, hubo tareas que no se ejecutaron.

## 8.3 Filtros y rangos de tiempo

El panel **Filtros** (pestaña vertical **Búsqueda Avanzada** en el borde derecho) controla qué datos alimentan todo el tablero:

| Filtro | Qué hace |
|---|---|
| **Equipo** | Limita a uno o varios equipos. |
| **Agentes** | Limita a agentes específicos. |
| **Tipos de Tareas** | Limita a ciertos tipos de tarea. |
| **Desde / Hasta** | Define el **rango de fechas** (con calendario). |

Pasos: ajusta los filtros → **Buscar** para aplicar (los gráficos se recalculan) → **Cancelar** para descartar.

![Dashboard panel filtros](imagenes/web/08_dashboard/dashboard_panel_filtros.png)

> 💡 **Tip:** Para revisar el desempeño histórico, abre **Filtros**, pon una fecha **Desde** anterior (ej. inicio de año) y **Hasta** hoy, y pulsa **Buscar**. En la cuenta de ejemplo, ampliar el rango a más de un año mostró 15.560 tareas con todos los gráficos poblados, frente a 25 del día actual.

> 📝 **Nota:** El selector de fecha es un calendario: haz clic en el campo **Desde**, navega con las flechas o tocando el **año/mes** del encabezado para saltar rápido, y elige el día.

## 8.4 Lectura e interpretación de los datos

- **Salud general:** mira primero las tarjetas KPI — un % alto de Completadas y Completadas a Tiempo indica buena operación; % altos de Rechazadas/Canceladas son señal de alerta.
- **Dónde está el problema:** usa "por equipos" y "por agentes" para localizar qué equipo o agente concentra rechazos/cancelaciones.
- **Tendencia:** usa los gráficos temporales (Planificadas vs Completadas, ejecutadas por estatus) para ver si el desempeño mejora o empeora en el tiempo.
- **Mix de trabajo:** "por prioridad" y "por modo" te dicen qué tipo de operación predomina.

## Pendientes de exploración (iteración futura)

- [ ] Confirmar si los gráficos permiten *drill-down* (clic para filtrar) o exportación.
- [ ] Detalle del gráfico "por modo" con datos.
- [ ] Capturas de pantalla definitivas.
