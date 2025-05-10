# Documentación Técnica del Proyecto

## Programación

- **Elementos fundamentales del código**: 
  - Variables: Utilizo variables para almacenar elementos del DOM (`generateBtn`, `avatarBox`, `loading`, `categorySelector`), valores seleccionados (`category`), respuestas de la API (`response`, `data`) y URLs de imágenes (`imageUrl`).
  - Constantes: Defino constantes para elementos que no cambian como el puerto del servidor (`PORT`) y la instancia de Express (`app`).
  - Operadores: Implemento operadores aritméticos, de asignación, lógicos y de comparación. Por ejemplo, uso el operador lógico OR (`||`) para establecer valores por defecto: `const PORT = process.env.PORT || 3000`.
  - Tipos de datos: Trabajo con strings para prompts y URLs, números para el puerto, booleanos para condiciones, objetos para respuestas de la API y arrays para almacenar datos.

- **Estructuras de control**:
  - Selección: Utilizo estructuras condicionales `if-else` para validar si la respuesta de la API contiene una URL de imagen válida y mostrar el resultado correspondiente.
  - Repetición: No he necesitado bucles explícitos ya que el proyecto se basa en eventos y peticiones asíncronas.
  - Saltos: Implemento saltos implícitos mediante el manejo de eventos y callbacks.

- **Control de excepciones**: 
  - Implemento bloques `try-catch-finally` tanto en el frontend como en el backend para capturar y manejar errores durante las peticiones a la API de OpenAI.
  - En el backend, capturo excepciones y devuelvo respuestas con código de estado 500 y mensajes de error descriptivos.
  - En el frontend, muestro alertas al usuario y mensajes en la consola cuando ocurren errores.

- **Documentación del código**: 
  - Documento el código con comentarios descriptivos que explican la funcionalidad de cada sección.
  - Utilizo bloques JSDoc al inicio de los archivos con etiquetas como `@fileoverview` y `@author`.
  - Añado comentarios en línea para explicar partes específicas del código, como la estructura de la respuesta de la API.

- **Paradigma aplicado**: 
  - Aplico principalmente programación estructurada con elementos de programación orientada a eventos.
  - Elijo este enfoque por su simplicidad y adecuación para una aplicación web pequeña donde la interacción del usuario se basa en eventos (clicks).

- **Clases y objetos principales**: 
  - No implemento clases explícitas ya que el proyecto es relativamente simple.
  - Trabajo con objetos nativos como el objeto `response` de fetch y el objeto JSON de la respuesta de la API.

- **Conceptos avanzados (herencia, polimorfismo, interfaces)**: 
  - No aplico estos conceptos avanzados debido a la naturaleza sencilla de la aplicación.

- **Gestión de información mediante archivos**: 
  - No utilizo archivos para almacenar datos persistentes; toda la información se procesa en memoria.
  - La interacción del usuario se realiza a través de una interfaz gráfica web con elementos HTML como botones, selectores y contenedores de imágenes.

- **Estructuras de datos**: 
  - Utilizo objetos JSON para estructurar las peticiones a la API y procesar las respuestas.
  - Trabajo con el DOM como estructura de datos para manipular elementos HTML.

- **Técnicas avanzadas**: 
  - Implemento promesas y async/await para manejar operaciones asíncronas como las peticiones fetch.
  - Utilizo flujos de entrada/salida para la comunicación con la API externa.

## Sistemas Informáticos

- **Características del hardware**:
  - Entorno de desarrollo: Windows 11 Pro con procesador Intel i11, tarjeta gráfica RTX 3090.
  - Entorno de producción: Máquina virtual Linux Server Ubuntu 24.04 con 2 vCore CPU, 2 GB RAM y 80 GB NVMe SSD.

- **Sistema operativo seleccionado**:
  - Desarrollo: Windows 11 Pro por su interfaz amigable, amplia compatibilidad con herramientas de desarrollo y facilidad de uso.
  - Producción: Linux Server Ubuntu 24.04 por su estabilidad, seguridad, bajo consumo de recursos y optimización para servidores web.

- **Configuración de redes**:
  - Tipo de red: En desarrollo uso una red local mediante Ethernet o Wi-Fi. En producción, la aplicación es accesible a través de Internet.
  - Protocolos: Utilizo HTTP/HTTPS para la comunicación entre cliente y servidor, y TCP/IP como protocolo base.
  - Seguridad: En desarrollo confío en la seguridad de la red local. En producción implemento HTTPS con certificado SSL/TLS, firewalls a nivel de servidor y configuraciones de seguridad gestionadas por Plesk.

- **Sistemas de copias de seguridad**:
  - En desarrollo: Utilizo Git como sistema de control de versiones que funciona como backup del código fuente.
  - En producción: Implemento backups automáticos programados de archivos y base de datos a nivel de servidor a través de Plesk.

- **Medidas para asegurar integridad y seguridad de datos**:
  - Uso variables de entorno (.env) para proteger información sensible como claves API.
  - Implemento el archivo .gitignore para evitar subir información confidencial al repositorio.
  - Aplico HTTPS en producción para cifrar la comunicación entre cliente y servidor.

- **Configuración de usuarios y permisos**:
  - En desarrollo (Windows): Ejecuto la aplicación con los permisos del usuario de Windows que inicia Laragon.
  - En producción (Linux/Plesk): Gestiono usuarios del sistema (FTP, SSH) y permisos de archivo/directorio para el usuario bajo el cual se ejecuta el servidor web.

