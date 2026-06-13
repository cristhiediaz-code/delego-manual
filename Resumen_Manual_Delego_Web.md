# 📘 Manual Delego Web — Resumen del Proyecto

> Documento de referencia del avance del Manual Delego Web. Recopila todas las decisiones, secciones redactadas, capturas necesarias, recursos visuales generados y pendientes.

---

## 1. Contexto general del proyecto

**Objetivo:** Crear los manuales de usuario oficiales de Delego (SaaS de logística de última milla / operaciones de campo).

**Manuales a crear:**
1. **Manual Delego Web** — para administradores y dispatchers *(este es el que estamos trabajando)*
2. **Manual Delego App** — para agentes de campo *(pendiente, después del Web)*

**Idioma:** español neutro
**Tono:** claro, profesional, cercano y práctico. Tratar al lector de "tú".
**Audiencia:** usuarios operativos, no técnicos.

**Plataforma de publicación:** GitBook
**Fuente de verdad:** Markdown

---

## 2. Convenciones acordadas

### Estructura de cada módulo
Cada sección/módulo sigue esta estructura:
1. ¿Qué es? — Descripción breve del módulo
2. ¿Cuándo se usa? — Casos de uso reales
3. Paso a paso — Instrucciones numeradas
4. Capturas de pantalla — Marcadas con `[CAPTURA: descripción]` o ya con ruta
5. Tips y buenas prácticas
6. Advertencias (si aplica)

### Bloques destacados
- `> 💡 **Tip:**` — recomendaciones útiles
- `> 📝 **Nota:**` — información complementaria
- `> ⚠️ **Advertencia:**` — algo que requiere precaución
- `> 🔜 **Próximamente:**` — funcionalidad en desarrollo

### Terminología fija
- "tarea" (no pedido, envío, orden)
- "agente" (no repartidor, técnico, conductor)
- "dispatcher" (anglicismo aceptado)
- "ruta" (no recorrido, viaje)
- "cliente" (destinatario final)
- "hub" (en inglés) / "centro" (en español) — ambos se mencionan
- "centros/hubs" como expresión cuando se hace referencia general

### Convención de imágenes
- **Ruta:** `/imagenes/web/<seccion>/<archivo>.png`
- **Nomenclatura:** guiones bajos y minúsculas (con excepción de nombres ya guardados)
- Ejemplo: `/imagenes/web/01_bienvenida/Dashboard_mas_menu.png`

---

## 3. Índice definitivo del Manual Delego Web

