# 14. Solución de problemas y preguntas frecuentes

> Recopilación de las dudas y situaciones más comunes al operar Delego Web, con su solución. Organizada por tema.

## Acceso y sesión

**No puedo entrar / la pantalla se queda en blanco.**
Verifica que tu **correo y contraseña** sean correctos y que tengas conexión. Si entraste por primera vez con una **contraseña temporal**, recuerda que es de un solo uso y debes cambiarla (§2.1).

**Se me cerró la sesión sola / volví al login.**
Vuelve a iniciar sesión. Para no perder trabajo, **guarda los cambios** de un formulario antes de dejarlo inactivo mucho tiempo: si la sesión expira mientras tienes un modal abierto, el contenido no guardado se pierde.

**La plataforma está en inglés (o en otro idioma).**
Cámbialo en **Configuraciones ⚙️ → Preferencias → Platform language** (Español / English / Português). El idioma de la plataforma es independiente del **idioma de las notificaciones** (ese se ajusta en Notificaciones, §9).

## Configuración inicial

**No me deja crear un equipo.**
Primero debes tener al menos un **Hub (centro)** creado. El orden es: **Tipo de tarea → Hub → Equipo → Agente** (§2.3). Sin hub no se puede guardar un equipo.

**No me deja guardar un tipo de tarea.**
La **Descripción** y el **Estatus** son obligatorios. Si guardas en vacío verás "Debes ingresar la descripción del tipo de tarea / Debes seleccionar el estatus" (§3.1).

**No encuentro dónde asociar el formulario al tipo de tarea.**
No se hace desde Tipos de Tareas, sino desde **Configuraciones → Formularios Personalizados**, en el constructor del formulario (pestaña Tipos de tarea) (§3.8).

**¿Cómo elimino un agente o un vehículo?**
No se eliminan. Edítalos y cambia su **Estatus a INACTIVO** (§3.3, §3.4). Así conservas la trazabilidad de las tareas que ejecutaron.

**El correo del agente quedó mal escrito.**
El **correo del agente no es editable** después de creado (es su llave de acceso). Tendrás que crear el agente nuevamente con el correo correcto e inactivar el anterior (§3.3).

## Tareas

**¿Cuál es la diferencia entre Cancelar y Eliminar una tarea?**
**Cancelar** conserva la tarea con estado Cancelada y su historial (recomendado para trazabilidad). **Eliminar** la borra por completo (§4.3).

**Creé una tarea pero no puedo asignarla.**
Revisa que **no esté En Pausa (On Hold)**: una tarea con la condición de pausa activa no se puede asignar. Desactiva el toggle **Condición de tarea** para liberarla (§4.6).

**La carga masiva (XLSX) me falla.**
- Usa la **plantilla** descargable y **no renames ni reordenes** sus columnas (los encabezados van en inglés).
- Las columnas con `*` son obligatorias.
- Confirma que cada **TaskType** y **Team** del archivo **ya existan** en tu cuenta (§4.2).

**¿Por qué se creó un cliente que no registré?**
Los **clientes se crean automáticamente** al crear una tarea con una dirección y teléfono nuevos. El **teléfono es la llave única**: un teléfono nuevo genera un cliente nuevo (§3.7).

## Asignación y rutas

**Al optimizar una ruta sale "no pertenece a los equipos de las tareas".**
El **agente/vehículo debe ser del mismo equipo que las tareas**. Verifica el equipo de las tareas (o cámbialo con **Edición Masiva**) y elige un recurso de ese equipo (§6.1).

**Al optimizar sale "fuera de la ventana de atención o supera la capacidad".**
El agente no alcanza a cubrir las tareas en su jornada (su punto de partida está lejos) o se excede su capacidad. Soluciones: amplía la ventana (**Hora inicio/final**), elige un **Punto de partida** más cercano (ej. un **hub** próximo a las tareas) o reduce la cantidad de tareas (§6.2-6.3).

