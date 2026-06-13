# 3.8 Formularios de campo (Formularios Personalizados)

> ✅ Exploración en vivo completada el 12/06/2026.

## ¿Qué es?

Los **Formularios Personalizados** definen qué información captura el agente en la app móvil al ejecutar una tarea: campos de texto, fotos, firmas, códigos QR, etc. Cada formulario se asocia a uno o varios **tipos de tarea**; cuando el agente ejecuta una tarea de ese tipo, la app le muestra el formulario correspondiente.

> 📝 **Nota:** Esta es la pieza que faltaba al crear un tipo de tarea: la asociación tipo de tarea ↔ formulario **se hace aquí**, no en el módulo Tipos de Tareas.

## Acceder al módulo

1. En el menú lateral, haz clic en **Configuraciones**.
2. Selecciona **Formularios Personalizados**.

## El listado de formularios

[CAPTURA: listado_formularios.png]

| Columna | Qué muestra |
|---|---|
| **Descripción** | Nombre del formulario. |
| **Tipo de Tareas** | Chips con los tipos de tarea asociados (vacío si aún no se asocia). |
| **Opciones** | **Editar**, **Clonar Formulario**, **Copiar Formulario ID** y **Borrar**. |

> 💡 **Tip:** **Clonar Formulario** es la vía rápida para crear variantes: duplica la estructura y luego ajustas. **Copiar Formulario ID** copia el identificador del formulario, útil para integraciones.

## Crear un formulario

1. Haz clic en el botón **+**.
2. Se abre el constructor **Formulario Personalizado**:
   - **Nombre del formulario** (arriba).
   - Panel izquierdo **Componentes**: la paleta de elementos que puedes arrastrar al lienzo.
   - Panel izquierdo **Tipos de tarea**: selecciona a qué tipos de tarea se asociará el formulario.
   - Interruptor **Obligatorio**: si se activa, el agente no puede completar la tarea sin llenar el formulario.
   - Lienzo derecho **Formulario:**: arrastra aquí los componentes y ordénalos.

[CAPTURA: constructor_formulario.png]

### Componentes disponibles

| Componente | Para qué sirve |
|---|---|
| **Texto** | Respuesta de texto libre. |
| **Número** | Valor numérico. |
| **Fecha y hora** | Selector de fecha/hora. |
| **Selección múltiple** | Checkboxes (varias opciones). |
| **Selección única** | Radio buttons (una opción). |
| **Lista desplegable** | Dropdown de opciones. |
| **Imagen** | Captura de foto como evidencia. |
| **Firma** | Firma del cliente en pantalla. |
| **Separador** | Divisor visual para organizar secciones. |
| **Código QR** | Escaneo de código QR/barras. |
| **Componente de repeticiones** | Grupo de campos que el agente puede repetir N veces (ej. un registro por ítem entregado). |

3. Arrastra los componentes al lienzo, configura cada uno (etiqueta, opciones), asocia los **Tipos de tarea** y haz clic en **Guardar**.

> 💡 **Tip:** Múltiples tipos de tarea pueden usar el mismo formulario, pero cada tipo de tarea muestra un solo formulario en la app.

## Editar, clonar y borrar

- **Editar**: abre el constructor con el formulario cargado.
- **Clonar Formulario**: crea una copia para modificar sin afectar el original.
- **Borrar**: elimina el formulario (verifica antes qué tipos de tarea lo usan — columna Tipo de Tareas).

## Pendientes de exploración (iteración futura)

- [ ] Configuración detallada de cada componente al soltarlo en el lienzo (etiquetas, opciones, validaciones).
- [ ] Comportamiento del toggle **Obligatorio** a nivel formulario vs a nivel componente.
- [ ] Confirmar el flujo de asociación desde "Tipos de tarea" del constructor.
- [ ] Capturas de pantalla definitivas.
