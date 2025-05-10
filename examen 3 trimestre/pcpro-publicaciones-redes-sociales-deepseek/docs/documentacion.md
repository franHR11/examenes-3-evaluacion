# Documentación Técnica del Proyecto

## Programación

- **Elementos fundamentales del código**:
  - Variables: Utilizo variables para almacenar datos temporales como `textArea`, `postBox`, `promptSystem`, `userPreferences`, `PORT`, etc.
  - Constantes: Declaro constantes como `app`, `openai`, `PORT` para valores que no cambian durante la ejecución.
  - Operadores: Implemento operadores aritméticos, de asignación y comparación en el código JavaScript.
  - Tipos de datos: Trabajo con strings para textos y mensajes, numbers para el puerto, objetos para las respuestas JSON, y booleanos para validaciones.

- **Estructuras de control**:
  - Selección: Uso condicionales `if/else` para validar si hay texto antes de publicar y para manejar errores.
  - Repetición: No implemento bucles explícitos ya que la aplicación se basa en eventos.
  - Saltos: Utilizo `return` para finalizar funciones y devolver respuestas HTTP.

- **Control de excepciones**:
  - Implemento bloques `try/catch` en las llamadas a la API de DeepSeek para capturar y manejar errores.
  - Gestiono errores devolviendo respuestas HTTP con códigos de estado 500 y mensajes descriptivos.

- **Documentación del código**:
  - Documento el código con comentarios descriptivos que explican la función de cada sección.
  - Incluyo comentarios sobre las dependencias importadas y su propósito.

- **Paradigma aplicado**:
  - Utilizo programación estructurada con JavaScript para el frontend y backend.
  - Elijo este paradigma por su simplicidad y adecuación para una aplicación web pequeña sin necesidad de estructuras complejas.

- **Clases y objetos principales**:
  - No implemento un sistema orientado a objetos formal, pero trabajo con objetos nativos de JavaScript y Express.
  - Utilizo el objeto `app` de Express para gestionar rutas y middleware.
  - Trabajo con el cliente `openai` para comunicarme con la API de DeepSeek.

- **Conceptos avanzados (herencia, polimorfismo, interfaces)**:
  - No aplico estos conceptos en este proyecto debido a su alcance limitado y enfoque en funcionalidad directa.

- **Gestión de información mediante archivos**:
  - Utilizo archivos estáticos para el frontend (HTML, CSS, JS).
  - Implemento una interfaz gráfica web para la interacción del usuario.
  - No almaceno datos persistentes en archivos, todo se procesa en memoria.

- **Estructuras de datos**:
  - Utilizo objetos JSON para las peticiones y respuestas de la API.
  - Trabajo con arrays para los mensajes en las peticiones a DeepSeek.
  - Manipulo el DOM para añadir elementos HTML dinámicamente.

- **Técnicas avanzadas**:
  - Implemento flujos de entrada/salida asíncronos con Promises y async/await para las peticiones HTTP.
  - Utilizo fetch API para comunicación cliente-servidor.

## Sistemas Informáticos

- **Características del hardware**:
  - Entorno de desarrollo: Windows 11 Pro, Intel i11, RTX 3090.
  - Entorno de producción: Máquina virtual Linux Server Ubuntu 24.04, 2 vCore CPU, 2GB RAM, 80GB NVMe SSD.

- **Sistema operativo seleccionado**:
  - Desarrollo: Windows 11 Pro por su interfaz amigable y compatibilidad con herramientas de desarrollo.
  - Producción: Ubuntu 24.04 por su estabilidad, seguridad y rendimiento para servidores web.

- **Configuración de redes**:
  - Tipo de red: TCP/IP sobre HTTP.
  - Protocolos: HTTP para la comunicación cliente-servidor.
  - Seguridad: Variables de entorno para proteger claves API.
  - En producción: Configuración con Apache/Nginx, posiblemente HTTPS con certificados SSL.

- **Sistemas de copias de seguridad**:
  - Desarrollo: Control de versiones Git para el código fuente.
  - Producción: Servicios de backup proporcionados por el proveedor de hosting o configurados a través de Plesk.

- **Medidas para asegurar integridad y seguridad**:
  - Uso de variables de entorno (.env) para proteger claves API.
  - Implementación de .gitignore para excluir archivos sensibles del control de versiones.
  - Validación de entradas en el frontend y backend.

- **Configuración de usuarios, permisos y accesos**:
  - Desarrollo: Ejecución con los permisos del usuario de Windows que inicia Laragon.
  - Producción: Gestión a través de Plesk, con usuarios específicos para el servidor web.

- **Documentación de configuración técnica**:
  - Documentación en README.md, CONEXIONES_BD.md y MEMORIAS.md.
  - Instrucciones detalladas para instalación y configuración.