**No me aparece la opción de hacer la ruta recurrente.**
Solo aparece si **ninguna** de las tareas seleccionadas ya tiene su propia recurrencia. Para una ruta recurrente, parte de tareas **sin recurrencia propia** (§6.7).

**¿Por qué no veo a un agente en el panel de Recursos?**
El panel de selección para modalidades **inmediatas** muestra solo **Agentes**; los **Vehículos** solo aplican en **Planif. Avanzada de Rutas** (§5.2). Verifica también que el agente pertenezca al equipo correcto.

## Monitoreo

**El agente aparece en el mapa pero su ubicación parece vieja.**
Mira el campo **Último reporte** en su tarjeta: si la fecha/hora es antigua, su dispositivo no está reportando (app cerrada, sin señal o GPS apagado). Es un agente **inalcanzable** (§7.3).

## Notificaciones al cliente

**¿Cuál módulo de notificaciones uso?**
Usa **Notificaciones BETA** (Configuraciones → Notificaciones BETA). La pestaña "Notificaciones" clásica está en proceso de deprecación (§9).

**Configuré una notificación pero el cliente no la recibe.**
- Verifica que la notificación esté **activa** (toggle encendido).
- En **Destinatarios**, activa **Usar correos asociados a la tarea** para que llegue al correo del cliente (§9.6).
- Revisa los **Filtros** (§9.3): si acotaste por tipo de tarea/equipo/prioridad, solo dispara en esos casos.
- Haz una **prueba** (botón enviar ✈️) antes de depender de ella (§9.5).

**No veo mi reporte en la lista de Adjuntos de la notificación.**
El reporte debe existir en **Reportes Personalizados** y estar **asociado al tipo de tarea** seleccionado en Filtros. Solo aparecen esos (§9.4).

## Reportes

**Mi reporte sale vacío.**
Revisa el **rango de fechas** y los filtros. En reportes y Dashboard, por defecto el rango es el día actual; **amplía el rango Desde/Hasta** para ver datos históricos (§8.3, §10.2).

**El Dashboard muestra gráficos vacíos.**
Las tareas del día aún no se han ejecutado. **Filtra un rango de fechas pasado** (panel Filtros → Búsqueda Avanzada) para poblar los gráficos (§8.3).

**¿Cuál módulo de reportes personalizados uso?**
Los **Reportes Personalizados BETA**. Los personalizados clásicos están en deprecación (§10).

## Auditoría

**¿Quién cambió o eliminó algo?**
Usa **Reportes → Logs → Logs de Eventos**: filtra por **Tipo de Evento** (CREAR/ACTUALIZAR/ELIMINAR), **Usuario** y rango de fechas; la columna **Estado Anterior → Nuevo Estado** muestra el cambio exacto (§12.1).

**¿Cómo veo la historia de una tarea puntual?**
En el listado de Tareas, botón **Ver eventos de la tarea** (ícono de reloj): muestra cada cambio de estado con fecha y autor (§4.3, §12.1).

## Recurrencias

**Una recurrencia dejó de generar tareas.**
Probablemente pasó a **Vencida** (su fecha de finalización ya pasó). Revisa el chip **Por Vencer** periódicamente y **extiende la fecha de fin** de las que deban continuar (§11.4). Una recurrencia con fecha de fin vacía es **indefinida**.

---

## Apéndices sugeridos

> 🔜 **Próximamente:** Para cerrar el manual se recomienda agregar:
> - **Apéndice A. Glosario de términos** (tarea, tipo de tarea, ítem, agente, vehículo, hub/centro, equipo, ruta, recurrencia, On Hold, etc.).
> - **Apéndice B. Tabla de estados y colores** (consolidar §4.4: En Pausa, No Asignada, Asignada=azul, En Tránsito=amarillo, En Sitio, Completada=verde, Parcialmente, Rechazada/Cancelada=rojo).
> - **Apéndice C. Atajos y tips del dispatcher** (selección por shift+drag en el mapa, Edición Masiva para alinear equipos, filtros guardados como Vistas Personalizadas, etc.).
