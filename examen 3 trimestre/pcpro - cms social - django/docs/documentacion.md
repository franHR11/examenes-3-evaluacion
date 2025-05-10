# Documentación Técnica del Proyecto WebPlayground

## Programación

### ¿Qué elementos fundamentales incluye vuestro código (variables, constantes, operadores, tipos de datos)?
Nuestro código incluye diversos elementos fundamentales de programación:
- **Variables**: Utilizamos variables para almacenar datos temporales y estados, como en las vistas para almacenar objetos recuperados de la base de datos.
- **Constantes**: Definimos constantes en el archivo settings.py como SECRET_KEY, DEBUG, ALLOWED_HOSTS y configuraciones de bases de datos.
- **Operadores**: Implementamos operadores de comparación (==, !=, >, <), operadores lógicos (and, or, not) y operadores de asignación (=, +=).
- **Tipos de datos**: Trabajamos con tipos de datos básicos como strings, integers, booleans, y tipos complejos como listas, diccionarios y objetos.

### ¿Qué estructuras de control habéis usado y por qué (selección, repetición, saltos)?
Implementamos diversas estructuras de control para manejar el flujo de la aplicación:
- **Selección**: Utilizamos if-else para controlar el flujo de ejecución basado en condiciones, como verificar si un usuario está autenticado o tiene permisos.
- **Repetición**: Empleamos bucles for para iterar sobre colecciones de datos, como al procesar mensajes o listar páginas.
- **Saltos**: Utilizamos return para salir de funciones y redirect para redirigir a los usuarios a diferentes páginas tras completar acciones.

### ¿Habéis implementado control de excepciones? ¿Cómo gestionáis errores?
Implementamos control de excepciones para manejar errores de forma elegante:
- Utilizamos try-except para capturar excepciones específicas, como en la gestión de archivos y operaciones de base de datos.
- Implementamos validaciones en los formularios para prevenir errores de entrada de datos.
- Utilizamos el sistema de mensajes de Django para mostrar errores al usuario.
- Levantamos excepciones Http404 cuando un recurso no existe o el usuario no tiene permisos.

### ¿Habéis documentado el código mediante comentarios o docstrings?
Documentamos el código de varias formas:
- Incluimos comentarios explicativos en secciones complejas del código.
- Utilizamos docstrings en clases y funciones para explicar su propósito y funcionamiento.
- Creamos archivos de documentación específicos como README.md, MEMORIAS.md y CONEXIONES_BD.md.
- Seguimos las convenciones de nomenclatura de Django para hacer el código más legible y autoexplicativo.

### ¿Qué paradigma habéis aplicado (estructurada, orientada a objetos)? ¿Por qué lo habéis elegido?
Aplicamos principalmente el paradigma de programación orientada a objetos porque:
- Django está diseñado siguiendo este paradigma, con modelos que representan tablas de la base de datos y vistas basadas en clases.
- La POO facilita la reutilización de código mediante herencia y composición.
- Permite una mejor organización del código en módulos y clases con responsabilidades específicas.
- Facilita la implementación de patrones de diseño como el patrón MTV (Model-Template-View) de Django.

### ¿Qué clases y objetos principales forman vuestro proyecto? ¿Cómo se relacionan entre sí?
Las clases principales de nuestro proyecto son:
- **User**: Modelo de Django para la autenticación de usuarios.
- **Profile**: Extiende User con campos adicionales como avatar, biografía y enlaces.
- **Page**: Almacena páginas de contenido creadas por los usuarios con título, contenido y orden.
- **Thread**: Representa conversaciones entre usuarios.
- **Message**: Almacena mensajes individuales dentro de un Thread.

Estas clases se relacionan entre sí mediante:
- Relaciones uno a uno (User-Profile).
- Relaciones muchos a muchos (Thread-User, Thread-Message).
- Relaciones uno a muchos (User-Message).

### ¿Habéis usado conceptos avanzados como herencia, polimorfismo o interfaces? Explicad su aplicación.
Implementamos varios conceptos avanzados de POO:
- **Herencia**: Extendemos clases base de Django como ListView, DetailView, CreateView, UpdateView y DeleteView para personalizar su comportamiento.
- **Mixins**: Utilizamos el patrón mixin con StaffRequiredMixin para añadir funcionalidad de verificación de permisos a múltiples vistas.
- **Polimorfismo**: Sobrescribimos métodos como get_object(), get_form() y get_success_url() para personalizar el comportamiento de las vistas.
- **Señales**: Utilizamos señales de Django (post_save, m2m_changed) para ejecutar código cuando ocurren ciertos eventos, como crear un perfil automáticamente cuando se registra un usuario.