```
1. Bienvenido a Delego                          ✅ REDACTADA
2. Primeros pasos                                ✅ REDACTADA
   2.1 Acceder a la plataforma por primera vez
   2.2 Recorrido rápido por la interfaz
   2.3 Configuración mínima antes de operar
   2.4 Crea tu primera tarea
   2.5 Asigna tu primera tarea
3. Configuración de tu cuenta                    ✅ REDACTADA (exploración en vivo)
   3.1 Tipos de tarea                            ✅
   3.2 Equipos                                   ✅
   3.3 Agentes                                   ✅
   3.4 Vehículos                                 ✅
   3.5 Hubs                                      ✅
   3.6 Habilidades (skills) y capacidades        ✅
   3.7 Clientes                                  ✅
   3.8 Formularios de campo                      ✅
   3.9 Ajustes del sistema                       ✅
   3.10 Usuarios web y permisos                  ✅
   3.11 Otros catálogos (Campos/Vistas Pers.,    ✅ (nuevo, no estaba en índice)
        Unidad de medidas, Marcas, Modelos)
4. Gestión de tareas                             ✅ REDACTADA (exploración en vivo)
   4.1 Crear manual / 4.2 Carga Masiva (XLSX)
   4.3 Editar/duplicar/cancelar / 4.4 Estados+colores
   4.5 Relacionadas/parciales / 4.6 On Hold / 4.7 Ítems
   4.1 Crear una tarea manualmente
   4.2 Crear tareas en lote (Bulk Load)
   4.3 Editar, duplicar y cancelar tareas
   4.4 Estados de una tarea y sus transiciones
   4.5 Tareas relacionadas, devoluciones y completados parciales
   4.6 Estado "On Hold" y manejo de excepciones
   4.7 Ítems y cantidades dentro de una tarea
5. Asignación de tareas                          ✅ REDACTADA (exploración en vivo)
   5.1 Modos de ejecución (Immediate, Same Day, Next Day, Appointed)
   5.2 Asignación directa
   5.3 Publicación a varios agentes (Immediate)
   5.4 Reasignación y cambios de equipo
   [11 acciones del menú contextual + panel Recursos Agentes/Vehículos]
6. Planificación y optimización de rutas         ✅ REDACTADA (con ejecución real del optimizador)
   6.1 Planificador de rutas                     ✅
   6.2 Reglas y palancas del optimizador         ✅ (todas las palancas + 3 modos de optimización)
   6.3 Puntos de inicio y fin de ruta            ✅ (opciones completas + hub como partida)
   6.4 Ajuste manual de la ruta propuesta        ✅ (Resultados Planificación de Rutas)
   6.5 Indicadores de ruta                       ✅ (Resumen de Rutas: dist/duración/uso/desglose)
   6.6 Costos y confirmación (Asignar a Ruta)    ✅
   6.7 Rutas recurrentes (nuevo)                 ✅ (regla: solo con tareas sin recurrencia propia)
   [Reglas clave: agente del mismo equipo; ventana/capacidad; partir de hub cercano]
   [Técnica usada: Edición Masiva para alinear equipo tareas↔agente, luego optimizar]
7. Maestro de Rutas  🔜 Próximamente             ⏳ PENDIENTE
   7.1 ¿Qué es el Maestro de Rutas?
   7.2 Plantillas de rutas
   7.3 Rutas Por Planificar / Incompletas
   7.4 Rutas Planificadas
   7.5 Rutas en Proceso (vista en vivo)
   7.6 Rutas Ejecutadas
8. Monitoreo en tiempo real                      ✅ REDACTADA (exploración en vivo)
   8.1 Mapa operativo (CAPAS: Equipos, Tareas Ejecutadas)
   8.2 Estado de agentes (tarjeta: último reporte, estatus, coords)
   8.3 Alertas y agentes inalcanzables (vía Último reporte)
   8.4 Acciones rápidas (Ver Estatus/Calendario del Agente + menú contextual)
9. Dashboard                                     ✅ REDACTADA (exploración en vivo)
   9.1 ¿Qué muestra? / 9.2 6 KPIs + 7 gráficos documentados
   9.3 Filtros (Equipo/Agentes/Tipos/Desde-Hasta) con rango histórico
   9.4 Lectura e interpretación
   [Tip clave: filtrar rango pasado amplio para poblar gráficos]
10. Notificaciones al cliente                    ✅ REDACTADA (solo Notificaciones BETA; la clásica se deprecará)
    10.1 ¿Qué se puede notificar? (8 estados x Email/Webhook/WhatsApp)
    10.2 Crear/configurar (editor 4 pestañas + Campos Dinámicos)
    10.3 Condiciones (Filtros: tipo/equipo/agente/prioridad/modo/cliente)
    10.4 Adjuntar reportes (hasta 5, desde Reportes Personalizados)
    10.5 Probar antes de activar (botón enviar + toggle activo)
    10.6 Destinatarios + links de tracking/ETA (campo dinámico)
11. Reportes                                     ⏳ PENDIENTE
    11.1 Reportes disponibles
    11.2 Generar bajo demanda
    11.3 Programar reportes recurrentes
    11.4 Ventana de descargas y reportes asíncronos
    11.5 Personalizar plantillas
12. Recurrencias y tareas planificadas a futuro  ⏳ PENDIENTE
    12.1 Crear una recurrencia
    12.2 Vista de tareas planificadas
    12.3 Edición y eliminación masiva
    12.4 Recurrencias activas, por vencer y vencidas
13. Auditoría y trazabilidad                     ⏳ PENDIENTE
    13.1 Registro de eventos (event log)
    13.2 Reporte de tareas planificadas no ejecutadas
    13.3 Buenas prácticas de trazabilidad
14. Integraciones                                ⏳ PENDIENTE
    14.1 Integración con Zoho
    14.2 Conexión con Power BI
    14.3 Links de tracking externos
    14.4 Coordenadas de ejecución para reportes
15. Solución de problemas y preguntas frecuentes ⏳ PENDIENTE

Apéndice A. Glosario de términos
Apéndice B. Tabla de estados y colores
Apéndice C. Atajos y tips del dispatcher
```

---

## 4. Estado de avance por sección

### ✅ SECCIÓN 1: Bienvenido a Delego — COMPLETA

**Sub-secciones redactadas:**
- 1.1 ¿Qué es Delego?
- 1.2 ¿A quién está dirigido este manual?
- 1.3 Conceptos clave que vas a encontrar
- 1.4 Cómo está organizado el manual

**Decisiones clave de esta sección:**
- Delego se describe con 4 funcionalidades clave (no "capacidades" para evitar confusión con el concepto técnico):
  1. Asignación de recursos
  2. Optimización de rutas
  3. Ejecución digital en campo
  4. Trazabilidad
