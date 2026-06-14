# 3.7 Clientes

> ✅ Exploración en vivo completada el 12/06/2026.

## ¿Qué es?

Los **Clientes** representan el **punto de visita** donde se realizará una tarea: la combinación de una dirección georreferenciada y un teléfono de contacto. Son el destino (o recogida) de tus tareas y acumulan el historial de todo lo ejecutado en ese punto.

Cuatro conceptos clave:

- **Destino de la tarea:** el cliente indica dónde debe ejecutarse la actividad en campo.
- **Teléfono único:** el teléfono identifica unívocamente al cliente; un teléfono nuevo en una dirección registrada genera un cliente distinto.
- **Reutilizable:** los clientes ya registrados se vinculan automáticamente a nuevas tareas.
- **Historial operativo:** cada cliente acumula el historial de visitas y tareas ejecutadas en su punto.

> 💡 **Tip:** **No necesitas crearlos manualmente.** Los clientes se registran automáticamente cada vez que creas una tarea con una dirección y teléfono nuevos. Usa este módulo para consultarlos, corregir datos o preparar clientes antes de una operación.

## Acceder al módulo

En el menú lateral, haz clic en **Clientes**.

> 💡 **Tip:** El botón **?** muestra el diagrama "Crea tu primer cliente".

## El listado de clientes

![Listado clientes](imagenes/web/03_07_clientes/listado_clientes.png)

| Columna | Qué muestra |
|---|---|
| ☑️ (checkbox) | Selección múltiple para eliminación masiva. |
| **Nombre** | Nombre del cliente. |
| **Teléfono** | Su número con código de país. |
| **Dirección** | La dirección del punto de visita. |
| **Opciones** | **Editar** (lápiz) y **Eliminar** (papelera). |

> 📝 **Nota:** Si tu cuenta tiene muchos clientes, el listado se carga **por lotes**: verás un indicador de progreso en la esquina inferior derecha (ej. "4,000 clientes de 10,409 cargados — batch 2"). Puedes empezar a trabajar mientras termina la carga.

Las herramientas habituales aplican: búsqueda en vivo, ordenamiento, filtros por columna, papelera masiva en la cabecera y exportación.

## Crear un cliente manualmente

1. Haz clic en el botón **+**.
2. Se abre el modal **Detalles del Cliente** con dos pestañas: **Datos del cliente** y **Campos personalizados**.

| Campo | Obligatorio | Descripción |
|---|---|---|
| **Nombre** | ✅ | Nombre del cliente (ej. "Carlos Pérez"). |
| **País / Ciudad** | Opcional | El país físico del cliente; ayuda al geocodificador a ubicar bien la dirección. |
| **Dirección** | ✅ | La dirección del punto de visita; alimenta la geocodificación. |
| **Correo Electrónico** | Opcional | Para notificaciones por correo. |
| **País (código) + Teléfono** | ✅ | El código telefónico puede ser distinto al país físico. El teléfono es la **llave única** del cliente y se usa para notificaciones por WhatsApp. |
| **Coordenadas Geográficas (Latitud / Longitud)** | ✅ | Se calculan con la dirección; ajustables con el pin del mapa. |

¿Más de un número? Usa el enlace **Agregar teléfono adicional** debajo del teléfono principal.

![Modal detalles cliente](imagenes/web/03_07_clientes/modal_detalles_cliente.png)

> 💡 **Tip (precisión del pin):** Como indica el propio formulario: haz clic en el punto del mapa y **arrástralo** para mayor precisión; luego haz clic **fuera del punto** para aceptar las coordenadas.

3. Haz clic en **Guardar**.

## Editar y eliminar clientes

- **Editar** (lápiz): abre el mismo modal con los datos del cliente; aquí puedes corregir una dirección mal geocodificada arrastrando el pin.
- **Eliminar** (papelera): individual con confirmación, o masivo seleccionando checkboxes y usando la papelera de la cabecera.

> ⚠️ **Advertencia:** Eliminar un cliente no es recuperable y pierdes la referencia de su historial de visitas. Si solo quieres depurar duplicados, verifica primero cuál registro acumula el historial.

## Pendientes de exploración (iteración futura)

- [ ] Vista de detalle/historial del cliente (¿se accede con clic en la fila?).
- [ ] Comportamiento del teléfono duplicado (¿valida que no exista otro cliente con el mismo teléfono?).
- [ ] Capturas de pantalla definitivas.
