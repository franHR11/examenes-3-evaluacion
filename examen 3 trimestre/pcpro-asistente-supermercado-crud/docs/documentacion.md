# Documentación Técnica del Proyecto PCpro Asistente IA Supermercado

## Programación

- **Elementos fundamentales del código**: 
  - Variables: `userId`, `myMessage`, `productoEnConstruccion`, `esperandoCampo`, etc.
  - Constantes: `PORT`, `PRODUCTOS_JSON`, `messagesContainer`, etc.
  - Operadores: aritméticos (+, -, *, /), comparación (==, ===, !=, !==), lógicos (&&, ||, !), ternarios.
  - Tipos de datos: strings, números, booleanos, arrays, objetos, JSON, promesas.

- **Estructuras de control utilizadas**:
  - Selección: `if/else` para validaciones de datos y control de flujo, operador ternario para asignaciones condicionales.
  - Repetición: `for`, `forEach` para iterar sobre arrays, `while` para esperar respuestas de la API de OpenAI.
  - Saltos: `return` para terminar funciones y manejar casos especiales.

- **Control de excepciones**:
  - Bloques `try/catch` en todas las funciones asíncronas para capturar errores de red, API y procesamiento.
  - Gestión de errores mediante respuestas HTTP con códigos de estado (404, 500) y mensajes descriptivos.
  - Timeouts para manejar casos de no respuesta del servidor.

- **Documentación del código**:
  - Comentarios descriptivos en cada sección principal del código.
  - Explicaciones detalladas de funcionalidades complejas.
  - Docstrings para explicar el propósito de funciones y variables importantes.

- **Paradigma aplicado**:
  - Programación orientada a objetos para la estructura general.
  - Programación funcional para operaciones de datos (map, filter, reduce).
  - Elegido por su claridad, mantenibilidad y adecuación a aplicaciones web modernas con JavaScript.

- **Clases y objetos principales**:
  - Objetos para representar productos con propiedades como id, nombre, marca, precio, cantidadEnStock.
  - Objetos para manejar respuestas HTTP y mensajes de la API.
  - Relación cliente-servidor mediante API REST.

- **Conceptos avanzados**:
  - No se implementa herencia explícita, pero sí composición de objetos.
  - Polimorfismo implícito en el manejo de diferentes tipos de mensajes y respuestas.
  - Interfaces REST para comunicación entre frontend y backend.

- **Gestión de información**:
  - Archivos JSON para almacenamiento persistente de productos.
  - Interfaz gráfica web para interacción del usuario mediante HTML, CSS y JavaScript.
  - API REST para operaciones CRUD.

- **Estructuras de datos utilizadas**:
  - Arrays para almacenar colecciones de productos y mensajes.
  - Objetos para representar entidades y configuraciones.
  - JSON como formato de intercambio de datos y almacenamiento.
  - Elegidas por su simplicidad, eficiencia y compatibilidad con JavaScript y API REST.

- **Técnicas avanzadas aplicadas**:
  - Expresiones regulares para validación y extracción de datos de mensajes de usuario.
  - Flujos de entrada/salida asíncronos con Promises y async/await.
  - Manejo de eventos del DOM para interactividad.
  - Fetch API para comunicación HTTP.

## Sistemas Informáticos

- **Características del hardware**:
  - Entorno de desarrollo: Windows 11 Pro, Intel i11, RTX 3090.
  - Entorno de producción: VPS con 2 vCore CPU, 2GB RAM, 80GB NVMe SSD.

- **Sistema operativo seleccionado**:
  - Desarrollo: Windows 11 Pro por compatibilidad con herramientas de desarrollo y familiaridad.
  - Producción: Linux Server Ubuntu 24.04 por estabilidad, seguridad y rendimiento en servidores web.

- **Configuración de redes**:
  - Desarrollo: Red local con Laragon configurando entorno localhost.
  - Producción: Servidor accesible vía HTTP/HTTPS, con conectividad de alta velocidad.
  - Protocolos: TCP/IP, HTTP/HTTPS.
  - Seguridad: Firewall a nivel de servidor, configuraciones de seguridad gestionadas por Plesk.

- **Sistemas de copias de seguridad**:
  - Desarrollo: Control de versiones Git como backup del código fuente.
  - Producción: Servicios de backup automáticos programados a través de Plesk.

- **Medidas para asegurar integridad y seguridad de datos**:
  - Variables de entorno para proteger claves API (OpenAI).
  - Validación de datos en frontend y backend.
  - Manejo de errores y excepciones para prevenir fallos.
  - Certificados SSL/TLS para conexiones seguras en producción.

- **Configuración de usuarios, permisos y accesos**:
  - Desarrollo: Ejecución con permisos del usuario de Windows que inicia Laragon.
  - Producción: Gestión de usuarios del sistema (FTP, SSH) y permisos de archivo/directorio a través de Plesk.

