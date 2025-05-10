# UpTask Framework PHP

## Descripción General

UpTask Framework es una base sólida para iniciar proyectos PHP con un sistema completo de autenticación de usuarios y una estructura MVC bien organizada. Este framework incluye registro de usuarios, inicio de sesión, recuperación de contraseñas, envío de correos electrónicos de confirmación y validaciones, todo listo para usar.

Este proyecto está diseñado para servir como una plantilla o punto de partida para tus nuevos desarrollos, evitando reescribir la configuración básica y funcionalidades comunes en cada proyecto.

## Comenzando un Nuevo Proyecto

### 1. Clonar y Reiniciar Repositorio

Para usar este framework como base para un nuevo proyecto, sigue estos pasos:

```bash
# Clonar el repositorio (ajusta la URL según corresponda)
git clone <url-del-repositorio> mi-nuevo-proyecto

# Entrar al directorio del proyecto
cd mi-nuevo-proyecto

# Eliminar el historial de Git para empezar desde cero
rm -rf .git

# Iniciar un nuevo repositorio Git
git init

# Hacer el primer commit
git add .
git commit -m "Estado inicial basado en UpTask Framework"
```

### 2. Instalación de Dependencias

#### Dependencias PHP (Composer)

```bash
# Instalar dependencias PHP
composer install

# Si quieres actualizar las dependencias
composer update
```

#### Dependencias JavaScript/CSS (Node.js)

```bash
# Instalar dependencias de Node.js
npm install

# Si necesitas actualizar las dependencias
npm update
```

### 3. Configuración del Entorno

#### Base de Datos

1. Crea una base de datos para tu proyecto en MySQL.
2. Edita el archivo `includes/database.php` con los datos de conexión:

```php
$db = mysqli_connect('localhost', 'tu_usuario', 'tu_password', 'nombre_db');
```

#### Configuración de Email

Para configurar el envío de emails, edita la información en las clases Email (`classes/Email.php`):

- Para desarrollo local (Mailpit):
  ```php
  $mail->Host = '127.0.0.1';
  $mail->Port = 1025;
  ```

- Para producción (servidor SMTP):
  ```php
  $mail->Host = 'mail.tudominio.com';
  $mail->Port = 587; // o 465 para SSL
  $mail->SMTPAuth = true;
  $mail->Username = 'usuario@tudominio.com';
  $mail->Password = 'tu_password';
  $mail->SMTPSecure = 'tls'; // o 'ssl'
  ```

### 4. Construcción de Assets (CSS/JS)

Gulp está configurado para compilar tus archivos SCSS y JavaScript:

```bash
# Iniciar Gulp para compilar y observar cambios
npm run dev
# o simplemente
gulp

# Solo compilar sin modo watch
gulp css
gulp js
```

## Estructura del Proyecto

```
/
├── classes/              # Clases auxiliares (Email, etc.)
├── controllers/          # Controladores MVC
├── includes/             # Archivos de configuración global
│   ├── app.php           # Carga y lógica principal
│   ├── database.php      # Configuración de base de datos
│   └── funciones.php     # Funciones auxiliares
├── models/               # Modelos de datos
│   ├── ActiveRecord.php  # Clase base para modelos ORM
│   └── Usuario.php       # Modelo de usuario
├── public/               # Archivos públicos
│   └── build/            # Assets compilados (CSS/JS)
├── src/                  # Código fuente
│   ├── js/               # JavaScript sin compilar
│   └── scss/             # Archivos SCSS
├── vendor/               # Dependencias de Composer
├── views/                # Vistas MVC
│   ├── auth/             # Vistas de autenticación
│   └── templates/        # Plantillas reutilizables
├── Router.php            # Enrutador principal
├── composer.json         # Configuración de Composer
├── gulpfile.js           # Configuración de Gulp
└── package.json          # Configuración de Node.js
```

## Funcionalidades Incluidas

### Autenticación de Usuarios
- Registro de usuarios con validación
- Confirmación de cuenta por email
- Inicio de sesión seguro
- Recuperación de contraseña
- Tokens únicos para acciones seguras

### Frontend
- Compilación de SCSS a CSS (con compresión)
- Minificación de JavaScript
- Estructura de archivos SCSS organizada
- Modo watch para desarrollo

### Backend
- Estructura MVC completa
- Sistema de enrutamiento
- Modelos con ActiveRecord
- Validaciones de formularios
- Manejo de sesiones
- Alertas y mensajes de error/éxito

## Al Iniciar un Nuevo Proyecto

1. **Personaliza los datos del proyecto**:
   - Edita `composer.json` con tu nombre y descripción
   - Actualiza `package.json` con los detalles de tu proyecto

2. **Estructura de Base de Datos**:
   - La tabla `usuarios` ya está configurada
   - Añade las tablas adicionales que necesites para tu proyecto

3. **Personalización visual**:
   - Modifica los archivos SCSS en `src/scss/`
   - Actualiza las vistas en `views/`

4. **Rutas y controladores**:
   - Añade nuevas rutas en `Router.php`
   - Crea nuevos controladores en `controllers/`

5. **Modelos de datos**:
   - Utiliza `ActiveRecord` para crear nuevos modelos

## Recomendaciones de Seguridad

- Actualiza regularmente las dependencias con `composer update` y `npm update`
- Utiliza contraseñas seguras para la base de datos
- En producción, usa HTTPS
- No expongas información sensible en repositorios públicos

## Comandos Útiles

```bash
# Iniciar el servidor de desarrollo (PHP)
php -S localhost:3000

# Iniciar compilación de assets
gulp

# Solo compilar CSS
gulp css

# Solo compilar JS
gulp js

# Modo desarrollo (vigilar cambios)
gulp dev
```

---

Este framework fue desarrollado inicialmente como parte del proyecto UpTask y adaptado para servir como base para futuros desarrollos.
