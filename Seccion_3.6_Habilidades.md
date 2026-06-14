# 3.6 Habilidades (skills)

> ✅ Exploración en vivo completada el 12/06/2026.

## ¿Qué es?

Las **Habilidades** son etiquetas de competencia que conectan tres piezas de tu operación:

- En el **Tipo de Tarea** defines qué habilidades se requieren para ejecutarlo.
- En el **Agente** (y en el **Vehículo**) defines qué habilidades posee.
- El **optimizador y la asignación** usan ese cruce para que las tareas lleguen solo a quien puede ejecutarlas (ej. una entrega refrigerada solo a vehículos con habilidad "Refrigerado").

Delego maneja **dos catálogos separados** de habilidades: uno para **agentes** y otro para **vehículos**.

## Acceder a los catálogos

1. En el menú lateral, haz clic en **Configuraciones**.
2. Dentro del grupo **Agentes**, selecciona **Habilidades** (catálogo de agentes); dentro del grupo **Vehículos**, selecciona **Habilidades** (catálogo de vehículos).

Se abre el modal **Configurar habilidades**.

![Modal configurar habilidades](imagenes/web/03_06_habilidades/modal_configurar_habilidades.png)

## Gestionar habilidades

El modal muestra el listado paginado de habilidades con su **Nombre** y, por cada una, los botones **Editar** (lápiz) y **Eliminar** (papelera).

### Crear una habilidad

1. Haz clic en el botón **+** (esquina superior derecha del modal).
2. En el sub-modal **Nueva Habilidad**, escribe la **Descripción** (el nombre de la habilidad, ej. "ELECTRICISTA").
3. Haz clic en **Guardar**. La habilidad aparece en el listado en orden alfabético.
4. Cierra con **Aceptar**.

### Editar una habilidad

1. Haz clic en el **lápiz** de la fila: el nombre pasa a edición en línea.
2. Ajusta el texto y confirma con **Guardar** (botones que aparecen en la propia fila).

> 💡 **Tip:** Usa nombres cortos y consistentes (todo en mayúsculas o todo capitalizado) — estas etiquetas aparecerán en los listados de agentes, vehículos y tipos de tarea.

> 📝 **Nota:** Donde se *usa* una habilidad (Tipos de Tareas, Agentes, Vehículos), el selector es de **selección múltiple con buscador**; desde ahí no se crean habilidades nuevas, solo se asignan las existentes en estos catálogos.

## Pendientes de exploración (iteración futura)

- [ ] Comportamiento de **Eliminar** (durante la exploración devolvió "La acción no se pudo completar" — reportado a QA; re-probar tras corrección).
- [ ] Confirmar si el catálogo de habilidades de vehículos tiene el mismo flujo (aparenta ser idéntico).
- [ ] Capturas de pantalla definitivas.
