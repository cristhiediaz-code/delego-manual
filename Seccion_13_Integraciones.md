# 13. Integraciones

> ✅ Exploración en vivo completada el 13/06/2026.

Delego se conecta con otras herramientas de tu operación. Todas las integraciones se configuran en **Configuraciones (engranaje ⚙️) → Integraciones**, que tiene cuatro sub-pestañas: **API, Power BI, Webhook** y **Geotab (BETA)**. Ver también la referencia técnica en §3.9.

> ⚠️ **Advertencia:** Las credenciales de integración (API keys, tokens, contraseñas) son **secretas**. No las compartas ni las publiques: cualquiera con ellas puede operar tu cuenta.

## 13.1 Integración con Zoho (y otros sistemas) vía API / Webhook

Delego **no tiene una pestaña dedicada a Zoho**: la conexión con Zoho (CRM, Forms, Creator, etc.) —y con cualquier otro sistema externo— se construye sobre los conectores genéricos **API** y **Webhook**.

### Con la API (Integraciones → API)
Para que un sistema externo (Zoho, un ERP, etc.) **cree o consulte tareas en Delego**, usa las credenciales que aparecen en la sub-pestaña **API**:
- **x-api-key** — la clave de API.
- **Tenant-ID** — identificador de tu cuenta.
- **ClientId** — identificador del cliente/aplicación.
- **Documentación de APIs** — enlace a la documentación técnica de los endpoints.

Cada credencial tiene un botón de **copiar**. El equipo técnico de Zoho (o tu integrador) usa estos datos para autenticar las llamadas.

![Integraciones api](imagenes/web/13_integraciones/integraciones_api.png)

### Con Webhook (Integraciones → Webhook)
Para que **Delego avise a un sistema externo** cuando algo ocurre (ej. una tarea se completó), configura el **Webhook**:
- **URL** del endpoint destino (ej. un flujo de Zoho/Make/Zapier que recibe el evento).
- **Tipo de Autenticación** (ej. BASIC).
- **Usuario / Contraseña**.
- Enlace a **Documentación WebHook**.

> 💡 **Tip — patrón típico con Zoho:** Zoho **crea tareas** en Delego llamando a la API (con la x-api-key), y Delego **devuelve los resultados** (tarea completada, evidencia) a Zoho mediante el Webhook o las notificaciones por Webhook (§9.1). Así el flujo es bidireccional.

## 13.2 Conexión con Power BI

En **Integraciones → Power BI** configuras la incrustación de tableros de Power BI y el acceso a datos para análisis externo. Hay dos juegos de credenciales:

| Vista | Campos |
|---|---|
| **Administrador / Despachador** | URL, Identificador, Token. |
| **Cliente** | URL, Identificador, Token (vista limitada para perfiles tipo Cliente). |

Además:
- Interruptor **Permitir al perfil tipo Cliente visualizar tablero de PBI**.
- Bloque **API** con un endpoint `get_report_file` para **descargar reportes por rango de fechas** (incluye el header **Accept** y un enlace a la **Documentación de Power BI**).

![Integraciones powerbi](imagenes/web/13_integraciones/integraciones_powerbi.png)

> 💡 **Tip:** Usa la **Vista Cliente** + el toggle de visualización para dar a un cliente corporativo su propio tablero de Power BI dentro de Delego, sin exponer los datos del resto de tu operación.

## 13.3 Links de tracking externos

El **enlace de seguimiento (tracking)** permite que el cliente final siga su tarea en tiempo real desde un navegador, sin necesidad de acceso a Delego.

- Se inserta en los correos de notificación al cliente desde los **Campos Dinámicos** del editor de notificaciones (§9.6).
- Lleva a una página pública de seguimiento con el **estado y la ubicación** de la tarea y la **hora estimada de llegada (ETA)**.

> 💡 **Tip:** Combínalo con la notificación de estado **EN TRÁNSITO**: el cliente recibe "tu pedido va en camino" con el botón para rastrearlo en vivo, igual que en las apps de delivery.

## 13.4 Coordenadas de ejecución para reportes

Para integraciones de análisis y verificación, Delego registra **dónde se ejecutó realmente** cada tarea (no solo dónde estaba planificada):

- En el reporte (§10.2) puedes incluir la columna **Coordenadas de Ejecución** (latitud/longitud del punto donde el agente marcó la tarea), junto con **Fecha/Hora de Ejecución**.
- Estas coordenadas alimentan auditorías, validación de cumplimiento y sistemas externos que necesiten confirmar la ubicación real de la ejecución.

> 💡 **Tip:** Exporta el reporte con **Coordenadas de Ejecución** + **ID Orden** (§3.9) para cruzar la ejecución real con el sistema origen (ej. Zoho) y validar que cada tarea se atendió en el lugar correcto.

## Geotab (BETA)

Integración con la telemática de flota **Geotab**. En **Integraciones → Geotab** se configuran **Base de Datos, Usuario y Contraseña**, con enlace a su documentación. Permite enriquecer la operación con datos de los vehículos.

## Pendientes de exploración (iteración futura)

- [ ] Pasos concretos del lado de Zoho (fuera de Delego) — depende del producto Zoho usado.
- [ ] Contenido exacto de la página de tracking externa.
- [ ] Capturas de pantalla definitivas.
