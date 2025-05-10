# Documentación Técnica - PCPro App Peluquería

## Programación

- **Elementos fundamentales del código**:
  - Variables: Utilizamos variables para almacenar datos temporales y persistentes como `$nombre`, `$precio`, `$duracion`, `$fecha`, `$hora`.
  - Constantes: Definimos constantes como `URL_BASE` para mantener valores inmutables en toda la aplicación.
  - Operadores: Implementamos operadores aritméticos (+, -, *, /), de comparación (==, ===, !=, <, >), lógicos (&&, ||) y el operador de fusión de null (??) para asignar valores predeterminados.
  - Tipos de datos: Trabajamos con strings para nombres y textos, integers para IDs y duraciones, decimales para precios, booleanos para estados, arrays para colecciones de datos y objetos para entidades complejas.

- **Estructuras de control utilizadas**:
  - Selección: Usamos `if/else` para validaciones de formularios y control de acceso, y operadores ternarios para asignaciones condicionales compactas.
  - Repetición: Implementamos bucles `foreach` para iterar sobre colecciones de servicios, citas y configuraciones, y `for` para generar intervalos de tiempo disponibles.
  - Saltos: Utilizamos `return` para finalizar funciones y `header()` para redirecciones tras operaciones CRUD.

- **Control de excepciones**:
  - Implementamos un sistema de alertas para gestionar errores de validación en formularios.
  - Utilizamos validaciones preventivas antes de realizar operaciones críticas como guardar citas.
  - Verificamos la disponibilidad de horarios antes de permitir reservas para evitar conflictos.
  - Sanitizamos los datos de entrada mediante la función `s()` para prevenir inyecciones.

- **Documentación del código**:
  - Incluimos comentarios descriptivos para explicar la funcionalidad de métodos complejos como `comprobarDisponibilidad()` y `obtenerHorariosDisponibles()`.
  - Documentamos la estructura de la base de datos en `CONEXIONES_BD.md`.
  - Registramos decisiones de diseño importantes en `MEMORIAS.md`.
  - Agregamos comentarios en secciones críticas del código para facilitar su mantenimiento.

- **Paradigma aplicado**:
  - Utilizamos programación orientada a objetos para organizar el código de forma modular y reutilizable.
  - Elegimos este paradigma porque facilita el mantenimiento del código, permite la reutilización mediante herencia y proporciona una estructura clara para representar entidades del negocio.

- **Clases y objetos principales**:
  - `ActiveRecord`: Clase base abstracta que implementa operaciones CRUD genéricas.
  - `Servicio`: Representa los servicios ofrecidos por la peluquería con propiedades como nombre, precio y duración.
  - `Cita`: Gestiona las reservas de clientes con fecha, hora y duración.
  - `Usuario`: Maneja la información de clientes y administradores.
  - `Router`: Controla el enrutamiento de peticiones HTTP.
  - Estas clases se relacionan mediante composición (Cita contiene Servicios) y herencia (todos los modelos extienden ActiveRecord).

- **Conceptos avanzados**:
  - Herencia: Todos los modelos extienden la clase `ActiveRecord` para heredar funcionalidad CRUD.
  - Polimorfismo: Sobrescribimos métodos como `validar()` en cada modelo para implementar validaciones específicas.
  - Interfaces implícitas: Cada modelo implementa una estructura común definida por `ActiveRecord`.

- **Gestión de información**:
  - Utilizamos una base de datos MySQL para almacenamiento persistente.
  - Implementamos interfaces gráficas web para la interacción del usuario mediante HTML, CSS y JavaScript.
  - Utilizamos archivos de configuración para mantener parámetros del sistema.

- **Estructuras de datos**:
  - Arrays asociativos para manejar datos de formularios y resultados de consultas.
  - Objetos para representar entidades del negocio.
  - Colecciones de objetos para listar servicios, citas y usuarios.
  - Elegimos estas estructuras por su flexibilidad y facilidad de manipulación en PHP.

- **Técnicas avanzadas**:
  - Expresiones regulares para validación de datos como emails y teléfonos.
  - Flujos de entrada/salida para la gestión de peticiones HTTP y respuestas JSON en la API.
  - Buffer de salida (ob_start/ob_get_clean) para renderizar vistas.