- Tabla de conceptos clave incluida en 1.3 como referencia rápida.

**Capturas asociadas:**
- ✅ `Dashboard_mas_menu.png` (vista general dashboard)
- ✅ `conceptos_clave_delego.svg` (diagrama de relaciones) — versión v4 final

**Diagrama de conceptos clave (v4 — versión final):**

Refleja estas relaciones:
- Tarea tiene 1 Tipo de tarea (obligatorio)
- Tarea pertenece a 1 Equipo (puede crearse sin equipo, queda con punto rojo)
- Tarea puede tener 1 Formulario (opcional)
- Tarea se asigna a 1 Agente
- Tarea se ejecuta para 1 Cliente
- Cliente recibe notificaciones en tiempo real
- Agente pertenece a 1 o varios Equipos (N:N)
- Agente puede tener 1 Vehículo (opcional)
- Equipo tiene 1 Hub (un Hub puede estar en varios equipos)
- Cluster de modalidades:
  - Inmediatas: Asignación directa, Asignación automática, Publicación
  - Planificadas: Ruta, Agenda

---

### ✅ SECCIÓN 2: Primeros pasos — COMPLETA

#### 2.1 Acceder a la plataforma por primera vez

**Flujo documentado de 5 sub-pasos:**
1. Crear cuenta (auto-registro en `https://prod.delego.ai/#/register`)
2. Verificar correo electrónico (link en email)
3. Recibir correo de bienvenida ("Cuenta Delego Creada")
4. Recibir credenciales temporales (en menos de 5 min)
5. Iniciar sesión en `https://prod.delego.ai/#/login` y cambiar contraseña

**Decisiones clave:**
- Idiomas disponibles: español (default), inglés, portugués
- El primer usuario que registra una organización queda automáticamente como administrador
- La contraseña temporal es de un solo uso

**Capturas asociadas (todas obtenidas):**
- ✅ `registro_delego.png`
- ✅ `correo_verificacion.png`
- ✅ `correo_bienvenida.png`
- ✅ `correo_credenciales.png`
- ✅ `pantalla_login.png`

#### 2.2 Recorrido rápido por la interfaz

**Menú lateral documentado (orden confirmado):**
1. Tablero de Indicadores
2. Operaciones (pantalla principal del dispatcher con mapa)
3. Tareas
4. Agenda
5. Clientes
6. PowerBI
7. Recursos operativos (submenú)
8. Reportes
9. Configuraciones (submenú: Tipos de Tareas, Vehículos, Agentes, Unidad de medidas, Vistas Personalizadas, Campos Personalizados, Formularios Personalizados)
10. Cerrar Sesión

**Capturas asociadas:**
- ✅ `vista_general_operaciones.png` (también `Dashboard_mas_menu.png`)

#### 2.3 Configuración mínima antes de operar (administrador)

**Orden de creación obligatorio:**
1. Tipo de tarea
2. Hub (centro) — *obligatorio para crear equipos*
3. Equipo
4. Agente

**Diagramas de bienvenida documentados:** la primera vez en cada módulo aparece un diagrama explicativo que desaparece al crear el primer registro.

**Reglas y campos clave por entidad:**

**Tipo de tarea:**
- Campos: Descripción* (rol de nombre), Estatus*, Habilidades, Ítems
- El formulario NO se asocia desde aquí (se hace en Formularios Personalizados)

**Hub:**
- Campos: Hub, Dirección, Latitud, Longitud
- Lat/Long se autocompletan con la dirección
- Todos opcionales (en términos de validación), pero obligatorio que exista al menos uno para crear equipos

**Equipo:**
- Campos: Nombre*, Centros*, Autoasignación (checkbox), Zona Geográfica (checkbox)
- Para usar asignación automática hay que activar Autoasignación

**Agente — 3 pestañas:**
- **Datos del Agente:** Nombre*, Apellido*, Estatus*, Equipos*, Tipo Agente (categoría personalizable), Correo Electrónico* (único, no editable después)
- **Opciones avanzadas:** Modo de Movilidad*, Capacidad 1-5, Habilidades, Dirección de pernocta*, Latitud*, Longitud* (lat/long autocompletan)
- **Vehículo asociado:** completamente opcional. Requiere que el vehículo exista en Configuraciones → Vehículos

