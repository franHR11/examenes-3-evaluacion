# PCpro - Tornado: Gestor de Sitios Web

## Sección Comercial
Tornado es un gestor de sitios web diseñado para administrar y controlar fácilmente todos tus enlaces web importantes en un solo lugar. Organiza tus sitios web con imágenes personalizadas, descripciones y enlaces directos a herramientas de administración.

## Descripción y Características
Tornado es una aplicación web de administración que te permite:

- **Gestionar Sitios Web**: Almacena y organiza tus sitios web favoritos
- **Sistema de Categorías**: Clasifica tus sitios por categorías (programación, hosting, juegos, etc.)
- **Enlaces Rápidos**: Acceso directo a la web, panel de administración, Plesk y phpMyAdmin
- **Imágenes Personalizadas**: Añade logotipos para identificar visualmente cada sitio
- **Panel Administrativo**: Interfaz limpia y moderna usando Bootstrap 5
- **Filtrado por Categoría**: Filtra rápidamente tus sitios web por categoría
- **Dashboard Estadístico**: Visualiza información sobre categorías y sitios web
- **Seguridad Incorporada**: Sistema de autenticación para proteger tus datos

## Funcionalidades Principales

### 1. Gestión de Websites
* Administración de múltiples sitios web con sus URLs
* Enlaces directos a paneles de administración, Plesk y phpMyAdmin
* Organización por categorías para mejor gestión
* Previsualización de los sitios mediante logos personalizados

### 2. Sistema de Categorías
* Clasificación jerárquica de sitios web
* Gestión visual de categorías (crear, modificar, eliminar)
* Filtrado de websites por categoría
* Estadísticas de uso por categoría

### 3. Sistema de Usuarios
* Registro de nuevos usuarios con correo electrónico
* Panel de administración para gestionar usuarios
* Control de acceso basado en roles (administrador/usuario)
* Gestión de estados de usuario (activo, pendiente, bloqueado)
* Interfaz intuitiva para activar, bloquear o cambiar roles

## Sección Técnica

### Requisitos
- PHP 7.4 o superior
- MySQL/MariaDB
- Servidor web (Apache, Nginx)
- Navegador web moderno

### Instalación
1. Clona el repositorio en tu servidor web
2. Importa el archivo `admin/database.sql` en tu base de datos MySQL
3. Configura las credenciales de base de datos en `admin/config/database.php`
4. Accede a la aplicación a través de tu navegador web
5. Inicia sesión usando las credenciales predeterminadas (usuario: admin, contraseña: admin)

### Actualización a la versión con Categorías
Si ya tenías instalada una versión anterior:
1. Accede a `http://tu-servidor/update-database.php`
2. Este script actualizará automáticamente la estructura de la base de datos e insertará las categorías de ejemplo
3. Una vez completada la actualización, podrás utilizar el sistema de categorías

### Estructura del Proyecto
- **admin/**: Directorio principal de la aplicación
  - **config/**: Configuración de base de datos
  - **includes/**: Archivos incluidos como autenticación, cabecera y barra lateral
  - **modules/**: Módulos de la aplicación (dashboard, websites, categories)
  - **assets/**: Recursos estáticos (CSS, imágenes)
  - **uploads/**: Directorio para subir archivos

### Uso
1. **Inicio de sesión**: Accede a través de login.php con tus credenciales
2. **Dashboard**: Visualiza estadísticas, categorías y sitios web recientes
3. **Categorías**: Gestiona las categorías para clasificar tus sitios web
4. **Sitios Web**: Administra (añade, edita, elimina) tus sitios web
5. **Filtrado**: Filtra tus sitios web por categoría
6. **Cierre de sesión**: Finaliza la sesión a través de logout.php

## Instalación y Configuración

### Requisitos previos
* Servidor web con PHP 7.0 o superior
* MySQL 5.6 o superior
* Extensiones PHP: mysqli, gd, json

### Pasos de instalación
1. Descarga los archivos del proyecto a tu servidor web
2. Crea una base de datos MySQL para el proyecto
3. Configura los datos de conexión en `admin/config/database.php`
4. Accede a `http://tu-dominio.com/update-database.php` para crear las tablas necesarias para categorías
5. Accede a `http://tu-dominio.com/update-users-database.php` para configurar el sistema de usuarios
6. Inicia sesión con el usuario predeterminado:
   * Usuario: admin
   * Contraseña: admin
7. ¡Importante! Cambia las credenciales del administrador después del primer inicio de sesión 