- **Documentación de configuración técnica**:
  - Documento la configuración en README.md con instrucciones de instalación y configuración.
  - Mantengo archivos específicos como CONEXIONES_BD.md para esquemas de base de datos y MEMORIAS.md para decisiones de diseño.

## Entornos de Desarrollo

- **Entorno de desarrollo (IDE)**:
  - Utilizo Cursor como editor de código principal por su integración con IA, lo que agiliza el desarrollo.
  - Lo configuro con extensiones para JavaScript, Node.js y control de versiones Git.

- **Automatización de tareas**:
  - Implemento scripts en package.json para automatizar el inicio del servidor con diferentes configuraciones.
  - Utilizo npm para gestionar dependencias y ejecutar tareas como la instalación de paquetes.

- **Control de versiones**:
  - Utilizo Git como sistema de control de versiones y GitHub como plataforma para alojar el repositorio.
  - Gestiono versiones mediante commits descriptivos y ramas para desarrollar nuevas funcionalidades.

- **Estrategia de refactorización**:
  - Identifico y corrijo bugs, como el problema con el indicador de carga que desaparecía.
  - Mejoro la estructura del código separando claramente el frontend y backend.
  - Optimizo el rendimiento y la legibilidad del código mediante comentarios descriptivos.

- **Documentación técnica**:
  - Utilizo archivos markdown (README.md, CONEXIONES_BD.md, MEMORIAS.md) para documentar diferentes aspectos del proyecto.
  - Implemento comentarios JSDoc en el código para documentar funciones y archivos.

- **Diagramas**:
  - No he creado diagramas específicos para este proyecto debido a su simplicidad.

## Bases de Datos

- **Sistema gestor de bases de datos seleccionado**:
  - Actualmente no utilizo una base de datos en este proyecto. Toda la funcionalidad se basa en conexiones a la API de OpenAI y procesamiento en memoria.
  - En el archivo CONEXIONES_BD.md se plantean posibles implementaciones futuras con MongoDB (NoSQL) o MySQL/PostgreSQL (relacionales).

- **Diseño del modelo entidad-relación**:
  - No aplica actualmente, pero en CONEXIONES_BD.md se propone un posible esquema con tablas de usuarios, traducciones y configuraciones.

- **Vistas, procedimientos almacenados, disparadores o funciones avanzadas**:
  - No aplica actualmente al no utilizar base de datos.

- **Mecanismos para proteger y recuperar datos**:
  - No aplica actualmente al no utilizar base de datos.

## Lenguajes de Marcas y Sistemas de Gestión de Información

- **Estructura de documentos HTML**:
  - Estructuro el HTML siguiendo estándares web con la declaración DOCTYPE, metadatos en el head y contenido semántico en el body.
  - Aplico buenas prácticas como el uso de elementos semánticos (section, h1) y atributos lang para accesibilidad.

- **Tecnologías para el frontend**:
  - HTML5 para la estructura básica de la página.
  - CSS3 para el diseño y estilo, con un enfoque moderno que incluye variables CSS y media queries.
  - JavaScript vanilla para la interactividad, evitando dependencias innecesarias.

- **JavaScript para interactuar con el DOM**:
  - Utilizo JavaScript para seleccionar elementos del DOM (querySelector), añadir event listeners y modificar contenido dinámicamente.
  - Implemento la actualización dinámica de la interfaz al recibir la imagen generada.

- **Validación de documentos HTML y CSS**:
  - El código HTML sigue la estructura estándar y utiliza elementos semánticos.
  - El CSS implementa un reset moderno y utiliza variables para mantener consistencia.

- **Conversión de datos entre formatos**:
  - Convierto datos entre formatos utilizando JSON.stringify() para enviar datos al servidor y response.json() para procesar las respuestas.
  - Esto es necesario para la comunicación con la API de OpenAI que utiliza formato JSON.

- **Interacción con sistemas de gestión empresarial**:
  - La aplicación no interactúa directamente con sistemas de gestión empresarial.
  - Puede considerarse una aplicación de gestión de contenido digital, específicamente para la generación de imágenes con IA.

## Proyecto Intermodular

- **Objetivo del software**:
  - Crear una aplicación web que permita generar avatares únicos en estilo cartoon utilizando inteligencia artificial.

- **Necesidad que cubre**:
  - Facilita la creación rápida de imágenes personalizadas sin necesidad de habilidades de diseño.
  - Soluciona el problema de acceso a herramientas de diseño complejas para usuarios sin conocimientos técnicos.

- **Stack de tecnologías elegido**:
  - Frontend: HTML5, CSS3, JavaScript vanilla.
  - Backend: Node.js, Express.js.
  - API: OpenAI DALL-E 2.
  - Gestión de entorno: dotenv.
  - He elegido estas tecnologías por su simplicidad, eficiencia y capacidad para crear una aplicación web funcional con pocas dependencias.

- **Desarrollo por versiones**:
  - Versión 1 (actual): Funcionalidad básica de generación de imágenes por categorías.
  - Futuras mejoras planeadas según MEMORIAS.md: implementación de más opciones de personalización, sistema de cuentas de usuario y mejoras en el diseño responsive.
