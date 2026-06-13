# 6. Planificación y optimización de rutas

> ✅ Documentada en vivo el 12–13/06/2026, incluyendo una **ejecución completa del optimizador** con su resultado, indicadores y costos.

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

> ⚠️ **Advertencia (regla clave):** El o los **agentes/vehículos elegidos deben pertenecer al mismo equipo que las tareas**. Si no, Delego bloquea la optimización con el mensaje: *"No es posible crear Rutas — Parece que estás intentando crear una ruta con agentes/vehículos que no pertenece a los equipos de las tareas. Inténtalo nuevamente seleccionando otros agentes."* Verifica el equipo de las tareas (pestaña Tarea → Equipo) y elige un recurso de ese mismo equipo. Si necesitas mover varias tareas a otro equipo de golpe, usa **Edición Masiva** (§5.4).

> ⚠️ **Advertencia (ventana y capacidad):** Si el agente no alcanza a atender las tareas dentro de la jornada (su punto de partida está demasiado lejos, o el tiempo de viaje + servicio excede la ventana) o se supera su capacidad, verás: *"Las tareas que has seleccionado para crear esta ruta no pueden ser atendidas debido a que se encuentran fuera de la ventana de atención planificada o superan la capacidad máxima de los agentes seleccionados."* Soluciones: amplía la ventana (Hora inicio/final), elige un **Punto de partida** más cercano (ej. un hub próximo) o reduce la cantidad de tareas.

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

Se controlan con **Punto de partida** y **Punto final** (§6.2). Cada selector es una lista con buscador que incluye:

- **Posición Actual Agente** — la última ubicación GPS conocida del agente.
- **Dirección del Agente** — su dirección de pernocta (base).
- **Posición Último Pedido** (solo en Punto final) — termina donde cae la última tarea de la ruta.
- **Cualquier Hub** de tu cuenta (ej. *COAP - Panamá*, *Oviensa*, *Centro Operativo...*) — útil para que la ruta arranque/termine en una bodega o centro.

> 💡 **Tip:** Si la optimización falla por "ventana de atención" (§6.1), suele deberse a que *Posición Actual Agente* no existe o está muy lejos. Cambiar el **Punto de partida** a un **hub cercano a las tareas** resuelve el cálculo. En la prueba documentada, partir desde el hub *COAP - Panamá* permitió generar la ruta con éxito.

## 6.4 Ajuste manual de la ruta propuesta

Tras pulsar **Siguiente**, el motor calcula y se abre la vista **Resultados Planificación de Rutas** (panel izquierdo), con dos grupos:

- **Tareas sin planificar** — las que no pudieron entrar en ninguna ruta (con su conteo).
- **Ruta - 1**, **Ruta - 2**, … — cada ruta generada, con un **nombre editable** y un contador de paradas. Cada ruta tiene un ícono de **previsualización** (ojo) para verla resaltada en el mapa.

Al **expandir** una ruta puedes ver el orden de las paradas y reordenarlas, quitar una tarea o moverla a otra ruta antes de confirmar. El mapa muestra el recorrido propuesto.

[CAPTURA: resultados_planificacion_rutas.png]

## 6.5 Indicadores de ruta

El panel derecho **Resumen de Rutas** muestra los indicadores de cada ruta para evaluarla antes de asignarla. En la ejecución de ejemplo (3 tareas, agente CLEOFAS, partida desde COAP - Panamá):

| Indicador | Qué significa | Valor de ejemplo |
|---|---|---|
| **Tareas planificadas** | Cuántas tareas entraron en rutas. | 3 |
| **Tareas sin planificar** | Cuántas quedaron fuera. | 0 |
| **Identificador de ruta/compartimiento** | Código de la ruta (ej. C1). | C1 |
| **Uso (%)** | Porcentaje de aprovechamiento de la capacidad del recurso. | 0% |
| **Distancia** | Kilómetros totales del recorrido. | 12.20 km |
| **Duración** | Tiempo total estimado. | (ver Nota) |
| ↳ **Conducción** | Tiempo manejando. | 00h 13m |
| ↳ **Servicio** | Tiempo atendiendo en sitio. | 00h 15m |
| ↳ **Espera** | Tiempo de espera entre paradas. | 00h 00m |

Cada tarjeta de ruta (panel der. y listado izq.) resume **Uso (%)**, **Distancia** y **Duración** de un vistazo.

[CAPTURA: resumen_de_rutas_indicadores.png]

> 📝 **Nota:** En la prueba, la **Duración** total se mostró como un valor negativo ("-5h -31m"), inconsistente con el desglose (Conducción 13m + Servicio 15m). Es un comportamiento a verificar; los sub-totales de Conducción/Servicio/Espera sí son confiables.

## 6.6 Costos y confirmación de la ruta

Los indicadores de **Distancia** y **Duración** (con su desglose) son la base del costo operativo de la ruta: permiten comparar alternativas (distinto agente, distinto punto de partida, distinto modo de optimización) y elegir la más eficiente antes de comprometerla.

Cuando la ruta propuesta te convence, haz clic en **Asignar a Ruta** para asignarla al agente (las tareas pasan a **Asignadas**). Usa **Atrás** para reconfigurar o **Cancelar** para descartar la propuesta sin asignar.

[CAPTURA: boton_asignar_a_ruta.png]

## 6.7 Rutas recurrentes

Desde la ventana de optimización **también puedes configurar la ruta como recurrente** (que se repita automáticamente en una cadencia: diaria, semanal, etc.), de modo que el mismo recorrido se genere periódicamente sin rehacerlo a mano.

> ⚠️ **Advertencia:** La opción de recurrencia de ruta **solo aparece si ninguna de las tareas seleccionadas tiene ya su propia recurrencia**. Si incluyes una tarea recurrente, Delego oculta la opción y, al intentar aplicarla, muestra: *"No se puede aplicar recurrencia a la ruta seleccionada, ya que algunas tareas incluidas tienen configurada una recurrencia. Revisa y ajusta las tareas individuales antes de intentar establecer una recurrencia para la ruta en su totalidad."*
>
> Para crear una **ruta recurrente**, parte de **tareas sin recurrencia propia**.

[CAPTURA: ruta_recurrente_opcion.png]

## Pendientes de exploración (iteración futura)

- [ ] Diferencias exactas entre **Planif. Rutas** (básico) y **Planif. Avanzada de Rutas**.
- [ ] El modo **Múltiples Compartimientos (Beta)**.
- [ ] Captura visual de la opción de **ruta recurrente** con tareas no recurrentes.
- [ ] Capturas de pantalla definitivas (marcadas arriba).
