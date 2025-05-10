# Documentación Técnica del Proyecto

## Programación

- **Elementos fundamentales del código**:
  - Variables: Utilizo variables para almacenar datos temporales en las vistas y plantillas (como `posts`, `services`, etc.).
  - Constantes: Implemento constantes en la configuración de Django (settings.py) como `MEDIA_URL`, `STATIC_URL`, etc.
  - Operadores: Empleo operadores de comparación en las plantillas para control de flujo y operadores lógicos en las vistas.
  - Tipos de datos: Trabajo con strings (CharField, TextField), números (SmallIntegerField), fechas (DateTimeField), booleanos, y tipos complejos como imágenes (ImageField) y URLs (URLField).

- **Estructuras de control utilizadas**:
  - Selección: Uso condicionales `if/else` en las plantillas para mostrar contenido dinámico según el contexto.
  - Repetición: Implemento bucles `for` para iterar sobre colecciones de objetos (posts, servicios, etc.).
  - Saltos: Utilizo redirecciones (`redirect`) en las vistas para manejar el flujo de navegación tras procesar formularios.

- **Control de excepciones**:
  - Implemento manejo de excepciones en el envío de emails con bloques try/except.
  - Utilizo `get_object_or_404` para manejar elegantemente los casos donde no se encuentra un objeto en la base de datos.

- **Documentación del código**:
  - Documento las funciones principales con docstrings explicando su propósito.
  - Incluyo comentarios en secciones críticas como el envío de emails.

- **Paradigma aplicado**:
  - Utilizo programación orientada a objetos, siguiendo el patrón MVT (Modelo-Vista-Plantilla) de Django.
  - Esta elección facilita la organización del código, la reutilización y el mantenimiento del proyecto.

- **Clases y objetos principales**:
  - Modelos: `Service`, `Post`, `Category`, `Page`, `Link` que representan las entidades del negocio.
  - Formularios: `ContactForm` para validación y procesamiento de datos de contacto.
  - Relaciones: Uso relaciones uno a muchos (ForeignKey) y muchos a muchos (ManyToManyField) entre modelos.

- **Conceptos avanzados OOP**:
  - Herencia: Los modelos heredan de `models.Model` y los formularios de `forms.Form`.
  - Polimorfismo: Implementado a través de métodos como `__str__` que se comportan según la clase.
  - Metaclases: Uso de la clase `Meta` en los modelos para configurar comportamientos específicos.

- **Gestión de información**:
  - Gestiono archivos para las imágenes subidas por el usuario.
  - Utilizo interfaces web para la interacción del usuario a través de formularios HTML y el panel de administración de Django.

- **Estructuras de datos**:
  - Colecciones: Uso QuerySets de Django para manejar colecciones de objetos de la base de datos.
  - Diccionarios: Empleo contextos en las vistas para pasar datos a las plantillas.
  - Listas: Implemento listas para manejar categorías y otros elementos relacionados.

- **Técnicas avanzadas**:
  - Expresiones regulares: Utilizadas implícitamente en las URLs de Django.
  - Flujos de entrada/salida: Manejo de archivos para imágenes y contenido estático.

## Sistemas Informáticos

- **Características del hardware**:
  - Entorno de desarrollo: Windows 11 Pro con procesador Intel i11, RTX 3090, que proporciona un rendimiento óptimo para el desarrollo.
  - Entorno de producción: Servidor Linux Ubuntu 24.04 con 2 vCores, 2GB RAM y 80GB NVMe SSD, configurado como máquina virtual VPS.

- **Sistema operativo seleccionado**:
  - Desarrollo: Windows 11 Pro por su interfaz amigable y compatibilidad con las herramientas de desarrollo.
  - Producción: Ubuntu Server 24.04 por su estabilidad, seguridad y eficiencia en entornos de servidor.

- **Configuración de redes**:
  - Tipo de red: TCP/IP sobre Internet para producción y red local para desarrollo.
  - Protocolos: HTTP/HTTPS para la comunicación web, con certificados SSL en producción.
  - Seguridad: Implemento HTTPS en producción y configuración de firewall en el servidor Ubuntu.

- **Sistemas de copias de seguridad**:
  - Desarrollo: Control de versiones Git como respaldo del código fuente.
  - Producción: Backups automáticos programados a través de Plesk para archivos y base de datos.

- **Medidas de seguridad de datos**:
  - Uso de HTTPS para la transmisión segura de datos.
  - Implementación de validación de formularios para prevenir inyecciones SQL.
  - Protección CSRF en formularios mediante los tokens de Django.
  - Almacenamiento seguro de contraseñas con hash en la base de datos.

