# Documentación Técnica PCpro - Chatbot para Supermercado

## Programación

### Elementos fundamentales del código
- **Variables**: Utilizamos variables para almacenar datos temporales como mensajes del usuario, respuestas del chatbot y el identificador único de usuario.
- **Constantes**: Definimos constantes para elementos inmutables como la configuración del contexto del chatbot, referencias a elementos del DOM y la instancia de OpenAI.
- **Operadores**: Implementamos operadores de asignación, comparación y lógicos para controlar el flujo de la aplicación.
- **Tipos de datos**: Trabajamos principalmente con strings para los mensajes, objetos para almacenar las conversaciones, números para identificadores y arrays para el historial de mensajes.

### Estructuras de control utilizadas
- **Selección**: Utilizamos condicionales `if/else` para validar entradas de usuario y manejar errores.
- **Repetición**: Implementamos limitación del historial de conversaciones mediante manipulación de arrays.
- **Saltos**: Empleamos eventos para controlar el flujo de ejecución, como el evento "click" del botón de envío y "keypress" para detectar la tecla Enter.

### Control de excepciones
- Implementamos bloques try/catch para manejar errores en las peticiones a la API de OpenAI.
- Validamos la entrada del usuario para evitar mensajes vacíos.
- Gestionamos errores de comunicación con el servidor mediante respuestas HTTP con códigos de estado apropiados.

### Documentación del código
- El código incluye comentarios explicativos sobre la funcionalidad de cada sección.
- Los nombres de variables y funciones son descriptivos y siguen convenciones de nomenclatura estándar.
- La estructura del proyecto está documentada en README.md con instrucciones detalladas de instalación y configuración.

### Paradigma aplicado
- Utilizamos principalmente programación estructurada con elementos de programación funcional.
- Esta elección se debe a la simplicidad del proyecto y la naturaleza de las operaciones realizadas, que no requieren un enfoque completamente orientado a objetos.

### Clases y objetos principales
- No implementamos clases formales, pero utilizamos objetos literales para:
  - Almacenar conversaciones indexadas por ID de usuario.
  - Estructurar los mensajes con roles (usuario/asistente) y contenido.
  - Configurar las peticiones a la API de OpenAI.

### Conceptos avanzados
- No implementamos herencia o polimorfismo formal, pero utilizamos composición de objetos para estructurar los datos.
- Empleamos funciones asíncronas (async/await) para manejar las peticiones a la API de forma eficiente.

### Gestión de información
- Actualmente no utilizamos archivos para almacenamiento persistente; las conversaciones se mantienen en memoria durante la ejecución.
- La interacción del usuario se realiza mediante una interfaz gráfica web con elementos HTML, CSS y JavaScript.

### Estructuras de datos utilizadas
- **Objetos**: Para almacenar las conversaciones indexadas por ID de usuario.
- **Arrays**: Para mantener el historial de mensajes de cada conversación.
- **JSON**: Para la comunicación entre el frontend y el backend.

### Técnicas avanzadas
- Implementamos flujos de entrada/salida asíncronos para la comunicación con la API de OpenAI.
- Utilizamos fetch API para las peticiones HTTP.
- Aplicamos manipulación dinámica del DOM para actualizar la interfaz de usuario.

## Sistemas Informáticos

### Características del hardware
- **Entorno de desarrollo**: 
  - Windows 11 Pro
  - Procesador Intel i11
  - Tarjeta gráfica RTX 3090
  - Memoria y almacenamiento suficientes para desarrollo web

- **Entorno de producción**:
  - Máquina virtual Linux Server Ubuntu 24.04
  - 2 vCore CPU
  - 2 GB RAM
  - 80 GB NVMe SSD

### Sistema operativo seleccionado
- **Desarrollo**: Windows 11 Pro por su compatibilidad con las herramientas de desarrollo y facilidad de uso.
- **Producción**: Ubuntu 24.04 por su estabilidad, seguridad y rendimiento para aplicaciones web.

### Configuración de redes
- **Tipo de red**: Cliente-servidor web con comunicación HTTP/HTTPS.
- **Protocolos**: HTTP/HTTPS para la comunicación entre cliente y servidor, TCP/IP como base.
- **Seguridad**: En desarrollo se utiliza la seguridad de la red local. En producción se implementa HTTPS con certificados SSL/TLS.

### Sistemas de copias de seguridad
- **Desarrollo**: Control de versiones Git como respaldo del código fuente.
- **Producción**: Backups automáticos programados a través de Plesk para archivos y base de datos.

### Medidas de seguridad de datos
- Validación de entradas de usuario para prevenir inyecciones.
- Limitación de contexto del chatbot para evitar respuestas inapropiadas.
- Uso de variables de entorno para proteger claves API.
- Implementación de HTTPS en producción.

