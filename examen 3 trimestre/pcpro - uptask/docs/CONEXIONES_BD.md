# Configuración de Base de Datos para UpTask Framework

Este documento contiene los comandos SQL necesarios para configurar la base de datos y las tablas requeridas por el framework UpTask.

## Creación de la Base de Datos

```sql
-- Crear la base de datos
CREATE DATABASE IF NOT EXISTS uptask;

-- Seleccionar la base de datos
USE uptask;
```

## Tabla de Usuarios

La tabla `usuarios` almacena toda la información relacionada con los usuarios del sistema, incluyendo credenciales, tokens de confirmación y estado de cuenta.

```sql
CREATE TABLE `usuarios` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nombre` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci DEFAULT NULL,
  `email` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci DEFAULT NULL,
  `password` varchar(60) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci DEFAULT NULL,
  `token` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci DEFAULT NULL,
  `confirmado` tinyint(1) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;
```


```sql
CREATE TABLE `proyectos` (
	`id` INT NOT NULL AUTO_INCREMENT,
	`proyecto` VARCHAR(60) NULL DEFAULT NULL COLLATE 'utf8mb4_spanish_ci',
	`url` VARCHAR(32) NULL DEFAULT NULL COLLATE 'utf8mb4_spanish_ci',
	`propietarioId` INT NULL DEFAULT NULL,
	PRIMARY KEY (`id`) USING BTREE,
	INDEX `FK_proyectos_usuarios` (`propietarioId`) USING BTREE,
	CONSTRAINT `FK_proyectos_usuarios` FOREIGN KEY (`propietarioId`) REFERENCES `usuarios` (`id`) ON UPDATE SET NULL ON DELETE SET NULL
)
COLLATE='utf8mb4_spanish_ci'
ENGINE=InnoDB
;
```



## Consultas SQL Importantes

### Autenticación de Usuarios

```sql
-- Buscar usuario por email (usado en login y recuperación de contraseña)
SELECT * FROM usuarios WHERE email = '[email_del_usuario]';

-- Buscar usuario por token (usado en confirmación y restablecimiento de contraseña)
SELECT * FROM usuarios WHERE token = '[token_del_usuario]';
```

### Gestión de Usuarios

```sql
-- Insertar nuevo usuario
INSERT INTO usuarios (nombre, email, password, token, confirmado) 
VALUES ('[nombre]', '[email]', '[password_hasheado]', '[token]', 0);

-- Actualizar información de usuario
UPDATE usuarios 
SET nombre = '[nombre]', email = '[email]' 
WHERE id = [id_usuario];

-- Confirmar cuenta de usuario
UPDATE usuarios 
SET confirmado = 1, token = NULL 
WHERE token = '[token]';

-- Actualizar contraseña de usuario
UPDATE usuarios 
SET password = '[nuevo_password_hasheado]', token = NULL 
WHERE token = '[token]';
```

## Estructura de la Base de Datos

El framework UpTask utiliza un enfoque ORM a través de la clase ActiveRecord, que permite la manipulación sencilla de los registros de la base de datos.

Para añadir nuevas tablas a tu proyecto, deberás:

1. Crear la tabla en la base de datos
2. Crear un modelo correspondiente que extienda de la clase ActiveRecord
3. Definir las propiedades y métodos específicos de la tabla

## Recomendaciones

- Utiliza contraseñas seguras para la conexión a la base de datos
- Mantén actualizada la estructura con comandos CREATE TABLE IF NOT EXISTS
- Realiza backups periódicos de tus datos
- Considera añadir índices para mejorar el rendimiento en tablas grandes