- **Configuración de usuarios y permisos**:
  - Desarrollo: Ejecución con permisos del usuario de Windows que inicia Laragon.
  - Producción: Gestión de usuarios y permisos a través de Plesk, con configuración específica para archivos y directorios (chmod 755).

- **Documentación de configuración técnica**:
  - Documentación en README.md con instrucciones de instalación y configuración.
  - Archivos específicos como CONEXIONES_BD.md y MEMORIAS.md para aspectos concretos del proyecto.

## Entornos de Desarrollo

- **IDE utilizado**:
  - Cursor como editor de código principal, configurado con extensiones para Python, Django y linting.

- **Automatización de tareas**:
  - Uso de scripts como runserver.bat para iniciar el servidor de desarrollo.
  - Implementación de comandos de Django (manage.py) para tareas comunes.

- **Control de versiones**:
  - Utilizo Git para el control de versiones con repositorio en GitHub.
  - Gestiono ramas para separar características y correcciones.

- **Estrategia de refactorización**:
  - Organización del código en apps separadas según funcionalidad.
  - Uso de plantillas base y herencia para evitar duplicación de código HTML.

- **Documentación técnica**:
  - Uso de markdown para la documentación (README.md, MEMORIAS.md, CONEXIONES_BD.md).
  - Docstrings en funciones y métodos principales.

- **Diagramas**:
  - No se han encontrado diagramas específicos en el repositorio, pero la estructura sigue el patrón MVT de Django.

## Bases de Datos

- **Sistema gestor seleccionado**:
  - SQLite para desarrollo por su simplicidad y portabilidad.
  - Configuración preparada para migrar a MySQL en producción por su mejor rendimiento con múltiples conexiones.

- **Diseño del modelo entidad-relación**:
  - Entidades principales: Service, Post, Category, Page, Link.
  - Relaciones: Post-Category (muchos a muchos), Post-User (muchos a uno).

- **Funcionalidades avanzadas**:
  - No se implementan procedimientos almacenados o disparadores, delegando esta lógica al ORM de Django.
  - Uso del ORM para consultas complejas como filtrado por categorías.

- **Mecanismos de protección y recuperación**:
  - Validación de datos a nivel de modelo y formulario.
  - Backups automáticos configurados en el servidor de producción.

## Lenguajes de Marcas y Sistemas de Gestión de Información

- **Estructura de documentos HTML**:
  - Implemento HTML5 semántico con estructura clara de cabecera, navegación, secciones y pie de página.
  - Aplico buenas prácticas como la separación de contenido y presentación.

- **Tecnologías frontend**:
  - CSS: Utilizo Bootstrap para un diseño responsive y consistente.
  - JavaScript: Implemento jQuery para interacciones básicas y Bootstrap JS para componentes dinámicos.

- **Interacción con el DOM**:
  - Uso JavaScript para la validación de formularios y efectos visuales.
  - Implemento eventos para mejorar la experiencia de usuario.

- **Validación de documentos**:
  - Las plantillas HTML siguen los estándares de HTML5.
  - El CSS cumple con las especificaciones de CSS3.

- **Conversión de datos entre formatos**:
  - Uso de JSON para las respuestas AJAX en formularios.
  - Implementación de serializadores para la conversión de modelos a JSON.

- **Interacción con sistemas de gestión empresarial**:
  - La aplicación es un sistema de gestión empresarial tipo CMS (Content Management System) para cafeterías.
  - Permite gestionar contenidos, servicios, blog y contacto desde un panel de administración centralizado.

## Proyecto Intermodular

- **Objetivo del software**:
  - Crear una web corporativa para una cafetería que permita gestionar y mostrar servicios, blog y páginas dinámicas.

- **Necesidad que cubre**:
  - Proporciona presencia online profesional para negocios de hostelería.
  - Facilita la comunicación con clientes a través del formulario de contacto.
  - Permite actualizar contenidos sin conocimientos técnicos mediante el panel de administración.

- **Stack tecnológico elegido**:
  - Backend: Python con Django 5.2 por su robustez, seguridad y rapidez de desarrollo.
  - Frontend: HTML5, CSS3 con Bootstrap para diseño responsive.
  - Base de datos: SQLite en desarrollo, preparado para MySQL en producción.
  - Despliegue: Gunicorn/Waitress como servidores WSGI, Nginx como proxy inverso.

- **Desarrollo por versiones**:
  - Versión 1: Implementación de funcionalidades básicas (páginas estáticas, servicios).
  - Versión 2: Adición de blog y categorías.
  - Versión 3: Implementación de páginas dinámicas con editor CKEditor.
  - Versión 4: Integración de formulario de contacto con envío de emails.
  - Versión actual: Optimización para producción con configuración de archivos estáticos y media.
