# 3.11 Otros catálogos de configuración

> ✅ Exploración en vivo completada el 12/06/2026.
> Estos catálogos no aparecían en el índice original pero son parte de **Configuraciones**; se documentan aquí para que el manual cubra el menú completo.

## 3.11.1 Campos Personalizados

Permiten añadir campos propios a las entidades de Delego, que luego aparecen como la pestaña **"Campos personalizados"** dentro de los modales de creación/edición.

**Acceso:** menú lateral → **Configuraciones → Campos Personalizados**.

El listado muestra las **7 entidades** que admiten campos personalizados, cada una con su botón **Editar**:
- **Tareas**
- **Clientes**
- **Hubs**
- **Equipos**
- **Agentes**
- **Usuarios web**
- **Vehículos**

Al editar una entidad se abre el modal **Campos Personalizados** con dos zonas:
- **Componentes** (izquierda): los tipos de campo disponibles — **Texto, Número, Fecha y hora, Selección múltiple, Selección única, Lista desplegable**.
- **Lista de campos personalizados** (derecha): los campos ya creados para esa entidad, con su tipo y opciones; cada uno se puede quitar con la **✕**.

Para añadir un campo, arrastra el componente deseado a la lista, configúralo y haz clic en **Guardar**.

![Modal campos personalizados](imagenes/web/03_otros_config/modal_campos_personalizados.png)

> 💡 **Tip:** Si necesitas capturar un dato que el formulario estándar no contempla (ej. un número de contrato en el cliente, o una placa interna en el vehículo), créalo aquí una vez y estará disponible en todos los registros de esa entidad.

---

## 3.11.2 Vistas Personalizadas

Son **vistas/filtros guardados** que puedes reutilizar para no reconfigurar los filtros cada vez (ej. "ZONA NORTE", "TAREAS TEXAS", "VALIJAS").

**Acceso:** menú lateral → **Configuraciones → Vistas Personalizadas**.

| Columna | Qué muestra |
|---|---|
| **Nombre** | Nombre de la vista. |
| **Modificado** | Fecha de última modificación. |
| **Opciones** | **Editar** (lápiz) y **Eliminar** (papelera). |

Con el botón **+** creas una vista nueva. Búsqueda, ordenamiento y filtros funcionan igual que en los demás listados.

![Listado vistas personalizadas](imagenes/web/03_otros_config/listado_vistas_personalizadas.png)

---

## 3.11.3 Unidad de medidas

Catálogo de las unidades que usa la plataforma para las capacidades de agentes y vehículos.

**Acceso:** menú lateral → **Configuraciones → Unidad de medidas**. Se abre el modal **Configurar unidades de medida**.

Cada unidad tiene **Nombre** y **Símbolo** (ej. CAJAS → `caj.`, KILOGRAMO → `kg`, METRO → `m`, LITRO → `l`, GALÓN (EE.UU.) → `gal (us)`, LIBRA → `lb`, CENTÍMETRO → `cm`).

- **+** (esquina superior): crea una unidad nueva.
- Por cada unidad: **Editar** (lápiz) y **Eliminar** (papelera).
- **Aceptar** para cerrar.

> 📝 **Nota:** Estas unidades son las que luego asignas a cada capacidad (Capacidad 1-5) en **Settings → Settings Generales → Definición de unidades por capacidad** (Sección 3.9).

![Modal unidades medida](imagenes/web/03_otros_config/modal_unidades_medida.png)

---

## 3.11.4 Marcas y Modelos (de vehículos)

Catálogos que alimentan las listas desplegables **Marca** y **Modelo** del modal de Vehículos (Sección 3.4).

**Acceso:** menú lateral → **Configuraciones**, grupo **Vehículos** → **Marcas** / **Modelos**.

Funcionan como catálogos simples (crear / editar / eliminar). Mantén estos catálogos al día para que al registrar un vehículo puedas seleccionar su marca y modelo en lugar de escribirlos.

![Catalogos marcas modelos](imagenes/web/03_otros_config/catalogos_marcas_modelos.png)

---

## Pendientes de exploración (iteración futura)

- [ ] Configuración detallada de cada tipo de campo personalizado al soltarlo (validaciones, obligatoriedad).
- [ ] Flujo de creación de una Vista Personalizada (qué filtros admite).
- [ ] Confirmar gestión de Marcas/Modelos (modal idéntico a Unidad de medidas).
- [ ] Capturas de pantalla definitivas.