### Configuración de usuarios y permisos
- **Desarrollo**: Ejecución bajo el usuario de Windows que inicia los servicios.
- **Producción**: Configuración de permisos específicos para directorios de la aplicación (chmod 755).
- Gestión de usuarios a través de Plesk para FTP y SSH si está habilitado.

### Documentación de configuración técnica
- Documentación detallada en README.md sobre instalación y configuración.
- Documentación específica sobre conexiones de base de datos en CONEXIONES_BD.md.
- Registro de decisiones técnicas en MEMORIAS.md.

## Entornos de Desarrollo

### Entorno de desarrollo utilizado
- **IDE principal**: Cursor, elegido por su integración con IA y funcionalidades avanzadas.
- **Configuración**: Personalizada para desarrollo web con extensiones para JavaScript, Node.js y PHP.

### Automatización de tareas
- Uso de npm scripts para iniciar el servidor y gestionar dependencias.
- Configuración de recarga automática durante desarrollo.

### Control de versiones
- **Sistema**: Git para control de versiones local.
- **Plataforma**: GitHub para almacenamiento remoto y colaboración.
- **Gestión**: Ramas para desarrollo de características y versiones.

### Estrategia de refactorización
- Mejora continua del código manteniendo la funcionalidad existente.
- Optimización de rendimiento y legibilidad.
- Documentación de cambios en MEMORIAS.md.

### Documentación técnica
- Uso extensivo de markdown para toda la documentación.
- README.md para instrucciones generales y descripción del proyecto.
- Documentación específica en archivos separados dentro del directorio docs/.

### Diagramas
- No se han encontrado diagramas formales de clases o comportamiento en la documentación actual.

## Bases de Datos

### Sistema gestor de bases de datos seleccionado
- Actualmente no se utiliza una base de datos persistente.
- Se propone implementar MySQL o PostgreSQL en futuras versiones por su robustez y compatibilidad con Node.js.

### Diseño del modelo entidad-relación
- Propuesta documentada en CONEXIONES_BD.md con tres tablas principales:
  - `users`: Para almacenar información de usuarios.
  - `conversations`: Para registrar conversaciones.
  - `messages`: Para almacenar mensajes individuales.

### Uso de características avanzadas
- No implementadas actualmente, pero se proponen consultas SQL para futuras versiones.
- Se planea implementar índices para optimizar búsquedas frecuentes.

### Mecanismos de protección y recuperación
- Actualmente no implementados.
- Se propone un sistema de respaldo y recuperación para futuras versiones.

## Lenguajes de Marcas y Sistemas de Gestión de Información

### Estructura de documentos HTML
- Estructura semántica con uso de elementos HTML5 como `section`, `header`.
- Aplicación de buenas prácticas con separación de contenido, presentación y comportamiento.

### Tecnologías frontend
- **CSS3**: Para estilos visuales responsivos y animaciones.
- **JavaScript (ES6+)**: Para la lógica del cliente y comunicación con el servidor.
- Estas tecnologías fueron elegidas por su compatibilidad universal y capacidad para crear interfaces modernas.

### Uso de JavaScript con DOM
- Manipulación dinámica del DOM para añadir mensajes al chat.
- Gestión de eventos para interacción del usuario (click, keypress).
- Control de scroll automático para mejorar la experiencia de usuario.

### Validación de documentos
- No se menciona validación formal de HTML y CSS en la documentación.

### Conversión de datos entre formatos
- Uso de JSON para la comunicación entre frontend y backend.
- Procesamiento de respuestas de la API de OpenAI en formato JSON.

### Interacción con sistemas de gestión empresarial
- La aplicación puede considerarse una herramienta de gestión empresarial de tipo CRM (Customer Relationship Management) enfocada en atención al cliente automatizada para supermercados.

## Proyecto Intermodular

### Objetivo del software
- Proporcionar un chatbot de atención al cliente automatizado para supermercados.
- Responder consultas de clientes sobre horarios, productos, ubicación y métodos de pago.

### Necesidad cubierta
- Reducción de carga de trabajo del personal de atención al cliente.
- Disponibilidad 24/7 para responder consultas básicas de clientes.
- Mejora de la experiencia del usuario en la web o aplicación del negocio.

### Stack tecnológico elegido
- **Backend**: Node.js con Express por su eficiencia y facilidad para crear APIs.
- **IA**: OpenAI API (GPT-3.5 Turbo) por su capacidad de procesamiento de lenguaje natural.
- **Frontend**: HTML5, CSS3 y JavaScript para una interfaz responsiva y accesible.
- **Gestión de configuración**: dotenv para variables de entorno.

### Desarrollo por versiones
- **Versión 1.0.0 (actual)**: Funcionalidad básica de chat con contexto controlado.
- **Futuras versiones planificadas**:
  - Implementación de base de datos para persistencia.
  - Panel de administración para gestión del contexto.
  - Autenticación para proteger la API.
  - Análisis de sentimiento para mejorar respuestas.
