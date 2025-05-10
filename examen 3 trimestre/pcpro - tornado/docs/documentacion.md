# Documentación Técnica PCpro-Tornado

## Programación

### Elementos fundamentales del código
- **Variables**: Utilizo variables para almacenar datos temporales como `$username`, `$password`, `$conn`, `$result`, `$user`, `$total_websites`, etc.
- **Constantes**: He definido constantes para la conexión a la base de datos (`DB_HOST`, `DB_USER`, `DB_PASS`, `DB_NAME`) en el archivo `admin/config/database.php`.
- **Operadores**: Implemento operadores aritméticos (+, -), de comparación (==, ===, !=, <, >), lógicos (&&, ||, !), de asignación (=) y operadores ternarios.
- **Tipos de datos**: Trabajo con strings para nombres y textos, integers para IDs y contadores, arrays asociativos para resultados de consultas, booleanos para validaciones y timestamps para fechas.

### Estructuras de control
- **Selección**: Utilizo `if/else` para validar formularios y permisos de usuario, y `switch/case` para manejar diferentes acciones en los módulos (como en `websites/index.php`).
- **Repetición**: Implemento bucles `while` para recorrer resultados de consultas SQL y `foreach` para iterar sobre arrays.
- **Saltos**: Uso `return` para finalizar funciones y `break` para salir de estructuras switch.

### Control de excepciones
- Implemento bloques `try/catch` en funciones críticas como `validateLogin()` para capturar y manejar excepciones.
- Gestiono errores mediante mensajes específicos almacenados en variables de sesión (`$_SESSION['login_error']`).
- Utilizo funciones como `error_log()` para registrar errores en el sistema.

### Documentación del código
- He documentado las funciones y módulos principales con comentarios descriptivos.
- Incluyo comentarios de cabecera en los archivos principales indicando autor y propósito.
- Añado comentarios explicativos en secciones complejas del código.

### Paradigma de programación
- Aplico programación estructurada con un enfoque modular, organizando el código en funciones reutilizables.
- Elijo este paradigma por su simplicidad y facilidad de mantenimiento en aplicaciones web PHP tradicionales.

### Clases y objetos principales
- No implemento clases propias, pero utilizo objetos nativos de PHP como:
  - `mysqli` para la conexión y operaciones con la base de datos
  - `mysqli_stmt` para consultas preparadas
  - `mysqli_result` para resultados de consultas

### Conceptos avanzados (herencia, polimorfismo, interfaces)
- No implemento estos conceptos avanzados de POO, ya que el proyecto sigue un enfoque de programación estructurada.

### Gestión de información mediante archivos
- Gestiono la información principalmente a través de la base de datos MySQL.
- Utilizo interfaces gráficas web (HTML/CSS/Bootstrap) para la interacción del usuario.
- Manejo archivos para almacenar logos de sitios web en el directorio `admin/uploads/logos/`.

### Estructuras de datos
- Utilizo arrays asociativos para manejar resultados de consultas y datos de formularios.
- Implemento arrays indexados para listar elementos como usuarios, sitios web y categorías.
- Trabajo con matrices bidimensionales para representar relaciones entre entidades.

### Técnicas avanzadas
- Aplico consultas SQL complejas con JOIN para relacionar tablas.
- Utilizo expresiones regulares para validaciones.
- Implemento flujos de entrada/salida para la carga de archivos (logos).
- Uso consultas preparadas para prevenir inyecciones SQL.

## Sistemas Informáticos

### Características del hardware
- **Entorno de desarrollo**: Trabajo con un equipo Windows 11 Pro con procesador Intel i11, tarjeta gráfica RTX 3090, que proporciona un rendimiento óptimo para el desarrollo web.
- **Entorno de producción**: El proyecto se despliega en una máquina virtual con 2 vCores, 2GB de RAM y 80GB de almacenamiento NVMe SSD, suficiente para una aplicación web PHP con tráfico moderado.

### Sistema operativo seleccionado
- **Desarrollo**: Utilizo Windows 11 Pro por su compatibilidad con las herramientas de desarrollo web y su interfaz intuitiva.
- **Producción**: Implemento Ubuntu Server 24.04 por su estabilidad, seguridad y rendimiento optimizado para servidores web.

### Configuración de redes
- En desarrollo, trabajo con una red local configurada por Laragon que establece un servidor local accesible vía localhost.
- En producción, configuro el servidor con acceso a Internet mediante protocolos HTTP/HTTPS.
- Implemento seguridad mediante HTTPS con certificados SSL/TLS y firewalls configurados a nivel de servidor.

### Sistemas de copias de seguridad
- En desarrollo, utilizo Git como sistema principal de control de versiones y respaldo de código.
- En producción, configuro backups automáticos diarios de la base de datos y archivos del sitio mediante las herramientas de Plesk.

### Medidas de seguridad e integridad de datos
- Implemento consultas preparadas para prevenir inyecciones SQL.
- Almaceno contraseñas con hash para proteger la información de los usuarios.
- Valido todos los datos de entrada para prevenir ataques XSS.
- Gestiono sesiones seguras con tiempos de expiración configurados.
- Implemento control de acceso basado en roles (admin, user).

### Configuración de usuarios y permisos
- En desarrollo, trabajo con los permisos del usuario de Windows que ejecuta Laragon.
- En producción, configuro usuarios específicos para el servidor web con permisos limitados.
- Establezco permisos de escritura solo en directorios necesarios como `uploads/logos/`.

### Documentación de configuración técnica
- Documento la configuración en archivos markdown como `README.md`, `CONEXIONES_BD.md` y `MEMORIAS.md`.
- Incluyo instrucciones detalladas de instalación, configuración y requisitos del sistema.