### ¿Habéis gestionado la información mediante archivos? ¿Usáis ficheros o interfaces gráficas para la interacción del usuario?
Gestionamos la información de varias formas:
- **Archivos estáticos**: CSS, JavaScript e imágenes para la interfaz de usuario.
- **Archivos de medios**: Almacenamos avatares de usuario y otros archivos subidos.
- **Archivos de configuración**: settings.py, urls.py para configurar el proyecto.
- **Interfaces gráficas**: Utilizamos plantillas HTML con Bootstrap para crear una interfaz web interactiva y responsive.
- **Formularios web**: Para la entrada de datos del usuario, utilizando el sistema de formularios de Django.

### ¿Qué estructuras de datos estáis utilizando (listas, matrices, colecciones)? ¿Por qué?
Utilizamos diversas estructuras de datos:
- **Listas**: Para almacenar y procesar colecciones ordenadas de elementos, como en la configuración de INSTALLED_APPS.
- **Diccionarios**: Para almacenar pares clave-valor, como en la configuración de DATABASES y TEMPLATES.
- **QuerySets**: Estructura específica de Django para representar consultas a la base de datos.
- **Modelos ORM**: Utilizamos el ORM de Django para abstraer las operaciones de base de datos y trabajar con objetos Python en lugar de SQL directo.

### ¿Habéis aplicado técnicas avanzadas como expresiones regulares o flujos de entrada/salida?
Implementamos técnicas avanzadas como:
- **Expresiones regulares**: En las URLs de Django para el enrutamiento de peticiones.
- **Flujos de entrada/salida**: Para la gestión de archivos subidos por el usuario, como imágenes de perfil.
- **AJAX**: Para la comunicación asíncrona en el sistema de mensajería.
- **Señales y eventos**: Para ejecutar código en respuesta a eventos específicos del sistema.

## Sistemas Informáticos

### ¿Qué características tiene el hardware donde se ejecuta vuestro desarrollo (Entorno de desarrollo y entorno de producción)?
**Entorno de desarrollo:**
- Sistema operativo: Windows 11 Pro
- Procesador: Intel i11
- Tarjeta gráfica: RTX 3090
- Memoria RAM: No especificada, pero suficiente para desarrollo web

**Entorno de producción:**
- Sistema operativo: Linux Server Ubuntu 24.04
- Configuración: Máquina virtual VPS 2
- CPU: 2 vCore
- RAM: 2 GB
- Almacenamiento: 80 GB NVMe SSD

### ¿Qué sistema operativo habéis seleccionado para vuestro entorno de desarrollo y producción? ¿Por qué?
**Entorno de desarrollo:**
- Windows 11 Pro: Seleccionado por su compatibilidad con las herramientas de desarrollo utilizadas y por ser el sistema operativo principal del equipo de desarrollo.

**Entorno de producción:**
- Ubuntu 24.04: Seleccionado por su estabilidad, seguridad y rendimiento para servidores web. Linux es ideal para servidores por su menor consumo de recursos y mejor gestión de conexiones concurrentes.

### ¿Cómo habéis configurado las redes para vuestro proyecto (tipo de red, protocolos usados, seguridad)?
**Entorno de desarrollo:**
- Red local mediante Ethernet o Wi-Fi
- Laragon configura un entorno local (localhost)
- Protocolos: TCP/IP, HTTP
- Seguridad basada en la red local

**Entorno de producción:**
- Aplicación accesible a través de Internet mediante HTTP/HTTPS
- Servidor configurado en un centro de datos con conectividad de alta velocidad
- Plesk gestiona la configuración de red (IP, DNS)
- Seguridad: Firewalls a nivel de servidor, configuraciones de seguridad (fail2ban, mod_security)
- HTTPS para conexión segura con certificado SSL/TLS

### ¿Habéis implementado sistemas de copias de seguridad? ¿Cuál es vuestra estrategia?
**Entorno de desarrollo:**
- Copias manuales o uso de herramientas de backup de Windows
- Control de versiones (Git) como forma de backup del código fuente

**Entorno de producción:**
- Servicios de backup proporcionados por el proveedor de hosting
- Backups automáticos programados de archivos y base de datos a nivel de servidor configurados a través de Plesk

### ¿Qué medidas habéis tomado para asegurar la integridad y seguridad de vuestros datos?
Implementamos varias medidas de seguridad:
- Autenticación de usuarios con contraseñas seguras
- Protección contra CSRF en formularios
- Validación de datos en el servidor
- Uso de HTTPS en producción
- Almacenamiento seguro de contraseñas mediante hashing
- Permisos restrictivos para archivos y directorios
- Separación de entornos de desarrollo y producción
- Configuración adecuada de DEBUG=False en producción

### ¿Cómo habéis configurado usuarios, permisos y accesos en el sistema operativo?
**Entorno de desarrollo:**
- Ejecución con los permisos del usuario de Windows que inicia Laragon