- **Documentación de configuración técnica**:
  - README.md con instrucciones de instalación y configuración.
  - CONEXIONES_BD.md con esquema y consultas de base de datos.
  - MEMORIAS.md con decisiones de diseño y actualizaciones.

## Entornos de Desarrollo

- **Entorno de desarrollo utilizado**:
  - IDE principal: Cursor.
  - Configurado con extensiones para JavaScript, Node.js y herramientas de depuración.

- **Automatización de tareas**:
  - Scripts NPM en package.json para iniciar el servidor y otras tareas.
  - Nodemon para reinicio automático del servidor durante desarrollo.

- **Control de versiones**:
  - Git para control de versiones local.
  - GitHub como plataforma de repositorio remoto.
  - Gestión de versiones mediante commits descriptivos.
  - Ramas para desarrollo de nuevas características.

- **Estrategia de refactorización**:
  - Mejora continua del código con comentarios descriptivos.
  - Separación de responsabilidades en funciones específicas.
  - Validación de datos en puntos críticos.

- **Documentación técnica**:
  - Markdown para documentación general (README.md, CONEXIONES_BD.md, MEMORIAS.md).
  - Comentarios en código para explicar funcionalidades complejas.
  - Docstrings para funciones importantes.

- **Diagramas**:
  - No se encontraron diagramas de clases o comportamiento explícitos en el repositorio.

## Bases de Datos

- **Sistema gestor de bases de datos seleccionado**:
  - JSON como almacenamiento de datos simple.
  - Elegido por su simplicidad, portabilidad y adecuación para proyectos pequeños sin necesidad de configuración compleja.

- **Diseño del modelo entidad-relación**:
  - Entidad principal: Producto con atributos id, nombre, marca, precio, cantidadEnStock.
  - Relaciones no implementadas al ser un modelo de datos simple.

- **Uso de vistas, procedimientos almacenados, disparadores o funciones avanzadas**:
  - No se implementan al usar JSON como almacenamiento.
  - Lógica de consulta y agregación implementada en el código JavaScript.

- **Mecanismos para proteger y recuperar datos**:
  - Validación de datos antes de escritura.
  - Control de errores en operaciones de lectura/escritura.
  - Control de versiones Git como respaldo del archivo JSON.

## Lenguajes de Marcas y Sistemas de Gestión de Información

- **Estructura de documentos HTML**:
  - HTML5 semántico con elementos como header, section, div.
  - Buenas prácticas: metadatos completos, estructura jerárquica clara, separación de contenido y presentación.

- **Tecnologías frontend utilizadas**:
  - CSS3 para estilos y diseño responsive.
  - JavaScript para interactividad y comunicación con el backend.
  - FontAwesome para iconos.
  - Chart.js para gráficos.
  - Elegidas por su amplia adopción, compatibilidad y capacidades modernas.

- **Uso de JavaScript para interactuar con el DOM**:
  - Manipulación dinámica de elementos HTML.
  - Gestión de eventos (click, keypress).
  - Actualización de contenido en tiempo real.
  - Animaciones y efectos visuales (loaders).

- **Validación de documentos HTML y CSS**:
  - Implementación de HTML5 válido.
  - CSS organizado y modular.

- **Conversión de datos entre formatos**:
  - JSON como formato principal para intercambio de datos entre frontend y backend.
  - Conversión entre objetos JavaScript y JSON mediante JSON.parse() y JSON.stringify().

- **Interacción con sistemas de gestión empresarial**:
  - La aplicación es un sistema de gestión empresarial para inventario de supermercados.
  - Tipo: Sistema de gestión de inventario con asistente IA.

## Proyecto Intermodular

- **Objetivo del software**:
  - Proporcionar una solución web inteligente para gestionar productos e inventario en supermercados.
  - Facilitar operaciones CRUD mediante interfaz chat con IA y botones directos.

- **Necesidad cubierta o problema solucionado**:
  - Agiliza la administración de productos en supermercados.
  - Reduce errores en la gestión de inventario.
  - Mejora la eficiencia diaria sin requerir conocimientos técnicos avanzados.
  - Facilita la digitalización para pequeñas y medianas cadenas.

- **Stack de tecnologías elegido**:
  - Backend: Node.js, Express, OpenAI API.
  - Frontend: HTML5, CSS3, JavaScript.
  - Almacenamiento: JSON.
  - Herramientas: Nodemon, dotenv, Chart.js.
  - Elegido por su simplicidad, eficiencia, bajo coste de implementación y adecuación para aplicaciones web modernas.

- **Desarrollo por versiones**:
  - Versión 1: Implementación CRUD básica y chat asistente.
  - Actualizaciones (22/04/2025): 
    - Implementación de endpoints REST y gráficos.
    - Validación y flujo conversacional mejorado para alta de productos.
    - Botones flotantes CRUD para mejorar la experiencia de usuario.