**Capturas asociadas (todas obtenidas):**
- ✅ `bienvenida_tipos_tareas.png`, `modal_tipo_tarea.png`
- ✅ `bienvenida_hubs.png`, `modal_hub.png`
- ✅ `bienvenida_equipos.png`, `modal_equipo.png`
- ✅ `bienvenida_agentes.png`, `modal_agente_datos.png`, `modal_agente_optimizacion.png`, `modal_agente_vehiculo.png`

#### 2.4 Crea tu primera tarea (dispatcher)

**Modal "Detalle de Tareas" con 6 pestañas:**

**Pestaña 1: Tarea**
- Obligatorios: Nombre, Prioridad (Normal/Alta), Modo de Tarea (Inmediata/Mismo día/Día siguiente/Programada), Fecha, Después, Antes, Tipo de Tarea, Valor 1
- Opcionales: Identificador (puede autogenerarse), Instrucciones, Equipo, Condición de tarea (toggle = pausa/On Hold), Tiempo de Servicio, Valores 2-5, Detalle de Items
- **Tip especial documentado:** Geocodificación automática + asignación por Zona Geográfica
- **On Hold documentado:** activar el toggle pausa la tarea con motivo; en pausa no se puede asignar

**Pestaña 2: Sitio Recolección** (opcional)
- Para flujos de recolección+entrega
- Reusa ubicaciones del sistema (clientes guardados)
- Si seleccionas un Hub, autocompleta dirección y coordenadas

**Pestaña 3: Cliente** (obligatoria)
- Obligatorios: Nombre, Dirección, Latitud, Longitud (lat/long autocompletan)
- "País del cliente" (físico, ayuda al geocodificador) vs "Código de país del teléfono" (puede ser distinto)
- Teléfono es llave para crear cliente + se usa para notificaciones WhatsApp

**Pestaña 4: Campos personalizados**
- Aparece vacía si no hay campos configurados
- Siempre opcionales
- Los configura el admin en Configuraciones → Campos Personalizados

**Pestaña 5: Asignación**
- Equipo se sincroniza con pestaña Tarea
- 5 modalidades: Sin Asignación, Asignación Directa, Publicar, Publicación Inteligente, Agendar
- Asignación Directa muestra selector de agente debajo

**Pestaña 6: Recurrencia**
- Toggle ¿Ruta recurrente?
- Modos: Diaria, Semanal, Mensual, Anual, Personalizada
- Termina vacío = indefinida
- Genera tareas automáticas en cada fecha

**4 botones inferiores:**
- Guardar
- Guardar & Crear Nueva Tarea (abre modal vacío)
- Guardar & Crear Retorno (crea tarea inversa intercambiando pickup ↔ cliente)
- Cancelar

**Botón Carga Masiva:** lleva al flujo de Bulk Load (CSV), detallado en sección 4.2

**Capturas asociadas:**
- ✅ `modal_tarea_pestaña_1.png` a `modal_tarea_pestaña_6.png`
- ⚠️ FALTA: `listado_tareas_crear.png` (vista del listado con botón Crear tarea)

#### 2.5 Asigna tu primera tarea

**Clasificación de modalidades:**
- **Inmediatas (3):** Asignación Directa, Publicar, Publicación Inteligente
- **Planificadas (3):** Agendar, Planif. Rutas, Planif. Avanzada de Rutas

**Selección de tareas (2 formas):**
- Listado lateral (checkboxes)
- Mapa con shift+drag (selección por área)

**Happy path documentado — Asignación Directa (5 pasos):**
1. Clic derecho en tarea(s) seleccionada(s) → "Asignación Directa"
2. Panel "Recursos" del lado derecho con lista de agentes (nombre, capacidad, habilidades, equipos) → marcar agente → Siguiente
3. Modal "Seleccionar para asignar" con lista de tareas + preview de ruta en mapa → Asignar
4. Modal de confirmación "Asignar Tareas" → Asignar
5. Mensaje de éxito + toast + tarea en listado cambia color (blanco → azul) y muestra "Asignado a: [Nombre]"

**Nota documentada:** El panel Recursos tiene Agentes y Vehículos, pero para modalidades inmediatas solo se asigna a Agentes. Vehículos solo en Planif. Avanzada de Rutas.

**Resumen de las 5 modalidades restantes (con descripciones validadas):**
- **Publicar:** publica a varios agentes que tú eliges; primero que acepta se queda con ella
- **Publicación Inteligente:** estilo Uber, por zonas en tiempo de manejo, va ampliando radio
- **Agendar:** abre calendario para programar a fecha/hora futura
- **Planif. Rutas:** optimizador básico, premisa: ruta más corta
- **Planif. Avanzada de Rutas:** optimizador avanzado, considera capacidades, tiempos de servicio, ventanas de atención y más. Única modalidad que también permite asignar a vehículos.

