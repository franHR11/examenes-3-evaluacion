# Documentación Técnica del Proyecto

## Programación

### Elementos fundamentales del código
Utilizo diversos elementos fundamentales en mi código como variables para almacenar datos temporales, constantes para valores fijos (como BASE_URL en config.php), operadores aritméticos y lógicos para realizar operaciones y comparaciones, y varios tipos de datos como strings para textos (nombres, descripciones), integers para identificadores numéricos, arrays para colecciones de datos (como listas de documentos y categorías), y booleanos para valores de verdadero/falso en validaciones.

### Estructuras de control utilizadas
Implemento estructuras de selección (if-else) para validaciones de formularios y control de flujo, estructuras de repetición (while, foreach) para iterar sobre resultados de consultas y colecciones de datos, y saltos (return) para finalizar la ejecución de funciones y devolver valores. Estas estructuras son esenciales para el control de flujo en la aplicación, permitiendo tomar decisiones basadas en condiciones y procesar colecciones de datos de manera eficiente.

### Control de excepciones
Gestiono los errores mediante validaciones preventivas antes de realizar operaciones críticas. Por ejemplo, verifico la existencia de documentos antes de intentar editarlos, valido los datos de formularios antes de procesarlos, y compruebo la integridad referencial antes de eliminar registros. También utilizo mensajes de error personalizados que se muestran al usuario mediante la función setMessage() y redirecciones con la función redirect() para mantener una experiencia de usuario fluida incluso cuando ocurren errores.

### Documentación del código
He documentado exhaustivamente el código mediante comentarios de bloque PHPDoc que describen el propósito de cada clase, método y función, incluyendo parámetros, tipos de retorno y descripciones funcionales. También utilizo comentarios en línea para explicar secciones complejas o decisiones de implementación específicas, lo que facilita la comprensión y mantenimiento del código.

### Paradigma aplicado
Aplico principalmente el paradigma orientado a objetos, complementado con programación estructurada para funciones auxiliares. Elegí este enfoque híbrido porque la orientación a objetos proporciona una mejor organización, encapsulamiento y reutilización del código para los componentes principales (modelos y controladores), mientras que la programación estructurada ofrece simplicidad y claridad para funciones auxiliares y de utilidad.

### Clases y objetos principales
Las clases principales de mi proyecto son:
- `MarkdownController` y `MarkdownModel`: Gestionan los documentos markdown, su creación, edición, visualización y eliminación.
- `CategoryController` y `CategoryModel`: Manejan las categorías y subcategorías para organizar los documentos.
- `AuthController` y `UserModel`: Controlan la autenticación y gestión de usuarios.

Estas clases se relacionan siguiendo el patrón MVC, donde los controladores actúan como intermediarios entre las vistas y los modelos, coordinando las acciones del usuario y las operaciones de datos.

### Conceptos avanzados de POO
Implemento herencia implícita en la estructura de categorías, donde una categoría puede tener una categoría padre, creando una jerarquía. Utilizo polimorfismo en los métodos getAll() de los modelos, que pueden comportarse de manera diferente según los parámetros recibidos (con o sin paginación). También aplico encapsulamiento al hacer privados los atributos de las clases y proporcionar métodos públicos para interactuar con ellos.

### Gestión de información
Gestiono la información mediante un enfoque dual: almacenamiento en base de datos MySQL para metadatos y búsqueda eficiente, y archivos físicos para el contenido markdown. Para la interacción del usuario, utilizo interfaces gráficas web con formularios HTML, JavaScript para interactividad en el cliente, y PHP para el procesamiento en el servidor, siguiendo un flujo de solicitud-respuesta HTTP.

### Estructuras de datos utilizadas
Utilizo principalmente arrays asociativos para representar registros de la base de datos y colecciones de objetos, arrays indexados para listas de elementos, y strings para almacenar contenido markdown. Estas estructuras son ideales para el manejo de datos en PHP y facilitan la manipulación y presentación de información en la aplicación web.

### Técnicas avanzadas aplicadas
Aplico expresiones regulares para la generación de slugs a partir de nombres de categorías y documentos. También implemento flujos de entrada/salida para la lectura y escritura de archivos markdown en el sistema de archivos, y para la descarga de documentos por parte del usuario. Utilizo además técnicas de renderizado en tiempo real para la vista previa de markdown mientras se edita.

## Sistemas Informáticos

### Características del hardware
Mi entorno de desarrollo utiliza un equipo con procesador Intel i11, tarjeta gráfica RTX 3090 y Windows 11 Pro como sistema operativo. Para el entorno de producción, utilizo una máquina virtual Linux Server Ubuntu 24.04 con 2 vCore de CPU, 2 GB de RAM y 80 GB de almacenamiento NVMe SSD, configurada como un VPS tipo 2 2 80.

### Sistema operativo seleccionado
Para desarrollo, utilizo Windows 11 Pro por su interfaz amigable, herramientas de desarrollo integradas y compatibilidad con el software que necesito. Para producción, elegí Linux Server Ubuntu 24.04 por su estabilidad, seguridad, rendimiento optimizado para servidores web, menor consumo de recursos y amplia comunidad de soporte para aplicaciones web.

