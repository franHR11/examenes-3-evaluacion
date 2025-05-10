# Documentación Técnica - Agencia de Viajes Node.js

Este documento contiene la información técnica detallada del proyecto Agencia de Viajes desarrollado con Node.js, respondiendo a las preguntas planteadas por asignatura.

## Programación

- **Elementos fundamentales del código**:
  - Variables: Utilizo variables para almacenar datos temporales como resultados de consultas, parámetros de rutas y datos de formularios.
  - Constantes: Defino constantes para elementos que no cambian como la configuración de Express, conexión a la base de datos y puerto del servidor.
  - Operadores: Implemento operadores de comparación en validaciones de formularios y operadores lógicos para controlar el flujo.
  - Tipos de datos: Trabajo con strings (nombres, correos, mensajes), números (precios, disponibilidad), objetos (modelos de datos), arrays (resultados de consultas) y fechas (para viajes).

- **Estructuras de control**:
  - Selección: Uso condicionales if/else para validar formularios de testimoniales y comprobar errores.
  - Repetición: Implemento bucles para recorrer resultados de consultas de viajes y testimoniales.
  - Asincronía: Utilizo async/await para gestionar operaciones asíncronas con la base de datos.

- **Control de excepciones**:
  - Implemento bloques try/catch para manejar errores en operaciones de base de datos.
  - Gestiono errores de validación en formularios con arrays de errores que se muestran al usuario.

- **Documentación del código**:
  - He documentado las funciones principales con comentarios que explican su propósito.
  - Incluyo comentarios para secciones importantes como la configuración de la base de datos y rutas.

- **Paradigma aplicado**:
  - Orientación a objetos: Utilizo este paradigma mediante modelos Sequelize que encapsulan la lógica de datos.
  - MVC (Modelo-Vista-Controlador): Separo la lógica de negocio (controladores), acceso a datos (modelos) y presentación (vistas Pug).

- **Clases y objetos principales**:
  - Modelos: `Viaje` y `Testimonial` que representan las entidades de la base de datos.
  - Controladores: `paginasController` y `testimonialController` que gestionan la lógica de negocio.
  - Relaciones: Los controladores utilizan los modelos para acceder y manipular datos.

- **Conceptos avanzados**:
  - Promesas: Implemento Promise.all para consultas paralelas a la base de datos.
  - ORM: Utilizo Sequelize como capa de abstracción para interactuar con la base de datos.

- **Gestión de información**:
  - Base de datos: Almaceno la información persistente en MySQL mediante Sequelize.
  - Interfaz gráfica: Utilizo plantillas Pug para la interacción con el usuario.

- **Estructuras de datos**:
  - Arrays: Para almacenar resultados de consultas de viajes y testimoniales.
  - Objetos: Para estructurar datos de modelos y parámetros de peticiones.
  - JSON: Para intercambio de datos entre el servidor y la aplicación.

- **Técnicas avanzadas**:
  - Flujos de entrada/salida: Gestiono peticiones HTTP y respuestas del servidor.
  - Middleware: Implemento middleware de Express para procesar formularios y configurar variables globales.

## Sistemas Informáticos

- **Características del hardware**:
  - Entorno de desarrollo: Windows 11 Pro con procesador Intel i11, RTX 3090, memoria suficiente para ejecutar entornos virtuales y servicios locales.
  - Entorno de producción: VPS con 2 vCore CPU, 2GB RAM, 80GB NVMe SSD, optimizado para aplicaciones web.

- **Sistema operativo seleccionado**:
  - Desarrollo: Windows 11 Pro por su compatibilidad con las herramientas de desarrollo y facilidad de uso.
  - Producción: Ubuntu 24.04 por su estabilidad, seguridad y rendimiento en servidores web.

- **Configuración de redes**:
  - Tipo de red: TCP/IP sobre HTTP/HTTPS.
  - Protocolos: HTTP para comunicación cliente-servidor.
  - Seguridad: Configuración de puertos específicos (5002) y acceso controlado.

- **Sistemas de copias de seguridad**:
  - Control de versiones Git para el código fuente.
  - Backups automáticos de la base de datos MySQL.
  - Copias de seguridad periódicas del servidor de producción.

- **Medidas de seguridad e integridad**:
  - Validación de datos en formularios.
  - Sanitización de entradas de usuario.
  - Configuración segura de la base de datos con credenciales específicas.

- **Configuración de usuarios y permisos**:
  - Usuarios de base de datos con permisos limitados (usuario 'franhr').
  - Permisos de sistema de archivos adecuados para directorios de la aplicación.
  - Separación de entornos de desarrollo y producción.

- **Documentación de configuración técnica**:
  - README.md con instrucciones de instalación y configuración.
  - Comentarios en archivos de configuración como db.js.
  - Documentación de la estructura del proyecto y sus componentes.