## Sistemas Informáticos

- **Características del hardware**:
  - Entorno de desarrollo: Windows 11 Pro con procesador Intel i11, tarjeta gráfica RTX 3090, memoria RAM suficiente para ejecutar entornos virtuales y servidores locales.
  - Entorno de producción: Servidor Linux Ubuntu 24.04 con 2 vCore CPU, 2GB RAM, 80GB NVMe SSD, configurado como máquina virtual VPS.

- **Sistema operativo seleccionado**:
  - Desarrollo: Windows 11 Pro por su compatibilidad con las herramientas de desarrollo utilizadas y por ser el sistema operativo principal del equipo de desarrollo.
  - Producción: Linux Ubuntu 24.04 por su estabilidad, seguridad, rendimiento optimizado para servidores web y bajo consumo de recursos.

- **Configuración de redes**:
  - Tipo de red: En desarrollo utilizamos red local Ethernet/Wi-Fi. En producción, la aplicación es accesible a través de Internet.
  - Protocolos: HTTP/HTTPS para la comunicación web, TCP/IP como protocolo base.
  - Seguridad: En desarrollo, seguridad basada en la red local. En producción, implementamos HTTPS con certificados SSL/TLS, firewalls a nivel de servidor y configuraciones de seguridad gestionadas por Plesk.

- **Sistemas de copias de seguridad**:
  - En desarrollo: Control de versiones Git como respaldo del código fuente y copias manuales.
  - En producción: Backups automáticos programados de archivos y base de datos configurados a través de Plesk.

- **Medidas para asegurar integridad y seguridad**:
  - Sanitización de datos de entrada para prevenir inyecciones SQL y XSS.
  - Encriptación de contraseñas con hash seguro.
  - Validación de sesiones para control de acceso.
  - Confirmación de cuentas por email para verificar identidad.
  - Separación de roles entre usuarios y administradores.

- **Configuración de usuarios y permisos**:
  - En desarrollo: Ejecución bajo el usuario de Windows que inicia Laragon.
  - En producción: Gestión de usuarios del sistema (FTP, SSH) y permisos de archivo/directorio a través de Plesk para el usuario bajo el cual se ejecuta el servidor web.
  - Permisos configurados para permitir escritura en directorios específicos (chmod 755).

- **Documentación de configuración técnica**:
  - Documentación en README.md con instrucciones de instalación.
  - CONEXIONES_BD.md con esquema detallado de la base de datos.
  - MEMORIAS.md con decisiones de diseño y cambios importantes.
  - Instalacion.md con instrucciones específicas de configuración.

## Entornos de Desarrollo

- **Entorno de desarrollo utilizado**:
  - IDE principal: Cursor como editor de código.
  - Configuración: Extensiones para PHP, JavaScript, HTML y CSS, con linting y formateo automático.
  - Servidor local: Laragon configurado con Apache y MySQL para simular el entorno de producción.

- **Automatización de tareas**:
  - Utilizamos Gulp para automatizar la compilación de SCSS a CSS y la optimización de JavaScript.
  - NPM para gestionar dependencias y scripts de desarrollo.
  - Composer para gestionar dependencias PHP.

- **Control de versiones**:
  - Utilizamos Git como sistema de control de versiones.
  - Plataforma: GitHub para almacenar el repositorio remoto.
  - Gestión: Trabajamos con ramas para desarrollo de funcionalidades y corrección de errores, fusionándolas a la rama principal cuando están listas.

- **Estrategia de refactorización**:
  - Identificamos código duplicado y lo extraemos a métodos reutilizables.
  - Aplicamos principios SOLID, especialmente responsabilidad única.
  - Mejoramos nombres de variables y métodos para mayor claridad.
  - Implementamos pruebas manuales después de cada refactorización.

- **Documentación técnica**:
  - Utilizamos Markdown para la documentación del proyecto (README.md, CONEXIONES_BD.md, MEMORIAS.md).
  - Comentarios en el código para explicar funcionalidad compleja.
  - Documentación de la API para endpoints disponibles.

- **Diagramas**:
  - No se encontraron diagramas explícitos en el código revisado, pero la estructura de clases sigue un patrón MVC claramente definido.

## Bases de Datos

