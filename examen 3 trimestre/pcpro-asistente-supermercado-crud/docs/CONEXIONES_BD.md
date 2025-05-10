# CONEXIONES_BD.md

## Archivo de Base de Datos
- **Archivo:** `primeros_10_productos.json`
- **Propósito:** Almacenar todos los productos del inventario del supermercado.

### Estructura de cada producto
- `id` (número, único)
- `nombre` (string)
- `marca` (string)
- `precio` (número)
- `cantidadEnStock` (número)

### Consultas y operaciones principales
- Listar todos los productos
- Buscar producto por ID
- Añadir producto (verificando unicidad de ID y datos completos)
- Modificar nombre, marca o precio por ID
- Eliminar producto por ID
- Agregación de datos para gráficos (precio medio por marca, número de productos por marca)

### Observaciones
- El archivo JSON es la única fuente de datos, no hay base de datos relacional.
- Todas las operaciones de CRUD y agregación se realizan leyendo y escribiendo el archivo JSON directamente desde el backend Node.js.