## Entornos de Desarrollo

- **IDE utilizado**:
  - Cursor como editor de código principal por sus capacidades de autocompletado y asistencia IA.
  - Configurado con linters para JavaScript y formateo automático de código.

- **Automatización de tareas**:
  - Scripts NPM para iniciar el servidor (`npm run dev`).
  - Nodemon para reinicio automático del servidor durante desarrollo.

- **Control de versiones**:
  - Git para control de versiones local.
  - GitHub como plataforma remota para almacenar el repositorio.
  - Gestión de ramas para desarrollo de nuevas características y corrección de errores.

- **Estrategia de refactorización**:
  - Separación de responsabilidades en controladores específicos.
  - Modularización del código en componentes reutilizables.
  - Revisión periódica para mejorar la legibilidad y mantenibilidad.

- **Documentación técnica**:
  - README.md en formato Markdown con información detallada del proyecto.
  - Comentarios en el código para explicar funcionalidades complejas.
  - Estructura clara de carpetas que refleja la arquitectura del proyecto.

- **Diagramas y modelado**:
  - Arquitectura MVC implementada en la estructura de carpetas.
  - Modelos de datos definidos con Sequelize que reflejan la estructura de la base de datos.

## Bases de Datos

- **Sistema gestor seleccionado**:
  - MySQL por su robustez, rendimiento y compatibilidad con Sequelize.
  - Facilidad de integración con Node.js mediante el paquete mysql2.

- **Diseño del modelo entidad-relación**:
  - Entidad `viajes` con atributos como título, precio, fechas, imagen, descripción, disponibilidad y slug.
  - Entidad `testimoniales` con atributos nombre, correo y mensaje.
  - Relaciones implícitas a través de consultas en el código.

- **Funcionalidades avanzadas**:
  - Consultas parametrizadas a través de Sequelize.
  - Limitación de resultados para optimizar rendimiento (ej. `limit: 3` en consultas).
  - Transacciones implícitas en operaciones de creación de testimoniales.

- **Mecanismos de protección y recuperación**:
  - Validación de datos antes de inserción en la base de datos.
  - Manejo de errores en operaciones de base de datos.
  - Configuración de pool de conexiones para optimizar recursos.

## Lenguajes de Marcas y Sistemas de Gestión de Información

- **Estructura de documentos HTML**:
  - Generados mediante plantillas Pug con estructura semántica.
  - Implementación de componentes reutilizables (layouts, bloques).
  - Separación de contenido y presentación.

- **Tecnologías frontend**:
  - CSS: Bootstrap para diseño responsive y consistente.
  - CSS personalizado para estilos específicos de la aplicación.
  - JavaScript para validación de formularios y mejora de la experiencia de usuario.

- **Interacción con el DOM**:
  - JavaScript para validación de formularios.
  - Manipulación dinámica de elementos de la página.

- **Validación de documentos**:
  - Estructura HTML correcta generada por Pug.
  - CSS compatible con estándares web actuales.

- **Conversión de datos entre formatos**:
  - JSON para intercambio de datos entre el servidor y la aplicación.
  - Objetos JavaScript convertidos a JSON para operaciones de base de datos.

- **Aplicación como sistema de gestión empresarial**:
  - Es una aplicación de gestión empresarial de tipo CRM para agencias de viajes.
  - Permite gestionar catálogo de productos (viajes), testimonios de clientes y promociones.
  - Facilita la interacción con clientes potenciales mediante formularios de contacto.

## Proyecto Intermodular

- **Objetivo del software**:
  - Crear una plataforma web para una agencia de viajes que permita mostrar destinos, recoger testimonios y gestionar información turística.

- **Necesidad que cubre**:
  - Presencia digital para agencias de viajes.
  - Canal de comunicación con clientes potenciales.
  - Showcase de destinos turísticos con información detallada.
  - Sistema de recolección de feedback de clientes.

- **Stack tecnológico elegido**:
  - Backend: Node.js con Express por su eficiencia y escalabilidad.
  - ORM: Sequelize para abstracción de base de datos.
  - Base de datos: MySQL por su robustez y compatibilidad.
  - Frontend: Pug como motor de plantillas por su sintaxis limpia y eficiente.
  - CSS: Bootstrap para diseño responsive y moderno.

- **Desarrollo por versiones**:
  - Versión 1.0.0: Funcionalidad básica con listado de viajes, detalles y testimoniales.
  - Futuras actualizaciones: Implementación de sistema de reservas, panel de administración, integración con pasarelas de pago.
  - Mejoras planificadas: Optimización de rendimiento, mejoras de UX/UI, implementación de API RESTful.