- **Sistema gestor de bases de datos**:
  - Seleccionamos MySQL por su robustez, amplia adopción, buen rendimiento y compatibilidad con PHP.
  - Complementamos con SQLite para algunas funcionalidades locales por su ligereza.

- **Diseño del modelo entidad-relación**:
  - Entidades principales: usuarios, servicios, citas, citasservicios y configuracion.
  - Relaciones: usuarios tienen citas, citas contienen servicios mediante la tabla intermedia citasservicios.
  - Claves primarias y foráneas correctamente definidas para mantener la integridad referencial.

- **Elementos avanzados**:
  - No se identificaron vistas o procedimientos almacenados explícitos, pero se utilizan consultas SQL complejas desde el código PHP.
  - La tabla configuracion implementa un sistema flexible de clave-valor para almacenar parámetros del sistema.
  - Utilizamos timestamps para registrar creación y actualización de configuraciones.

- **Mecanismos de protección y recuperación**:
  - Sanitización de datos antes de inserción para prevenir inyecciones SQL.
  - Backups automáticos configurados en el entorno de producción.
  - Transacciones implícitas para operaciones críticas.

## Lenguajes de Marcas y Sistemas de Gestión de Información

- **Estructura de documentos HTML**:
  - Implementamos una estructura semántica con elementos como header, nav, main, section y footer.
  - Separamos la presentación del contenido mediante plantillas (layout.php, templates).
  - Seguimos estándares web actuales con doctype HTML5.

- **Tecnologías frontend**:
  - CSS: Utilizamos SCSS como preprocesador para una mejor organización y mantenimiento del código.
  - JavaScript: Implementamos funcionalidad interactiva para la selección de servicios y horarios.
  - Elegimos estas tecnologías por su universalidad, potencia y facilidad de mantenimiento.

- **Interacción con el DOM**:
  - Utilizamos JavaScript para manipular dinámicamente el contenido de la página.
  - Implementamos eventos para responder a acciones del usuario como selección de servicios y fechas.
  - Realizamos peticiones asíncronas (fetch) para comunicarnos con la API sin recargar la página.

- **Validación de documentos**:
  - No se encontró evidencia explícita de validación formal de HTML y CSS, pero el código sigue prácticas estándar.

- **Conversión de datos entre formatos**:
  - Implementamos conversión entre PHP y JSON para la comunicación con la API.
  - Utilizamos JSON para transmitir datos de servicios, horarios disponibles y resultados de operaciones.

- **Interacción con sistemas de gestión empresarial**:
  - La aplicación es en sí misma un sistema de gestión empresarial para peluquerías.
  - Tipo: Sistema de gestión de citas y servicios para pequeños negocios del sector de belleza y peluquería.
  - Incluye gestión de clientes, servicios, reservas y configuración del negocio.

## Proyecto Intermodular

- **Objetivo del software**:
  - Crear un sistema de gestión de citas para peluquerías que permita a los clientes reservar servicios online y a los administradores gestionar el negocio eficientemente.

- **Necesidad cubierta**:
  - Soluciona el problema de gestión manual de citas, reduciendo errores y optimizando el tiempo.
  - Mejora la experiencia del cliente al permitir reservas online 24/7.
  - Proporciona a los administradores una visión clara de la agenda y ocupación.

- **Stack de tecnologías elegido**:
  - Backend: PHP con arquitectura MVC para una estructura organizada y mantenible.
  - Frontend: HTML5, SCSS/CSS3, JavaScript para una interfaz moderna y responsive.
  - Base de datos: MySQL para almacenamiento robusto de datos.
  - Herramientas: Composer para dependencias PHP, NPM y Gulp para frontend.
  - Elegimos este stack por su madurez, amplia documentación, facilidad de despliegue y rendimiento.

- **Desarrollo por versiones**:
  - Versión 1: Funcionalidad básica de registro de usuarios, gestión de servicios y reserva de citas.
  - Actualizaciones: Implementación de sistema de URL base para compatibilidad entre entornos, mejoras en la gestión de horarios disponibles y optimización del cálculo de duración de servicios.
  - Futuras versiones: Podrían incluir notificaciones por email/SMS, sistema de fidelización y estadísticas avanzadas.
