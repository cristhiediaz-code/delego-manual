# 6. Planificación y optimización de rutas

> ✅ Configuración del optimizador documentada en vivo el 12/06/2026.
> ⚠️ Algunas vistas de **resultado** (ruta propuesta, indicadores y costos) quedaron parcialmente documentadas: en la cuenta demo las tareas cargadas pertenecen a un equipo sin agente disponible para rutear, lo que impidió completar una optimización de ejemplo. Se detallan con la información disponible y se marcan los pendientes.

## 6.1 El planificador de rutas

Cuando una operación tiene muchas tareas que un mismo agente debe cubrir en un día, en lugar de asignarlas una por una conviene **optimizar una ruta**: que Delego calcule el mejor orden de visita. Hay dos modalidades (desde el menú contextual de Operaciones, §5):

- **Planif. Rutas** — optimizador básico, premisa: la **ruta más corta**.
- **Planif. Avanzada de Rutas** — optimizador completo: considera capacidades, tiempos de servicio, ventanas de atención, habilidades, tráfico y más. **Es la única modalidad que también permite rutear a vehículos**.

### Flujo general

1. En **Operaciones**, selecciona las tareas a rutear (checkbox del listado o shift+drag en el mapa).
2. **Clic derecho** → **Planif. Avanzada de Rutas** (o **Planif. Rutas**).
3. Se abre el panel **Recursos** para elegir el/los **agentes** (y vehículos) que ejecutarán la ruta. Marca su checkbox → **Siguiente**.
4. Se abre el panel **Planificación de la Ruta** con la **Configuración de Optimización** (§6.2).
5. Ajusta las palancas y haz clic en **Siguiente** para que el motor calcule la ruta.
6. Revisa la ruta propuesta, sus indicadores y costos; ajústala si hace falta (§6.4–6.6) y **confirma** para asignarla.

> ⚠️ **Advertencia (regla clave):** El o los **agentes/vehículos elegidos deben pertenecer al mismo equipo que las tareas**. Si no, Delego bloquea la optimización con el mensaje: *"No es posible crear Rutas — Parece que estás intentando crear una ruta con agentes/vehículos que no pertenece a los equipos de las tareas. Inténtalo nuevamente seleccionando otros agentes."* Verifica el equipo de las tareas (pestaña Tarea → Equipo) y elige un recurso de ese mismo equipo.

> 💡 **Tip:** El panel de selección de recursos tiene buscador y la opción **Seleccionar todos los agentes**. Cada agente muestra su capacidad, equipos, habilidades y carga actual de tareas, para que elijas con criterio.

## 6.2 Reglas y palancas del optimizador

El panel **Planificación de la Ruta → Configuración de Optimización** expone estas palancas:

[CAPTURA: panel_optimizador_configuracion.png]

| Palanca | Qué controla | Valores observados |
|---|---|---|
| **Punto de partida** | Dónde inicia la ruta. | "Posición Actual" (del agente), entre otros. |
| **Punto final** | Dónde termina la ruta. | "Posición Última" (último punto), entre otros. |
| **Tiempo de servicio** | Cómo se calcula el tiempo en cada parada. | "Tiempo de Tarea" (el definido en la tarea), entre otros. |
| **Modo de optimización** | El objetivo que prioriza el motor. | **Balancear Prioridad**, **Balancear Distancia y Tiempo** (default), **Múltiples Compartimientos (Beta)**. |
| **Modo de Movilidad** | Perfil de desplazamiento a usar. | "Todos…" (o un modo específico: peatonal, vehículo, etc.). |
| **Tráfico** | Si considera condiciones de tráfico. | **Habilitado** / deshabilitado. |
| **Capacidades a considerar** | Qué capacidad limita la carga de la ruta. | "Capacidad 1 (kg)" (o 2-5 según tu cuenta). |
| **Considerar Habilidades** (toggle) | Si exige que el agente tenga las habilidades de cada tarea. | Activado / desactivado. |
| **Considerar Equipos** (toggle) | Si respeta la pertenencia a equipos. | Activado por defecto. |

**Configuración General:**

| Campo | Qué define |
|---|---|
| **Fecha de visita** | El día para el que se planifica la ruta. |
| **Hora inicio** | Inicio de la jornada (ej. 07:00). |
| **Hora final** | Fin de la jornada (ej. 17:00). La ruta se ajusta a esta ventana. |

Botones del panel: **Atrás** (volver a elegir recursos), **Siguiente** (calcular), **Cancelar**.

> 💡 **Tip:** **Modo de optimización** es la palanca de negocio más importante: usa *Balancear Distancia y Tiempo* para eficiencia general, *Balancear Prioridad* cuando hay tareas urgentes que deben ir primero aunque el recorrido sea menos eficiente.

## 6.3 Puntos de inicio y fin de ruta

Se controlan con **Punto de partida** y **Punto final** (§6.2). Lo habitual:
- **Partida = Posición Actual** del agente (o su dirección de pernocta).
- **Fin = Posición Última** (termina donde cae la última tarea) o un retorno al hub.

[PENDIENTE: lista completa de opciones de cada selector]

## 6.4 Ajuste manual de la ruta propuesta

Tras calcular, Delego muestra la ruta sugerida en el mapa con el orden de paradas numerado. Desde ahí puedes **reordenar paradas**, **quitar** una tarea de la ruta o **mover** una tarea a otra ruta antes de confirmar.

[PENDIENTE: capturar la vista de ruta propuesta y los controles de reordenamiento — bloqueado por data demo, ver nota inicial]

## 6.5 Indicadores de ruta (On Time, Eficiencia, Hora de llegada)

Cada ruta propuesta muestra indicadores para evaluar su calidad antes de confirmar: cumplimiento de ventanas (**On Time**), **eficiencia** del recorrido y **hora de llegada / ETA** estimada por parada.

[PENDIENTE: capturar valores y ubicación exacta de los indicadores — bloqueado por data demo]

## 6.6 Costos de ruta

El optimizador estima el **costo** de la ruta (combustible/distancia/tiempo según la parametrización de la cuenta), para comparar alternativas.

[PENDIENTE: capturar el desglose de costos — bloqueado por data demo]

## Pendientes de exploración (iteración futura)

- [ ] Ejecutar una optimización completa con tareas y agente del **mismo equipo** para documentar 6.4–6.6 (ruta propuesta, indicadores, costos).
- [ ] Diferencias exactas entre **Planif. Rutas** (básico) y **Planif. Avanzada de Rutas**.
- [ ] Opciones completas de cada selector (Punto de partida/final, Tiempo de servicio, Modo de Movilidad).
- [ ] El modo **Múltiples Compartimientos (Beta)**.
- [ ] Capturas de pantalla definitivas.