## Entornos de Desarrollo

### Entorno de desarrollo (IDE)
- Utilizo Cursor como editor principal por su integración con IA para asistencia en el desarrollo.
- Lo configuro con extensiones para PHP, HTML, CSS y JavaScript para mejorar la productividad.

### Automatización de tareas
- Automatizo la actualización de la base de datos mediante scripts PHP (`update-database.php`, `update-users-database.php`).
- Utilizo Laragon para gestionar automáticamente el servidor web local.

### Control de versiones
- Implemento Git para el control de versiones del proyecto.
- Alojo el repositorio en GitHub (https://github.com/franHR11/pcpro-tornado.git).
- Gestiono versiones mediante etiquetas para cada release y utilizo ramas para nuevas funcionalidades.

### Estrategia de refactorización
- Organizo el código en módulos independientes para facilitar su mantenimiento.
- Extraigo funcionalidades comunes a archivos de inclusión como `auth.php`.
- Separo la lógica de negocio de la presentación mediante archivos específicos para cada función.

### Documentación técnica
- Documento el proyecto utilizando archivos markdown (`README.md`, `CONEXIONES_BD.md`, `MEMORIAS.md`).
- Incluyo comentarios en el código para explicar funcionalidades complejas.
- Mantengo un registro de cambios y versiones en `MEMORIAS.md`.

### Diagramas de clases o comportamiento
- No he implementado diagramas específicos para este proyecto, ya que sigue un enfoque de programación estructurada.

## Bases de Datos

### Sistema gestor de bases de datos
- Selecciono MySQL como SGBD por su robustez, rendimiento y compatibilidad con PHP.
- Esta elección facilita la gestión de relaciones entre entidades (usuarios, categorías, sitios web).

### Diseño del modelo entidad-relación
- **Entidades principales**: users, categories, websites.
- **Relaciones**:
  - Una categoría puede tener múltiples sitios web (1:N).
  - Un sitio web pertenece a una categoría (N:1).
  - Implemento claves foráneas como `category_id` en la tabla `websites`.

### Vistas, procedimientos almacenados, disparadores
- No implemento estos elementos avanzados, optando por gestionar la lógica desde PHP para mayor flexibilidad.

### Mecanismos de protección y recuperación
- Utilizo consultas preparadas para prevenir inyecciones SQL.
- Implemento transacciones para operaciones críticas.
- Configuro backups automáticos de la base de datos a través de Plesk.

## Lenguajes de Marcas y Sistemas de Gestión de Información

### Estructura de documentos HTML
- Estructuro los documentos HTML siguiendo estándares web actuales con DOCTYPE HTML5.
- Implemento etiquetas semánticas como `header`, `nav`, `main`, `section`, `footer`.
- Aplico buenas prácticas como la separación de contenido y presentación.

### Tecnologías frontend
- Utilizo **Bootstrap 5** como framework CSS para crear una interfaz responsive y moderna.
- Implemento **FontAwesome** para iconografía visual.
- Aplico CSS personalizado para ajustes específicos de diseño.
- Uso JavaScript para mejorar la interactividad, especialmente en filtros y validaciones.

### Interacción con el DOM
- Implemento JavaScript para manipular el DOM en funcionalidades como:
  - Filtrado en tiempo real de usuarios
  - Validación de formularios
  - Confirmaciones de eliminación
  - Mantenimiento de sesiones activas

### Validación de documentos
- Aseguro que el HTML y CSS cumplen con los estándares web actuales.
- Implemento validación de formularios tanto en el cliente (JavaScript) como en el servidor (PHP).

### Conversión de datos entre formatos
- No implemento conversión entre XML y JSON en este proyecto, ya que la comunicación de datos se realiza principalmente a través de PHP y MySQL.

### Interacción con sistemas de gestión empresarial
- PCpro-Tornado es en sí mismo una aplicación de gestión empresarial de tipo CMS (Content Management System) especializada en la administración centralizada de sitios web.
- Permite gestionar múltiples proyectos web desde un único panel, optimizando los flujos de trabajo para agencias y desarrolladores.

## Proyecto Intermodular

### Objetivo del software
- PCpro-Tornado tiene como objetivo centralizar la gestión de múltiples sitios web en una única plataforma, facilitando su administración, categorización y acceso.

### Necesidad que cubre
- Soluciona el problema de gestionar múltiples proyectos web dispersos, proporcionando un punto único de acceso y control.
- Facilita la organización de sitios por categorías y el acceso rápido a paneles de administración, Plesk y phpMyAdmin.

### Stack de tecnologías
- **Backend**: PHP puro con enfoque modular
- **Base de datos**: MySQL
- **Frontend**: HTML5, CSS3, Bootstrap 5, FontAwesome
- **Servidor**: Apache/Nginx en Ubuntu Server
- He elegido estas tecnologías por su robustez, facilidad de implementación y mantenimiento, y por ser estándares en el desarrollo web.

### Desarrollo por versiones
- **Versión 1.0**: Implementación de estructura básica, sistema de autenticación e interfaz inicial.
- **Versión 1.1**: Adición del sistema de categorías y mejoras en la estructura de la base de datos.
- **Versión 1.2**: Optimización de la interfaz de usuario y scripts de actualización automática.
- **Versión 1.3**: Mejoras en la navegación y usabilidad.
- **Versión 1.4**: Implementación del sistema completo de usuarios y gestión de registros.
- **Versión 1.5**: Mejoras en la seguridad y duración de sesiones.

Este enfoque de desarrollo incremental ha permitido ir añadiendo funcionalidades de forma progresiva, asegurando la estabilidad del sistema en cada fase.
