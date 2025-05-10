# MEMORIAS DEL PROYECTO PCpro-Tornado

## Estructura Principal

La aplicación fue construida siguiendo un diseño modular con separación de responsabilidades:

- **Sistema de autenticación**: Login y registro de usuarios
- **Panel de control**: Estadísticas de sitios y resumen general
- **Administración de sitios web**: CRUD completo para gestionar sitios
- **Sistema de categorías**: Clasificación de sitios web por categorías

## Decisiones de Diseño

### Frontend
- Se eligió **Bootstrap 5** como framework CSS para lograr una interfaz moderna y responsive.
- La interfaz sigue un diseño de panel de administración con barra lateral para navegación.
- Se utilizan iconos de **Font Awesome** para mejorar la experiencia visual.

### Backend
- Implementación en **PHP puro** con un enfoque modular.
- Base de datos **MySQL** para almacenamiento de información.
- Estructura de archivos organizada por funcionalidad.

### Seguridad
- Autenticación basada en sesiones.
- Validación de datos de entrada para prevenir inyecciones SQL.
- Comprobación de permisos antes de realizar operaciones.

## Cambios Implementados

### Versión Inicial (16-Feb-2025)
- Creación de estructura básica
- Implementación de sistema de autenticación
- Diseño base de la interfaz

### Versión 1.1 (24-Mar-2025)
- Implementación del sistema de categorías para clasificar los sitios web
- Actualización de la estructura de la base de datos
- Mejora de la interfaz para la gestión de categorías
- Filtrado de sitios web por categoría
- Estadísticas mejoradas en el dashboard

### Versión 1.2 (25-Mar-2025)
- Mejora en la visualización de botones de acceso en la lista de sitios web
- Solo se muestran los botones cuando el campo correspondiente tiene información
- Implementación de script automatizado para actualizar la base de datos
- Optimización de la experiencia de usuario ocultando enlaces innecesarios

### Versión 1.3 (25-Mar-2025)
- Mejora en la navegación: tanto el logo como el nombre de cada sitio web son ahora enlaces directos a la URL principal
- Optimización de la usabilidad permitiendo múltiples puntos de acceso a cada sitio web
- Adición de títulos en los enlaces para mejorar la experiencia del usuario
- Mejora en la accesibilidad mediante texto descriptivo en las imágenes

### Versión 1.4 - Sistema de Usuarios y Gestión de Registros

#### Fecha: <?php echo date('d-m-Y'); ?>

#### Cambios principales:

1. Sistema de Usuarios Completo
- Se ha implementado un sistema de gestión de usuarios que permite:
  - Registro de nuevos usuarios con correo electrónico y contraseña
  - Sistema de login mejorado con validación de campos
  - Verificación de estados de usuario (activo, pendiente, bloqueado)
  - Control de roles (administrador, usuario)
  - Almacenamiento seguro de contraseñas con hash

2. Panel de Administración de Usuarios
- Nuevo módulo de gestión de usuarios para administradores:
  - Listado de todos los usuarios registrados
  - Filtros para buscar usuarios por nombre, correo, estado y rol
  - Acciones para activar/bloquear usuarios
  - Control de promoción/degradación de administradores
  - Interfaz visual optimizada con indicadores de estado

3. Mejoras de Seguridad
- Cambios significativos en el sistema de autenticación:
  - Implementación de almacenamiento de contraseñas con hash
  - Verificación segura de identidad
  - Restricción de acceso basada en roles y estados
  - Protección de rutas según nivel de usuario

4. Cambios en la Base de Datos
- Estructura mejorada para la tabla de usuarios:
  - Nuevos campos: email, name, status, role
  - Control de estados mediante enumeraciones (active, pending, blocked)
  - Definición de roles (admin, user)
  - Script de actualización automática para bases de datos existentes

5. Mejoras en la Experiencia de Usuario
- Interfaz de login renovada con iconos y mensajes claros
- Página de registro con validaciones y feedback inmediato
- Integración con el resto del sistema manteniendo la estética
- Navegación mejorada con enlaces condicionales según el rol

#### Notas técnicas:
- Se ha creado un script de actualización (`admin/update-users-database.php`) para actualizar automáticamente la estructura de la base de datos
- Compatible con instalaciones anteriores, con migración automática de usuarios existentes
- La gestión de usuarios solo es accesible para administradores
- Las contraseñas se almacenan con hash para mayor seguridad

#### Próximos pasos:
- Implementar sistema de recuperación de contraseñas
- Añadir verificación por correo electrónico para nuevos registros
- Mejorar la gestión de permisos con niveles más granulares

## Versión 1.5 - Mejoras en la Gestión de Sesiones y Experiencia de Usuario

### Fecha: <?php echo date('d-m-Y'); ?>

### Cambios principales:

#### 1. Ampliación del Tiempo de Sesión
- Se ha incrementado la duración de las sesiones a 8 horas para evitar desconexiones frecuentes
- Implementación de un sistema de "ping" periódico para mantener la sesión activa
- Las sesiones ahora se mantienen vivas mientras el usuario navega, sin cerrar después de 20 minutos

#### 2. Sistema de "Recordar Sesión"
- Nueva opción "Mantener sesión iniciada" en la pantalla de login
- Implementación de cookies persistentes que duran 30 días
- El usuario puede permanecer logueado incluso después de cerrar el navegador

#### 3. Mejoras en los Mensajes de Error
- Mensajes de error más específicos y detallados durante el inicio de sesión
- Feedback claro sobre problemas con nombre de usuario o contraseña
- Información visual mejorada sobre estados de usuario (bloqueado, pendiente)

#### 4. Optimización del Proceso de Autenticación
- Refactorización del código de autenticación para mayor claridad
- Implementación de mejores prácticas de seguridad
- Mejor manejo de errores con registro detallado para diagnóstico

### Notas técnicas:
- Se han implementado cookies con duración de 30 días para usuarios que seleccionen "recordarme"
- Se utiliza JavaScript para hacer peticiones AJAX periódicas y mantener la sesión activa
- Configuración del sistema para extender la duración de sesión PHP a 8 horas (28800 segundos)
- Sistema compatible con navegadores modernos y dispositivos móviles

### Próximos pasos:
- Implementar un sistema completo de tokens en base de datos para mayor seguridad
- Añadir la opción de "cerrar todas las sesiones" para casos de seguridad
- Mejorar el sistema con renovación automática de tokens

## Mejoras Planificadas
- Implementar sistema de roles (admin, editor, visor)
- Implementar búsqueda y filtrado avanzado de sitios
- Mejorar seguridad con almacenamiento encriptado de contraseñas
- Añadir gestor de archivos para logos e imágenes

## Notas Técnicas
- La aplicación utiliza un sistema simple de enrutamiento basado en GET parameters
- Se utiliza la estructura de archivos para organizar módulos
- Carga dinámica de módulos según la URL solicitada
- Sistema de relaciones entre entidades para manejar las relaciones entre sitios web y categorías 