## Entornos de Desarrollo

- **Entorno de desarrollo (IDE)**:
  - Utilizo Cursor como editor de código principal.
  - Lo configuro con extensiones para JavaScript, Node.js y formateo de código.

- **Automatización de tareas**:
  - Implemento scripts en package.json para iniciar el servidor (`npm start`).
  - Uso Nodemon para reiniciar automáticamente el servidor durante el desarrollo.

- **Control de versiones**:
  - Utilizo Git con repositorios en GitHub.
  - Gestiono versiones siguiendo un flujo de trabajo con ramas para nuevas características y correcciones.

- **Estrategia para refactorizar código**:
  - Identifico código repetitivo o complejo.
  - Extraigo funcionalidades comunes a funciones separadas.
  - Mantengo comentarios descriptivos para facilitar futuras refactorizaciones.

- **Documentación técnica del proyecto**:
  - Uso Markdown para toda la documentación (README.md, CONEXIONES_BD.md, MEMORIAS.md).
  - Incluyo comentarios en el código para documentar funcionalidades específicas.

- **Diagramas de clases o comportamiento**:
  - No he creado diagramas formales para este proyecto debido a su estructura simple.
  - La documentación textual describe adecuadamente el flujo y componentes.

## Bases de Datos

- **Sistema gestor de bases de datos**:
  - Actualmente no utilizo una base de datos relacional o NoSQL.
  - Toda la funcionalidad se basa en procesamiento en memoria y conexiones a la API de DeepSeek.
  - Si implementara una base de datos en el futuro, utilizaría MySQL por su integración con Node.js y amplia adopción.

- **Diseño del modelo entidad-relación**:
  - No aplica actualmente, pero he documentado un posible esquema futuro en CONEXIONES_BD.md con tablas para usuarios y traducciones/publicaciones.

- **Vistas, procedimientos almacenados, disparadores o funciones avanzadas**:
  - No aplica en la versión actual del proyecto.

- **Mecanismos para proteger y recuperar datos**:
  - No aplica en la versión actual, ya que no hay persistencia de datos.

## Lenguajes de Marcas y Sistemas de Gestión de Información

- **Estructura de documentos HTML**:
  - Estructuro el HTML siguiendo estándares web con doctype, metadatos, y elementos semánticos.
  - Aplico buenas prácticas como separación de contenido y presentación.

- **Tecnologías para el frontend**:
  - CSS: Utilizo CSS moderno con variables personalizadas, flexbox y diseño responsive.
  - JavaScript: Implemento JavaScript vanilla para manipulación del DOM y comunicación con el backend.
  - Elijo estas tecnologías por su simplicidad, rendimiento y no requerir frameworks pesados para esta aplicación.

- **JavaScript para interactuar con el DOM**:
  - Manipulo el DOM para añadir publicaciones dinámicamente.
  - Gestiono eventos de click en botones.
  - Actualizo el contenido del textarea según las respuestas de la API.

- **Validación de documentos HTML y CSS**:
  - No hay evidencia explícita de validación formal, pero el código sigue buenas prácticas.

- **Conversión de datos entre formatos**:
  - Utilizo JSON para la comunicación entre cliente y servidor por su eficiencia y compatibilidad nativa con JavaScript.

- **Interacción con sistemas de gestión empresarial**:
  - Esta aplicación puede considerarse una herramienta de gestión empresarial para marketing digital.
  - Específicamente, es una herramienta de gestión de contenido para redes sociales que automatiza la creación de publicaciones.

## Proyecto Intermodular

- **Objetivo del software**:
  - Crear una herramienta web que utiliza IA para generar publicaciones creativas y personalizadas para redes sociales.

- **Necesidad que cubre o problema que soluciona**:
  - Optimiza el tiempo de creación de contenido para redes sociales.
  - Proporciona ideas creativas con un tono ácido, humorístico o sarcástico.
  - Ayuda a mantener una presencia digital constante con contenido original.

- **Stack de tecnologías elegido**:
  - Backend: Node.js con Express para crear un servidor web ligero y eficiente.
  - Frontend: HTML, CSS y JavaScript vanilla para una interfaz simple y directa.
  - API: DeepSeek (compatible con OpenAI) para la generación de texto mediante IA.
  - Herramientas: dotenv para variables de entorno, nodemon para desarrollo.
  - He elegido este stack por su simplicidad, eficiencia y facilidad de despliegue.

- **Desarrollo por versiones**:
  - Versión 1.0.0 (actual): Funcionalidad básica de generación y visualización de publicaciones.
  - Según MEMORIAS.md, se ha migrado de OpenAI a DeepSeek para el servicio de IA.
  - Futuras mejoras planeadas incluyen más opciones de personalización y posible almacenamiento de historial.