**Entorno de producción:**
- Plesk gestiona usuarios del sistema (FTP, SSH)
- Permisos de archivo/directorio configurados para el usuario bajo el cual se ejecuta el servidor web (www-data o usuario específico)
- Permisos configurados para permitir escritura en directorios específicos (chmod 755)

### ¿Habéis documentado la configuración técnica y la gestión del sistema informático?
La documentación técnica incluye:
- README.md: Instrucciones de instalación, configuración de BD y URL base
- CONEXIONES_BD.md: Esquema y consultas de base de datos
- MEMORIAS.md: Decisiones de diseño y cambios clave
- Documentación interna en el código

## Entornos de Desarrollo

### ¿Qué entorno de desarrollo (IDE) estáis utilizando y cómo lo habéis configurado?
Utilizamos Cursor como IDE principal, configurado con:
- Integración con Git para control de versiones
- Extensiones para Python y Django
- Integración con IA (ChatGPT y Claude) para asistencia en el desarrollo
- Resaltado de sintaxis para Python, HTML, CSS y JavaScript
- Autocompletado y sugerencias de código

### ¿Cómo automatizáis tareas en vuestro entorno de desarrollo?
Automatizamos tareas mediante:
- Comandos de Django (manage.py) para migraciones, creación de apps, etc.
- Scripts personalizados para tareas repetitivas
- Herramientas de Laragon para gestión de servidores locales
- Composer para gestión de dependencias PHP
- Tareas automatizadas de Git para control de versiones

### ¿Utilizáis control de versiones? ¿Qué plataforma (GitHub, GitLab, etc.)? ¿Cómo gestionáis versiones y ramas?
Utilizamos Git como sistema de control de versiones:
- Plataforma: GitHub para alojar repositorios
- Gestión de ramas: Rama principal (main/master) para código estable
- Ramas de características para desarrollo de nuevas funcionalidades
- Ramas de corrección para solucionar bugs
- Uso de pull requests para revisar código antes de fusionar

### ¿Qué estrategia seguís para refactorizar vuestro código?
Nuestra estrategia de refactorización incluye:
- Identificación de código duplicado para crear funciones o clases reutilizables
- Mejora de la legibilidad mediante nombres descriptivos y comentarios
- Optimización de consultas a la base de datos
- Aplicación de patrones de diseño cuando es apropiado
- Pruebas para asegurar que la refactorización no introduce errores

### ¿Cómo documentáis técnicamente el proyecto? ¿Utilizáis markdown, docstrings o herramientas específicas?
Documentamos el proyecto mediante:
- Archivos Markdown (.md) para documentación general
- Docstrings en Python para documentar clases y funciones
- Comentarios en el código para explicar secciones complejas
- README.md para instrucciones de instalación y uso
- Documentación específica en carpeta docs/

### ¿Habéis creado diagramas de clases o diagramas de comportamiento para modelar vuestra aplicación?
No se encontró evidencia específica de diagramas en el código revisado, pero el proyecto sigue la estructura estándar de Django que implícitamente define las relaciones entre modelos, vistas y plantillas.

## Bases de Datos

### ¿Qué sistema gestor de bases de datos habéis seleccionado (MySQL, SQLite, bases de datos no relacionales)? ¿Por qué?
Utilizamos SQLite para desarrollo por:
- Facilidad de configuración (no requiere servidor separado)
- Integración directa con Django
- Portabilidad (la base de datos es un único archivo)
- Adecuado para entornos de desarrollo con pocos usuarios concurrentes

Para producción, el proyecto está preparado para migrar a MySQL, que ofrece mejor rendimiento y concurrencia.

### ¿Cómo habéis diseñado el modelo entidad-relación?
El modelo entidad-relación incluye:
- **User**: Entidad para autenticación de usuarios (proporcionada por Django)
- **Profile**: Extensión de User con relación uno a uno
- **Page**: Entidad para páginas de contenido
- **Thread**: Entidad para conversaciones con relación muchos a muchos con User
- **Message**: Entidad para mensajes individuales con relación muchos a uno con User

Las relaciones están implementadas mediante el ORM de Django.

### ¿Usáis vistas, procedimientos almacenados, disparadores o funciones avanzadas? ¿Con qué objetivo?
No utilizamos procedimientos almacenados o disparadores a nivel de base de datos, sino que implementamos esta lógica en el código Python:
- Utilizamos señales de Django (similar a disparadores) para ejecutar código cuando ocurren ciertos eventos
- Implementamos managers personalizados (ThreadManager) para encapsular consultas complejas
- Utilizamos el ORM de Django para abstraer la lógica de base de datos