### Configuración de redes
En desarrollo, trabajo con una red local (Ethernet o Wi-Fi) donde Laragon configura un entorno localhost para acceder a la aplicación mediante HTTP. En producción, la aplicación es accesible a través de Internet mediante HTTPS, con un servidor configurado en un centro de datos con conectividad de alta velocidad. Utilizo Plesk para gestionar la configuración de red del servidor (dirección IP, DNS) y seguridad (firewalls, HTTPS con certificado SSL/TLS).

### Sistemas de copias de seguridad
Mi estrategia de copias de seguridad incluye el uso de Git como control de versiones para el código fuente, lo que proporciona un historial completo de cambios y la capacidad de revertir a versiones anteriores. En producción, utilizo los servicios de backup automáticos proporcionados por Plesk, que realizan copias periódicas de archivos y bases de datos a nivel de servidor, con programación regular y almacenamiento seguro.

### Medidas de seguridad de datos
Implemento varias medidas para asegurar la integridad y seguridad de los datos: autenticación de usuarios con contraseñas hasheadas mediante bcrypt, protección contra CSRF en formularios, validación de datos de entrada para prevenir inyección SQL, almacenamiento dual (base de datos y sistema de archivos) para redundancia, y uso de HTTPS en producción para cifrar la comunicación. También aplico permisos restrictivos en archivos y directorios del servidor.

### Configuración de usuarios y permisos
En desarrollo (Windows), ejecuto la aplicación con los permisos del usuario de Windows que inicia Laragon. En producción (Linux/Plesk), Plesk gestiona los usuarios del sistema (FTP, SSH) y configura los permisos de archivo/directorio para el usuario bajo el cual se ejecuta el servidor web (www-data o usuario específico). Los directorios que requieren escritura, como markdowns/, tienen permisos chmod 755 como se indica en el README.

### Documentación de configuración técnica
He documentado la configuración técnica en varios archivos: README.md contiene instrucciones de instalación, configuración de base de datos y URL base; CONEXIONES_BD.md detalla el esquema y consultas de la base de datos; y MEMORIAS.md registra las decisiones de diseño y cambios importantes como la implementación de subcategorías.

## Entornos de Desarrollo

### Entorno de desarrollo utilizado
Utilizo Cursor como editor de código principal, configurado con extensiones para PHP, HTML, CSS y JavaScript que proporcionan resaltado de sintaxis, autocompletado y depuración. También he personalizado atajos de teclado y temas para mejorar la productividad y reducir la fatiga visual durante largas sesiones de programación.

### Automatización de tareas
Automatizo tareas de desarrollo mediante scripts personalizados para la creación de usuarios (create_user_script.php) y generación de hashes (generate_hash.php). También utilizo Laragon para automatizar la configuración del servidor local, y aprovecho las funcionalidades de autocompletado y snippets de Cursor para acelerar la escritura de código repetitivo.

### Control de versiones
Utilizo Git como sistema de control de versiones con repositorios alojados en GitHub. Gestiono las versiones siguiendo un flujo de trabajo basado en ramas, donde mantengo una rama principal (main) estable y creo ramas de características para desarrollos específicos. Utilizo etiquetas para marcar versiones importantes y mensajes de commit descriptivos para documentar los cambios realizados.

### Estrategia de refactorización
Mi estrategia de refactorización se basa en identificar código duplicado o complejo y extraerlo en funciones o métodos reutilizables. Por ejemplo, he refactorizado la gestión de categorías para soportar subcategorías, mejorando la estructura sin romper la compatibilidad con el código existente. También aplico principios SOLID y patrones de diseño cuando es apropiado para mejorar la mantenibilidad del código.

### Documentación técnica
Documento técnicamente el proyecto mediante comentarios PHPDoc en el código fuente, archivos markdown detallados (README.md, CONEXIONES_BD.md, MEMORIAS.md) que explican la estructura, configuración y decisiones de diseño, y mensajes de commit descriptivos en Git. Esta documentación proporciona una referencia completa para entender y mantener el proyecto.

### Diagramas de modelado
No he encontrado diagramas de clases o comportamiento explícitos en el código revisado, pero la estructura del proyecto sigue claramente un patrón MVC (Modelo-Vista-Controlador) que se puede inferir de la organización de directorios y archivos. Cada módulo (auth, category, markdown) contiene sus propios controladores, modelos y vistas, siguiendo una arquitectura consistente.

## Bases de Datos

### Sistema gestor de bases de datos
Utilizo MySQL como sistema gestor de bases de datos por su robustez, rendimiento, amplia adopción en aplicaciones web PHP, excelente integración con el stack tecnológico del proyecto, y disponibilidad tanto en entorno de desarrollo (Laragon) como en producción (Plesk). MySQL proporciona todas las funcionalidades necesarias para almacenar y recuperar eficientemente los metadatos de documentos y categorías.