**Otras acciones del menú contextual (documentadas en nota):**
- Desasignar Tarea
- Cancelar Tarea
- Eliminar Tareas
- Invalidar Localización de Tarea
- Edición Masiva

**Capturas asociadas:**
- ⚠️ FALTA: `seleccion_lista_lateral.png`
- ⚠️ FALTA: `seleccion_mapa_shift.png`
- ✅ `menu_contextual_asignacion.png`
- ✅ `panel_recursos_agentes.png`
- ✅ `modal_seleccionar_asignar.png`
- ✅ `modal_confirmacion_asignar.png`
- ✅ `modal_exito_asignacion.png`
- ✅ `tarea_asignada_listado.png`

---

## 5. Recursos visuales generados

### Diagramas de conceptos clave
- `conceptos_clave_delego.svg` (v1) — versión inicial
- `conceptos_clave_delego_v2.svg` — agregadas cardinalidades
- `conceptos_clave_delego_v3.svg` — modalidades como cluster jerárquico
- ✅ `conceptos_clave_delego_v4.svg` — **VERSIÓN FINAL** (sin cruces de líneas, tipo de tarea reubicado)

### Ilustraciones para tarjetas del home (GitBook)
- ✅ `01_configuracion_inicial.svg` — engranaje con check (Configuración inicial de Delego)
- ✅ `02_primera_tarea.svg` — clipboard con checklist + reloj + pin (Crea tu primera tarea)
- ✅ `03_formularios_personalizados.svg` — móvil con formulario + llaves de código (Formularios Personalizados)

### Colores oficiales utilizados (Manual de Marca de Delego)
- Principal oscuro: `#3B54C2`
- Principal claro: `#5B7CE2`
- Acento suave: `#D1BEF9`
- Fondo gradient: `#F4F1FE` → `#E8E4FB`
- Gris claro: `#C4C4C4`

### Tipografías oficiales
- Títulos: Prompt
- Texto: Raleway

---

## 6. Capturas pendientes para iteraciones futuras

### Sección 2 — pendientes menores
- `listado_tareas_crear.png` (vista del listado de Tareas con botón "+ Crear tarea" visible)
- `seleccion_lista_lateral.png` (listado lateral con varias tareas seleccionadas)
- `seleccion_mapa_shift.png` (selección por área en el mapa con shift+drag)
- Pantalla de cambio de contraseña tras login con temporal (opcional)

---

## 7. Decisiones de diseño del proyecto

### Estructura del manual
- Sección 1 y 2 = onboarding (primer día)
- Sección 3 = referencia detallada de configuración
- Secciones 4-15 = uso día a día + temas avanzados

### Diferencia entre Sección 2.3 (onboarding) y Sección 3 (referencia)
| Sección 2.3 | Sección 3 |
|---|---|
| Crear el primer X | Todo sobre X |
| Pasos mínimos | Todos los campos, edge cases |
| Para arrancar rápido | Para configuración avanzada |

### Sobre el Maestro de Rutas (Sección 7)
- Aún no está listo en producto
- Se documentará con nota "🔜 Próximamente" y estructura básica

### Sobre los Casos de uso por industria
- Inicialmente considerados como Sección 14
- Descartados del manual a pedido del usuario
- Pueden reutilizarse para playbooks de ventas o documentación interna

---

## 8. Plataformas evaluadas para publicación

| Plataforma | Plan gratis | Pros | Contras |
|---|---|---|---|
| **GitBook** | Sí (1 usuario) | WYSIWYG, importa Markdown | Sin dominio personalizado, presión a upgrade |
| **Mintlify** | Sí (1 editor) | Dominio personalizado incluido | Curva MDX, salto a $250-300/mes |
| **Notion** | Sí (decente) | Edición más amigable | Look menos profesional out-of-the-box |

**Decisión:** El proyecto está actualmente en **GitBook** (plan gratuito).

---

## 9. Siguiente paso

🔄 **EN PROGRESO: Sección 3.1 — Tipos de tarea (referencia completa)**

**Lo que ya tenemos** (de Sección 2.3.1):
- Ruta de acceso
- Pantalla de bienvenida
- Modal de creación con campos básicos
- Regla de asociación con formularios

**Lo que falta para profundizar:**
- Vista del listado con datos
- Modal de edición (si es distinto al de creación)
- Inactivar / eliminar
- Gestión de ítems en lote
- Carga masiva de tipos de tarea
- Reglas de negocio (límites, duplicados, etc.)

---

*Documento generado como referencia del proyecto. Última actualización: Mayo 2026.*