### ¿Implementáis mecanismos específicos para proteger y recuperar datos?
Implementamos varios mecanismos:
- Validación de datos en formularios antes de guardarlos
- Transacciones para operaciones que involucran múltiples cambios
- Backups automáticos en producción
- Control de acceso basado en autenticación y permisos
- Protección contra inyección SQL mediante el ORM de Django

## Lenguajes de Marcas y Sistemas de Gestión de Información

### ¿Cómo habéis estructurado vuestros documentos HTML? ¿Aplicáis buenas prácticas y estándares web?
Estructuramos nuestros documentos HTML siguiendo buenas prácticas:
- Uso de HTML5 semántico (header, nav, main, footer)
- Plantilla base (base.html) con bloques para contenido específico
- Separación de estructura (HTML), presentación (CSS) y comportamiento (JavaScript)
- Uso de etiquetas meta para SEO y responsividad
- Formularios con etiquetas label y validación

### ¿Qué tecnologías utilizáis para el frontend (CSS, JavaScript)? ¿Por qué esas tecnologías?
Utilizamos:
- **Bootstrap**: Para diseño responsive y componentes UI predefinidos
- **jQuery**: Para simplificar la manipulación del DOM y AJAX
- **CSS personalizado**: Para estilos específicos no cubiertos por Bootstrap
- **Font Awesome**: Para iconos vectoriales

Estas tecnologías fueron seleccionadas por su amplia adopción, documentación y facilidad de uso.

### ¿Utilizáis JavaScript para interactuar con el DOM?
Utilizamos JavaScript para:
- Validación de formularios en el lado del cliente
- Peticiones AJAX para el sistema de mensajería
- Manipulación del DOM para actualizar la interfaz sin recargar la página
- Integración con CKEditor 5 para el editor de texto enriquecido

### ¿Habéis validado vuestros documentos HTML y CSS?
No hay evidencia explícita de validación formal, pero el código sigue las convenciones de Bootstrap y Django, que generalmente producen HTML válido.

### ¿Habéis implementado la conversión de datos entre formatos (XML, JSON)? ¿Por qué?
Implementamos conversión de datos a JSON para:
- Respuestas AJAX en el sistema de mensajería (JsonResponse)
- Comunicación entre el frontend y backend
- Serialización de datos para la API

### ¿Vuestra aplicación interactúa con sistemas de gestión empresarial o herramientas específicas de almacenamiento y gestión documental? ¿O se puede considerar que vuestra aplicación es una aplicación de gestión empresarial? ¿De qué tipo?
Nuestra aplicación puede considerarse una plataforma social básica con elementos de gestión de contenidos:
- Sistema de gestión de usuarios y perfiles
- Sistema de mensajería interna
- Creación y gestión de páginas de contenido con editor WYSIWYG
- No interactúa directamente con sistemas externos de gestión empresarial

## Proyecto Intermodular

### ¿Qué objetivo cumple vuestro software?
WebPlayground es una plataforma social interactiva que permite a los usuarios:
- Registrarse y crear perfiles personalizados
- Comunicarse mediante un sistema de mensajería interna
- Crear y gestionar páginas de contenido con un editor de texto enriquecido
- Interactuar con otros usuarios de la plataforma

### ¿Qué necesidad cubre o qué problema soluciona?
El software soluciona:
- La necesidad de comunicación entre usuarios en un entorno controlado
- La creación y gestión de contenido personalizado
- La presentación de perfiles profesionales o personales
- La construcción de una comunidad en línea

### ¿Cuál es el stack de tecnologías que habéis elegido y por qué?
Nuestro stack tecnológico incluye:
- **Backend**: Python con Django 5.2 por su robustez, seguridad y rapidez de desarrollo
- **Frontend**: HTML5, CSS3, Bootstrap, jQuery para una interfaz responsive y moderna
- **Base de datos**: SQLite (desarrollo) / MySQL (producción) por su integración con Django
- **Editor**: CKEditor 5 para creación de contenido enriquecido
- **Despliegue**: Gunicorn/Waitress como servidores WSGI, Nginx como proxy inverso

Este stack fue elegido por su estabilidad, amplia documentación y capacidad para desarrollar aplicaciones web robustas de forma eficiente.

### ¿Cómo habéis planteado el desarrollo por versiones (versión 1 con funcionalidad mínima, actualizaciones, etc)?
El desarrollo se ha planteado de forma modular:
- **Versión inicial**: Core y sistema de autenticación básico
- **Ampliaciones**: Módulos de perfiles, páginas y mensajería
- **Mejoras**: Integración de CKEditor 5, optimización de la interfaz de usuario
- **Futuras actualizaciones**: Según documentación en MEMORIAS.md, se han planificado mejoras en el despliegue y estructura de carpetas
