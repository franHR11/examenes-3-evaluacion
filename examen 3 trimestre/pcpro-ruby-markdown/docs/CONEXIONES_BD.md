# Gestión de Base de Datos (CONEXIONES_BD.md)

Este documento detalla la estructura de las tablas de la base de datos y consultas SQL importantes utilizadas en la aplicación.

## Esquema de la Base de Datos

Base de datos: `ruby`

### Tabla: `users`

Almacena la información de los usuarios registrados.

- **`id`** (INT, PK, AI): Identificador único del usuario.
- **`username`** (VARCHAR, UNIQUE): Nombre de usuario para el login.
- **`password`** (VARCHAR): Contraseña hasheada del usuario.
- **`created_at`** (TIMESTAMP): Fecha y hora de creación del registro.

### Tabla: `categories`

Almacena las categorías para organizar los documentos Markdown.

- **`id`** (INT, PK, AI): Identificador único de la categoría.
- **`name`** (VARCHAR(100), UNIQUE, NOT NULL): Nombre legible de la categoría.
- **`slug`** (VARCHAR(120), UNIQUE, NOT NULL): Versión del nombre para URLs.
- **`created_at`** (TIMESTAMP): Fecha y hora de creación del registro.

```sql
-- Sentencia de creación:
CREATE TABLE categories (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL UNIQUE,
    slug VARCHAR(120) NOT NULL UNIQUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```

### Tabla: `markdowns`

Almacena los documentos Markdown creados por los usuarios.

- **`id`** (INT, PK, AI): Identificador único del documento.
- **`nombre`** (VARCHAR): Título del documento.
- **`descripcion`** (TEXT): Descripción corta del documento.
- **`category_id`** (INT, NULL, FK -> categories.id): Referencia a la categoría (opcional).
- **`contenido`** (LONGTEXT): Contenido completo del documento en formato Markdown.
- **`archivo`** (VARCHAR): Nombre del archivo asociado (si aplica).
- **`fecha_creacion`** (TIMESTAMP): Fecha y hora de creación del documento.
- **`fecha_modificacion`** (TIMESTAMP): Fecha y hora de la última modificación.

```sql
-- Modificación para añadir category_id:
ALTER TABLE markdowns
ADD COLUMN category_id INT NULL AFTER descripcion,
ADD CONSTRAINT fk_markdown_category 
    FOREIGN KEY (category_id) 
    REFERENCES categories(id) 
    ON DELETE SET NULL 
    ON UPDATE CASCADE;
```

## Consultas SQL Importantes

### Búsqueda de Documentos por Título

Busca documentos cuyo título (`nombre`) contenga un texto específico.

```sql
SELECT id, nombre, descripcion, fecha_modificacion 
FROM markdowns 
WHERE nombre LIKE '%tuTextoDeBusqueda%' 
ORDER BY fecha_modificacion DESC;
```

### Obtener Documentos por Categoría

Selecciona documentos que pertenecen a una categoría específica (usando el `category_id`).

```sql
SELECT id, nombre, descripcion, fecha_modificacion 
FROM markdowns 
WHERE category_id = ? -- Reemplazar ? con el ID de la categoría
ORDER BY fecha_modificacion DESC;
```

# Documentación de Base de Datos

## Estructura General

El sistema utiliza una base de datos MySQL con las siguientes tablas principales:

1. `users` - Almacena información de usuarios del sistema
2. `markdowns` - Almacena documentos markdown y su contenido
3. `categories` - Almacena las categorías de documentos con soporte para jerarquía

## Tablas y Propósito

### Tabla: categories

Almacena las categorías para organizar documentos, con soporte para subcategorías.

#### Estructura

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | INT(11) | Identificador único autoincremental |
| name | VARCHAR(100) | Nombre de la categoría |
| slug | VARCHAR(120) | Versión URL-friendly del nombre |
| parent_id | INT(11) | Referencia a la categoría padre (NULL para categorías principales) |
| description | TEXT | Descripción de la categoría (opcional) |
| created_at | TIMESTAMP | Fecha de creación |
| updated_at | TIMESTAMP | Fecha de última actualización |

#### Restricciones

- `PRIMARY KEY (id)` - Clave primaria
- `UNIQUE KEY name (name)` - Nombre único
- `UNIQUE KEY slug (slug)` - Slug único
- `FOREIGN KEY (parent_id) REFERENCES categories (id) ON DELETE SET NULL` - Relación recursiva para jerarquía

#### Consultas Importantes

```sql
-- Obtener todas las categorías con información de categoría padre
SELECT c.*, p.name as parent_name 
FROM categories c
LEFT JOIN categories p ON c.parent_id = p.id
ORDER BY IFNULL(c.parent_id, 0), c.name ASC;

-- Obtener solo categorías principales (sin parent_id)
SELECT * FROM categories WHERE parent_id IS NULL ORDER BY name ASC;
```

### Tabla: markdowns

Almacena documentos markdown con asociación a categorías.

#### Estructura

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | INT(11) | Identificador único autoincremental |
| nombre | VARCHAR(255) | Nombre del documento |
| descripcion | TEXT | Descripción del documento |
| contenido | LONGTEXT | Contenido markdown del documento |
| archivo | VARCHAR(255) | Nombre del archivo |
| category_id | INT(11) | Referencia a la categoría (NULL si no tiene) |
| fecha_creacion | TIMESTAMP | Fecha de creación |
| fecha_modificacion | TIMESTAMP | Fecha de última modificación |

#### Consultas Importantes

```sql
-- Obtener documentos con información de categoría
SELECT m.*, c.name as category_name 
FROM markdowns m 
LEFT JOIN categories c ON m.category_id = c.id 
ORDER BY m.fecha_modificacion DESC;
```

## Relaciones entre Tablas

- **markdowns -> categories**: Un documento puede pertenecer a una categoría (`category_id` en `markdowns` hace referencia a `id` en `categories`).
- **categories -> categories**: Una categoría puede tener una categoría padre (`parent_id` en `categories` hace referencia a `id` en la misma tabla `categories`).

## Script de Actualización para Subcategorías

```sql
-- Modificación para soporte de subcategorías
-- Autor: franHR - web - www.pcprogramacion.es

-- Comprobar si la tabla categories existe
-- Si no existe, la creamos con estructura para subcategorías
CREATE TABLE IF NOT EXISTS categories (
    id INT(11) NOT NULL AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    slug VARCHAR(120) NOT NULL,
    parent_id INT(11) DEFAULT NULL,
    description TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    PRIMARY KEY (id),
    UNIQUE KEY name (name),
    UNIQUE KEY slug (slug),
    KEY parent_id (parent_id),
    CONSTRAINT fk_category_parent FOREIGN KEY (parent_id) REFERENCES categories (id) ON DELETE SET NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- Si la tabla ya existe, añadimos la columna parent_id y el índice si no existen
ALTER TABLE categories 
ADD COLUMN IF NOT EXISTS parent_id INT(11) DEFAULT NULL AFTER slug,
ADD COLUMN IF NOT EXISTS description TEXT AFTER parent_id,
ADD COLUMN IF NOT EXISTS created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP AFTER description,
ADD COLUMN IF NOT EXISTS updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP AFTER created_at,
ADD KEY IF NOT EXISTS parent_id (parent_id),
ADD CONSTRAINT IF NOT EXISTS fk_category_parent FOREIGN KEY (parent_id) REFERENCES categories (id) ON DELETE SET NULL;
``` 