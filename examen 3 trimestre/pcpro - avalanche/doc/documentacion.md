# Documentación Técnica del Proyecto

## Programación

### Elementos fundamentales del código
- Uso de variables, constantes y tipos de datos estándar de PHP (strings, enteros, arrays, booleanos).
- Definición de constantes de configuración para BD y aplicación (`DB_HOST`, `DB_NAME`, etc.).
- Operadores aritméticos, lógicos y de comparación en la lógica de negocio y validaciones.

### Estructuras de control
- Selección: if, else, switch (para flujos de autenticación, rutas, validaciones).
- Repetición: bucles for, foreach y while para recorrer arrays y resultados de BD.
- Saltos: break y continue para control de bucles.

### Control de excepciones y gestión de errores
- Uso de try-catch en conexiones a base de datos (PDO) y operaciones críticas.
- Registro de errores en logs (`logs/php_errors.log`).
- Control de errores de usuario mediante mensajes y redirecciones.

### Documentación y comentarios
- Comentarios descriptivos en cabeceras de archivos y funciones clave.
- Uso de docstrings en funciones y clases principales.

### Paradigma de programación
- Predomina la programación estructurada y modular.
- Uso de clases para la gestión de la base de datos (`Database`), con orientación a objetos.

### Clases y objetos principales
- Clase `Database` para la conexión y gestión de BD.
- Estructuras modulares para campañas, usuarios, contactos, plantillas y logs.

### Conceptos avanzados
- Uso de PDO para abstracción y seguridad en acceso a BD.
- No se emplean herencia ni interfaces explícitas en el núcleo, pero la estructura permite ampliación.

### Gestión de información mediante archivos
- Gestión de logs y backups mediante archivos en carpetas dedicadas.
- Subida y gestión de archivos en `/uploads`.

### Estructuras de datos
- Arrays asociativos y numéricos para almacenamiento temporal y procesamiento.

### Técnicas avanzadas
- Uso de expresiones regulares para validación de emails y datos.
- Flujos de entrada/salida para logs, backups y subida de archivos.

## Sistemas Informáticos

### Características del hardware
- Desarrollo: Windows 11 Pro, Intel i11, RTX 3090, 32GB RAM, SSD NVMe.
- Producción: VPS Ubuntu 24.04, 2 vCore, 2 GB RAM, 80 GB NVMe SSD.

### Sistema operativo
- Desarrollo: Windows 11 Pro.
- Producción: Ubuntu Server 24.04 LTS.

### Configuración de redes
- Desarrollo: Red local (Ethernet/Wi-Fi), acceso vía localhost.
- Producción: Acceso público HTTP/HTTPS, firewall y seguridad gestionada por Plesk.

### Copias de seguridad
- Desarrollo: Copias manuales y uso de Git.
- Producción: Backups automáticos en Plesk y copias de seguridad de BD y archivos.

### Integridad y seguridad de datos
- Uso de permisos restrictivos en carpetas sensibles (`logs/`, `uploads/`).
- Control de acceso por roles en la aplicación.
- Conexión segura a BD mediante PDO y parámetros externos.
- Uso de HTTPS en producción.

### Configuración de usuarios y permisos
- Desarrollo: Permisos del usuario de Windows.
- Producción: Permisos gestionados por Plesk y usuario del servidor web.

### Documentación de configuración técnica
- README.md: Instalación, configuración y uso.
- docs/CONEXIONES_BD.md: Esquema y consultas de BD.
- docs/MEMORIAS.md: Decisiones de diseño.

## Entornos de Desarrollo

### Entorno de desarrollo (IDE)
- Editor principal: Cursor.
- Complementos: GitHub Copilot, integración con Git.

### Automatización de tareas
- Uso de Composer para dependencias PHP.
- Scripts de mantenimiento en `/scripts`.
- Comandos para instalación y despliegue documentados en README.md.

### Control de versiones
- Uso de Git y repositorios en GitHub.
- Gestión de ramas para desarrollo y producción.

### Estrategia de refactorización
- Refactorización incremental, asegurando compatibilidad y estabilidad.
- Uso de control de versiones para revertir cambios si es necesario.

### Documentación técnica
- Documentación en Markdown (`README.md`, `documentacion.md`).
- Comentarios en el código y docstrings.

### Diagramas
- No se incluyen diagramas explícitos en el repositorio. Se recomienda su uso para modelado futuro.

## Bases de Datos

### Sistema gestor de bases de datos
- MySQL (principal) y soporte para SQLite en desarrollo.

### Modelo entidad-relación
- Tablas principales: `users`, `campaigns`, `contacts`, `templates`, `logs`, `tracking`.
- Relaciones: usuarios gestionan campañas, campañas se envían a contactos, logs y tracking almacenan eventos.

### Vistas, procedimientos y funciones avanzadas
- No se emplean procedimientos almacenados ni triggers en el núcleo.
- Consultas SQL optimizadas y parametrizadas.

### Protección y recuperación de datos
- Copias de seguridad automáticas y manuales.
- Uso de backups y logs para restauración.

## Lenguajes de Marcas y Sistemas de Gestión de Información

### Estructura de documentos HTML
- Uso de HTML5 semántico, separación de contenido y presentación.
- Buenas prácticas de accesibilidad y estructura.

### Tecnologías frontend
- CSS3 para estilos (ubicado en `/assets/css/style.css`).
- JavaScript para interactividad básica (ubicado en `/assets/js/script.js`).

### Interacción con el DOM
- JavaScript manipula elementos del DOM para formularios y validaciones.

### Validación de HTML y CSS
- Se recomienda validar con herramientas estándar (W3C Validator).

### Conversión de datos entre formatos
- Uso de JSON para intercambio de datos y configuración.

### Integración con sistemas de gestión empresarial
- La aplicación es una solución de gestión empresarial para email marketing.
- No integra con ERPs externos por defecto.

## Proyecto Intermodular

### Objetivo del software
- Facilitar la gestión integral de campañas de email marketing.

### Necesidad que cubre o problema que soluciona
- Automatiza el envío, seguimiento y análisis de campañas de correo masivo.
- Centraliza la gestión de usuarios, contactos y plantillas.

### Stack de tecnologías elegido
- PHP 7.4+, MySQL, HTML5, CSS3, JavaScript, Composer, PHPMailer.
- Entorno compatible con Windows y Linux.

### Desarrollo por versiones
- Versión 1: Funcionalidad mínima (gestión de campañas, usuarios y contactos).
- Actualizaciones: Añadido panel de estadísticas, editor de plantillas y sistema de backups.

---

**Esta documentación resume la configuración, arquitectura y buenas prácticas aplicadas en el desarrollo y despliegue del proyecto Avalanche Email Marketing System.**