### Diseño del modelo entidad-relación
Mi modelo entidad-relación consta de tres tablas principales:
- `users`: Almacena información de usuarios (id, username, password, created_at).
- `categories`: Gestiona categorías con soporte para jerarquía (id, name, slug, parent_id, description, created_at, updated_at).
- `markdowns`: Almacena documentos markdown (id, nombre, descripcion, category_id, contenido, archivo, fecha_creacion, fecha_modificacion).

Las relaciones incluyen: markdowns -> categories (un documento pertenece a una categoría) y categories -> categories (relación recursiva para la jerarquía de categorías).

### Uso de funcionalidades avanzadas
Implemento varias funcionalidades avanzadas de SQL:
- Vistas: Utilizo consultas JOIN complejas que actúan como vistas virtuales para obtener documentos con información de categorías.
- Restricciones: Aplico claves foráneas con acciones ON DELETE SET NULL y ON UPDATE CASCADE para mantener la integridad referencial.
- Índices: Utilizo índices en campos clave como parent_id para optimizar las consultas de jerarquía.
- Funciones agregadas: Empleo COUNT() para la paginación y funciones de fecha para gestionar timestamps.

### Mecanismos de protección de datos
Implemento varios mecanismos para proteger y recuperar datos:
- Uso de consultas preparadas para prevenir inyección SQL.
- Almacenamiento dual (base de datos y archivos) para mayor seguridad.
- Restricciones de integridad referencial mediante claves foráneas.
- Validación de datos antes de realizar operaciones en la base de datos.
- Transacciones implícitas para mantener la consistencia de los datos.

## Lenguajes de Marcas y Sistemas de Gestión de Información

### Estructura de documentos HTML
Estructuro mis documentos HTML siguiendo estándares web modernos con HTML5, utilizando elementos semánticos como `<header>`, `<nav>`, `<main>`, `<section>`, y `<footer>` para mejorar la accesibilidad y SEO. Organizo el contenido de forma lógica y jerárquica, separando claramente la estructura (HTML), presentación (CSS) y comportamiento (JavaScript).

### Tecnologías frontend
Utilizo CSS3 para estilizar la interfaz de usuario, con un diseño responsive que se adapta a diferentes dispositivos. Para la interactividad, implemento JavaScript vanilla, evitando dependencias innecesarias de frameworks pesados. Esta elección proporciona un rendimiento óptimo, tiempos de carga rápidos y una experiencia de usuario fluida sin sacrificar funcionalidad.

### Interacción con el DOM
Implemento JavaScript para diversas interacciones con el DOM, como la vista previa en tiempo real del contenido markdown mientras se edita, la generación automática de tablas de contenido, la funcionalidad de copiar código con un clic, y la navegación suave entre secciones mediante enlaces internos. También utilizo JavaScript para validación de formularios en el lado del cliente.

### Validación de documentos
Aunque no se menciona explícitamente en el código revisado, sigo las mejores prácticas de HTML5 y CSS3 para asegurar la compatibilidad con los estándares web. Las vistas están estructuradas de manera consistente y utilizan atributos apropiados para mejorar la accesibilidad y usabilidad.

### Conversión entre formatos de datos
Implemento conversión entre formatos de datos, principalmente la transformación bidireccional entre Markdown y HTML utilizando la biblioteca Marked.js. Esta conversión es fundamental para el funcionamiento de la aplicación, permitiendo a los usuarios escribir en Markdown y visualizar el resultado formateado en HTML.

### Interacción con sistemas de gestión empresarial
Mi aplicación es en sí misma un sistema de gestión empresarial de tipo documental, diseñada para la gestión centralizada de documentación técnica en formato Markdown. Proporciona funcionalidades de creación, edición, organización jerárquica, búsqueda y visualización de documentos, lo que la hace ideal para equipos de desarrollo, escritores técnicos y empresas que necesitan mantener documentación estructurada.

## Proyecto Intermodular

### Objetivo del software
Mi software tiene como objetivo proporcionar un sistema centralizado para la creación, edición, organización y visualización de documentos en formato Markdown, con un enfoque en la seguridad, usabilidad y organización jerárquica de la información.

### Necesidad cubierta
Cubro la necesidad de las empresas y equipos de desarrollo de mantener documentación técnica privada y bien organizada, ofreciendo una alternativa autogestionada a servicios en la nube. Esto permite a los usuarios mantener el control total sobre sus datos sensibles mientras disfrutan de herramientas avanzadas para la creación y gestión de contenido.

### Stack tecnológico elegido
He elegido un stack LAMP (Linux, Apache, MySQL, PHP) complementado con JavaScript, HTML5 y CSS3 para el frontend. Seleccioné estas tecnologías por su robustez, amplia adopción en la industria, excelente documentación, rendimiento optimizado para aplicaciones web, y la capacidad de funcionar eficientemente en servidores con recursos moderados.

### Desarrollo por versiones
He planteado el desarrollo por versiones comenzando con una versión 1 que incluye la funcionalidad básica de gestión de documentos markdown y autenticación de usuarios. Las actualizaciones posteriores han añadido características como la organización jerárquica con categorías y subcategorías (documentado en MEMORIAS.md), mejoras en la visualización con colores personalizados para encabezados, y funcionalidades avanzadas como la tabla de contenidos automática y navegación mejorada.
