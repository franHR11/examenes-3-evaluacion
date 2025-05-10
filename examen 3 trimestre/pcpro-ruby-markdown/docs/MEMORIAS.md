# Registro de Cambios y Decisiones Clave

## Implementación de Subcategorías
**Fecha:** <?php echo date('Y-m-d'); ?>

### Cambios Realizados

1. **Base de Datos**:
   - Se implementó la estructura para soportar subcategorías mediante el campo `parent_id` en la tabla `categories`.
   - Se añadió una restricción de clave foránea para mantener la integridad referencial cuando se elimina una categoría padre.
   - Se agregó el campo `description` para almacenar información descriptiva sobre cada categoría.

2. **Modelo de Categorías**:
   - Se actualizó el método `getAll()` para mostrar la jerarquía de categorías, incluyendo un LEFT JOIN para obtener el nombre de la categoría padre.
   - Se añadió un nuevo método `getAllParentCategories()` para obtener solo las categorías principales (sin parent_id).
   - Se modificaron los métodos `create()` y `update()` para incluir `parent_id` y `description`.
   - Se incluyó lógica para evitar ciclos en la jerarquía de categorías.
   - Se mejoró el método `delete()` para actualizar las subcategorías cuando se elimina una categoría padre.

3. **Controlador de Categorías**:
   - Se actualizaron los métodos `create()` y `edit()` para obtener y mostrar las posibles categorías padre.
   - Se modificaron los métodos `store()` y `update()` para procesar los nuevos campos.
   - Se añadieron validaciones para evitar referencias circulares en la jerarquía de categorías.

4. **Vistas**:
   - Se actualizó el formulario `form.php` para incluir campos de descripción y selección de categoría padre.
   - Se mejoró la vista `list.php` para mostrar la jerarquía de categorías con identación visual y los nuevos campos.
   - Se añadieron estilos CSS para una mejor visualización de la jerarquía.

### Decisiones de Diseño

1. **Jerarquía de Un Solo Nivel**: Se decidió implementar una jerarquía simple (solo un nivel de subcategorías) para facilitar la usabilidad y evitar complejidades en la navegación.

2. **Actualización de Subcategorías**: Cuando se elimina una categoría padre, sus subcategorías se convierten automáticamente en categorías principales en lugar de eliminarse, preservando así el contenido.

3. **Validación de Ciclos**: Se implementó una validación tanto en el controlador como en el modelo para evitar la creación de ciclos en la jerarquía (por ejemplo, que una categoría sea padre de sí misma o de sus ancestros).

4. **Compatibilidad con el Sistema Existente**: Los cambios se implementaron de manera que son retro-compatibles con el resto del sistema, específicamente con el modelo de Markdown, que ya estaba preparado para trabajar con categorías.

### Beneficios

1. **Mejor Organización**: Los usuarios ahora pueden organizar sus documentos en una estructura jerárquica, facilitando la navegación y el acceso a la información.

2. **Mayor Flexibilidad**: La adición de descripciones permite a los usuarios añadir contexto a sus categorías.

3. **Usabilidad Mejorada**: La interfaz de usuario muestra claramente la jerarquía, facilitando la comprensión de la estructura organizativa. 