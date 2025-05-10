# CONEXIONES A BASE DE DATOS

## Configuración de Conexión

La conexión a la base de datos se establece en el archivo `admin/config/database.php` con los siguientes parámetros:

```php
define('DB_HOST', 'localhost');
define('DB_USER', 'tornado');
define('DB_PASS', 'tornado');
define('DB_NAME', 'tornado');
```

## Estructura de la Base de Datos

### Tabla: users
Esta tabla almacena la información de los usuarios que pueden acceder al sistema.

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    email VARCHAR(100) UNIQUE,
    name VARCHAR(100),
    status ENUM('active', 'pending', 'blocked') DEFAULT 'pending',
    role ENUM('admin', 'user') DEFAULT 'user'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```

#### Campos:
- **id**: Identificador único del usuario
- **username**: Nombre de usuario (único)
- **password**: Contraseña almacenada con hash
- **email**: Correo electrónico del usuario (único)
- **name**: Nombre completo del usuario
- **status**: Estado del usuario
  - `active`: Usuario activo que puede iniciar sesión
  - `pending`: Usuario pendiente de activación
  - `blocked`: Usuario bloqueado sin acceso al sistema
- **role**: Rol del usuario
  - `admin`: Acceso completo a todas las funciones
  - `user`: Acceso limitado según permisos

### Tabla: categories

Almacena las categorías para clasificar los sitios web.

| Campo       | Tipo             | Descripción                            |
|-------------|------------------|----------------------------------------|
| id          | INT (PK, AUTO)   | Identificador único de la categoría    |
| name        | VARCHAR(100)     | Nombre de la categoría                 |
| description | TEXT             | Descripción de la categoría            |
| icon        | VARCHAR(50)      | Icono de Font Awesome para la categoría|
| created_at  | TIMESTAMP        | Fecha de creación del registro         |

```sql
CREATE TABLE categories (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL UNIQUE,
    description TEXT,
    icon VARCHAR(50),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Tabla: websites

Almacena la información de los sitios web gestionados por la aplicación.

| Campo           | Tipo             | Descripción                            |
|-----------------|------------------|----------------------------------------|
| id              | INT (PK, AUTO)   | Identificador único del sitio          |
| category_id     | INT (FK)         | ID de la categoría a la que pertenece  |
| name            | VARCHAR(100)     | Nombre del sitio web                   |
| description     | TEXT             | Descripción del sitio                  |
| url             | VARCHAR(255)     | URL principal del sitio                |
| logo            | VARCHAR(255)     | Ruta al archivo de logo                |
| admin_url       | VARCHAR(255)     | URL del panel de administración        |
| plesk_url       | VARCHAR(255)     | URL del panel Plesk                    |
| phpmyadmin_url  | VARCHAR(255)     | URL de phpMyAdmin                      |
| created_at      | TIMESTAMP        | Fecha de creación del registro         |

```sql
CREATE TABLE websites (
    id INT AUTO_INCREMENT PRIMARY KEY,
    category_id INT,
    name VARCHAR(100) NOT NULL,
    description TEXT,
    url VARCHAR(255) NOT NULL,
    logo VARCHAR(255),
    admin_url VARCHAR(255),
    plesk_url VARCHAR(255),
    phpmyadmin_url VARCHAR(255),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (category_id) REFERENCES categories(id) ON DELETE SET NULL
);
```

## Consultas SQL Importantes

### Consultas para la Gestión de Usuarios

#### Obtener todos los usuarios
```sql
SELECT id, username, email, name, status, role FROM users ORDER BY id DESC;
```

#### Validar credenciales de un usuario
```sql
SELECT id, username, password, email, name, status, role FROM users WHERE username = ?;
```

#### Actualizar el estado de un usuario
```sql
UPDATE users SET status = ? WHERE id = ?;
```

#### Actualizar el rol de un usuario
```sql
UPDATE users SET role = ? WHERE id = ?;
```

#### Registrar un nuevo usuario
```sql
INSERT INTO users (username, password, email, name, status, role) 
VALUES (?, ?, ?, ?, ?, ?);
```

### Gestión de Categorías

```sql
-- Listar todas las categorías
SELECT * FROM categories ORDER BY name

-- Insertar nueva categoría
INSERT INTO categories (name, description, icon) VALUES (?, ?, ?)

-- Actualizar categoría
UPDATE categories SET name = ?, description = ?, icon = ? WHERE id = ?

-- Eliminar categoría
DELETE FROM categories WHERE id = ?
```

### Listado de Sitios Web

```sql
-- Listar todos los sitios web con información de categoría
SELECT w.*, c.name as category_name 
FROM websites w 
LEFT JOIN categories c ON w.category_id = c.id
```

### Listar Sitios Web por Categoría

```sql
-- Obtener sitios web de una categoría específica
SELECT w.* 
FROM websites w 
WHERE w.category_id = ?
```

### Sitios Web Recientes

```sql
SELECT w.*, c.name as category_name 
FROM websites w 
LEFT JOIN categories c ON w.category_id = c.id
ORDER BY w.created_at DESC LIMIT 5
```

### Conteo de Sitios Web

```sql
-- Total de sitios web
SELECT COUNT(*) as total FROM websites

-- Total de sitios web por categoría
SELECT c.name, COUNT(w.id) as total 
FROM categories c 
LEFT JOIN websites w ON c.id = w.category_id 
GROUP BY c.id
```

### Inserción de Nuevo Sitio Web

```sql
INSERT INTO websites (category_id, name, url, description, logo, admin_url, plesk_url, phpmyadmin_url) 
VALUES (?, ?, ?, ?, ?, ?, ?, ?)
```
Utilizada en el módulo de websites para añadir un nuevo sitio web.

### Actualización de Sitio Web

```sql
UPDATE websites 
SET category_id=?, name=?, url=?, description=?, logo=?, admin_url=?, plesk_url=?, phpmyadmin_url=? 
WHERE id=?
```
Utilizada en el módulo de websites para actualizar un sitio web existente.

### Eliminación de Sitio Web

```sql
DELETE FROM websites WHERE id = ?
```
Utilizada en el módulo de websites para eliminar un sitio web.

## Actualización de la Base de Datos para Implementar Categorías

Hay dos formas de actualizar la base de datos para implementar el sistema de categorías:

### 1. Usando el script PHP interactivo

La forma más sencilla es utilizar el script PHP que hemos creado para automatizar el proceso:

1. Accede a `http://tu-servidor/admin/update-database.php`
2. El script ejecutará automáticamente todas las consultas necesarias
3. Te mostrará el progreso y resultado de cada paso
4. Al finalizar, podrás volver al panel de administración

Este método es recomendado para la mayoría de los usuarios ya que no requiere acceso directo a la base de datos.

### 2. Ejecutando el script SQL manualmente

Si prefieres hacerlo manualmente, puedes ejecutar el siguiente script SQL en tu gestor de base de datos:

```sql
-- Script para actualizar la base de datos con el sistema de categorías
-- Ejecuta este script en tu base de datos para implementar el sistema de categorías

-- Crear la tabla de categorías
CREATE TABLE IF NOT EXISTS categories (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL UNIQUE,
    description TEXT,
    icon VARCHAR(50),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Añadir campo category_id a la tabla websites si no existe
ALTER TABLE websites
ADD COLUMN IF NOT EXISTS category_id INT,
ADD CONSTRAINT fk_website_category FOREIGN KEY (category_id) REFERENCES categories(id) ON DELETE SET NULL;

-- Insertar algunas categorías de ejemplo
INSERT INTO categories (name, description, icon) VALUES 
('Programación', 'Sitios relacionados con desarrollo y programación', 'fa-code'),
('Hosting', 'Proveedores de hosting y servicios en la nube', 'fa-server'),
('Diseño', 'Recursos de diseño web y gráfico', 'fa-palette'),
('Juegos', 'Sitios de juegos y entretenimiento', 'fa-gamepad'),
('Herramientas', 'Utilidades y herramientas online', 'fa-tools');
```

Este script está disponible en el archivo `admin/database-update.sql`.

## Notas sobre la Implementación

- Se utilizan consultas preparadas para prevenir inyecciones SQL
- Las consultas se ejecutan a través del objeto `$conn` de tipo `mysqli`
- Las credenciales de la base de datos deben ajustarse según el entorno
- La relación entre websites y categories es una relación de muchos a uno (un sitio web pertenece a una categoría, una categoría puede tener muchos sitios web)
- Se utiliza `ON DELETE SET NULL` para que si se elimina una categoría, los sitios web asociados no se eliminen, sino que su campo `category_id` se establezca como NULL 