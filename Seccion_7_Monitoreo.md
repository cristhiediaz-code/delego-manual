# 7. Monitoreo en tiempo real

> ✅ Exploración en vivo completada el 13/06/2026.

El monitoreo en tiempo real ocurre en la pantalla **Operaciones** (menú lateral → **Operaciones**), la misma desde donde se asigna y planifica (§5 y §6). Combina el **listado de tareas**, el **mapa operativo** y paneles laterales. Aquí el dispatcher ve dónde está cada agente, en qué estado, y resuelve excepciones sobre la marcha.

## 7.1 Mapa operativo

El mapa muestra, en vivo:
- **Pines de tareas** — cada tarea geocodificada, con color según su estado (§4.4).
- **Pines de agentes** — marcadores con las **iniciales** del agente (ej. "MS", "LH", "JF"), ubicados en su última posición reportada.
- Controles de **zoom (+/−)**, brújula, pantalla completa, herramientas de medición y **Buscar lugar** (esquina superior derecha).

### Capas (CAPAS)
El control **CAPAS** (abajo a la izquierda) permite encender/apagar capas sobre el mapa:

| Capa | Qué muestra |
|---|---|
| **Equipos** | Las **zonas geográficas** dibujadas para los equipos (las que usa la autoasignación por zona, §3.2). |
| **Tareas Ejecutadas** | Los puntos donde se ejecutaron tareas (histórico sobre el mapa). |

![Monitoreo mapa capas](imagenes/web/07_monitoreo/monitoreo_mapa_capas.png)

> 💡 **Tip:** Enciende la capa **Equipos** para ver visualmente si una tarea cayó dentro o fuera de la zona de su equipo, y la capa **Tareas Ejecutadas** para detectar concentraciones de actividad.

## 7.2 Estado de agentes y vehículos

Al hacer **clic en el pin de un agente** en el mapa, se abre su **tarjeta de estado en tiempo real**:

| Dato | Qué indica |
|---|---|
| **Nombre** | El agente (ej. "MICHAEL SCHUMACHER PANAMÁ"). |
| **Último reporte** | Fecha y hora del último ping GPS del dispositivo (ej. 30/04/2026 14:21). |
| **Estatus** | Estado operativo: **AVAILABLE** (disponible, verde), entre otros. |
| **Coordenadas** | Latitud y longitud de su última posición. |

![Monitoreo tarjeta agente](imagenes/web/07_monitoreo/monitoreo_tarjeta_agente.png)

El panel lateral **Recursos** (pestaña en el borde derecho) lista todos los agentes y vehículos con su capacidad, equipos, habilidades y carga de tareas, como vista consolidada.

## 7.3 Alertas y agentes inalcanzables

El campo **Último reporte** es la clave para detectar **agentes inalcanzables**: si la fecha/hora del último ping es muy antigua respecto a la actual, el dispositivo del agente no está reportando (app cerrada, sin señal, GPS apagado).

> 💡 **Tip:** Revisa el **Último reporte** de cada agente antes de asignarle tareas urgentes. Un reporte de hace horas (o días) indica que no podrás confiar en su ubicación en vivo ni en que reciba la tarea de inmediato.

> 📝 **Nota:** El **Estatus** (AVAILABLE, etc.) complementa la ubicación: un agente puede estar reportando posición pero no estar disponible para recibir trabajo.

## 7.4 Acciones rápidas desde el monitoreo

Desde la tarjeta de estado de un agente, el menú **...** (tres puntos) ofrece acciones rápidas:

| Acción | Qué hace |
|---|---|
| **Ver Estatus del Agente** | Abre un resumen de la **carga de trabajo** del agente: tareas **Pendientes**, **Completadas** y **Rechazadas** (con buscador). |
| **Ver Calendario del Agente** | Abre el calendario/agenda del agente para ver su programación. |

![Monitoreo acciones agente](imagenes/web/07_monitoreo/monitoreo_acciones_agente.png)

Además, desde el listado/mapa de tareas se accede a todas las acciones de asignación y excepción mediante **clic derecho** (menú contextual, §5): Asignación Directa, Publicar, Desasignar, Cancelar, Invalidar Localización, etc. Esto convierte el monitoreo en un centro de control accionable, no solo de visualización.

## Pendientes de exploración (iteración futura)

- [ ] Lista completa de valores de **Estatus** del agente (además de AVAILABLE).
- [ ] Detalle del panel **Recursos** consolidado y del **Calendario del Agente**.
- [ ] Capturas de pantalla definitivas.
