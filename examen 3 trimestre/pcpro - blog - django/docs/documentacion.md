# Documentación Técnica del Proyecto

## Programación

- **Elementos fundamentales del código**:
  - Variables: Utilizamos variables para almacenar datos temporales en las vistas (como `projects` en `portfolio_views.py`).
  - Constantes: Definidas en settings.py (como `SECRET_KEY`, `MEDIA_URL`, `STATIC_URL`).
  - Operadores: Principalmente operadores de asignación (=) y comparación en plantillas Django ({% if %}).
  - Tipos de datos: Strings para títulos y URLs, integers para IDs, DateTimeField para fechas, ImageField para imágenes.

- **Estructuras de control utilizadas**:
  - Selección: Uso de condicionales `{% if %}` en plantillas (como en portfolio.html para mostrar enlaces opcionales).
  - Repetición: Bucles `{% for %}` en plantillas para iterar sobre colecciones de objetos (como en portfolio.html para mostrar proyectos).
  - No se utilizan saltos explícitos ya que Django maneja el flujo de control.

- **Control de excepciones**:
  - Django maneja automáticamente muchas excepciones comunes.
  - No hay implementación explícita de try/except en el código visible, pero Django proporciona manejo de errores HTTP por defecto.

- **Documentación del código**:
  - Comentarios básicos en archivos Python (como "# Create your models here." en models.py).
  - Docstrings en los archivos de configuración generados por Django.
  - Documentación externa en README.md y archivos en la carpeta docs/.

- **Paradigma aplicado**:
  - Orientado a objetos: El proyecto utiliza el framework Django que implementa el patrón MVC (Modelo-Vista-Controlador).
  - Elegido por la naturaleza del proyecto web y las ventajas de Django para desarrollo rápido y seguro.

- **Clases y objetos principales**:
  - `Project`: Clase modelo principal que representa los proyectos del portafolio.
  - `ProjectAdmin`: Clase para configurar la administración de proyectos en el panel de Django.
  - Relaciones: No hay relaciones explícitas entre modelos ya que solo existe un modelo principal.

- **Conceptos avanzados OOP**:
  - Herencia: Las vistas heredan de las clases base de Django, los modelos heredan de `models.Model`.
  - No se implementa polimorfismo explícito ni interfaces en el código visible.

- **Gestión de información**:
  - Archivos: Las imágenes se almacenan en el sistema de archivos (carpeta media/projects/).
  - Interfaz gráfica: Implementada mediante plantillas HTML con Bootstrap para la interfaz de usuario.
  - Panel de administración de Django para la gestión de contenidos.

- **Estructuras de datos utilizadas**:
  - Listas: QuerySets de Django para recuperar y manipular colecciones de objetos (como `Project.objects.all()`).
  - Diccionarios: Para pasar contexto a las plantillas (como `{"projects": projects}`).
  - Elegidas por su integración con el ORM de Django y facilidad de uso.

- **Técnicas avanzadas**:
  - Expresiones regulares: Utilizadas internamente por Django para el enrutamiento de URLs.
  - Flujos de entrada/salida: Manejo de archivos para la carga de imágenes con Pillow.

## Sistemas Informáticos

- **Características del hardware**:
  - Entorno de desarrollo: Windows 11 Pro, Intel i11, RTX 3090.
  - Entorno de producción: Linux Server Ubuntu 24.04, VPS con 2 vCore, 2GB RAM, 80GB NVMe SSD.

- **Sistema operativo seleccionado**:
  - Desarrollo: Windows 11 Pro por su compatibilidad con las herramientas de desarrollo y facilidad de uso.
  - Producción: Linux Server Ubuntu por su estabilidad, seguridad y rendimiento para aplicaciones web.

- **Configuración de redes**:
  - Tipo de red: TCP/IP sobre HTTP/HTTPS.
  - Protocolos: HTTP para desarrollo local, HTTPS recomendado para producción.
  - Seguridad: Configuración de firewall en el servidor de producción, certificados SSL/TLS para HTTPS.

- **Sistemas de copias de seguridad**:
  - Desarrollo: Control de versiones Git para el código fuente.
  - Producción: Backups automáticos programados a través de Plesk.

- **Medidas de seguridad e integridad de datos**:
  - Validación de formularios en Django.
  - Protección CSRF en formularios.
  - Panel de administración protegido con autenticación.
  - Configuración de permisos adecuados en el servidor de producción.

- **Configuración de usuarios y permisos**:
  - Desarrollo: Ejecución con permisos del usuario de Windows que inicia Laragon.
  - Producción: Gestión a través de Plesk, con permisos específicos para directorios como media/ (chmod 755).

- **Documentación de configuración técnica**:
  - README.md: Instrucciones de instalación y configuración.
  - CONEXIONES_BD.md: Documentación sobre la base de datos.
  - MEMORIAS.md: Registro de decisiones de diseño y cambios.

## Entornos de Desarrollo

- **IDE utilizado**:
  - Cursor como editor de código principal.
  - Configurado con extensiones para Python y Django.

- **Automatización de tareas**:
  - Script runserver.bat para iniciar el servidor de desarrollo rápidamente.
  - Uso de comandos de Django para tareas comunes (migrate, collectstatic).

- **Control de versiones**:
  - Git para control de versiones local.
  - GitHub como plataforma para repositorios remotos.
  - Gestión de versiones mediante commits y ramas para nuevas funcionalidades.

- **Estrategia de refactorización**:
  - Organización modular del código en apps separadas (core y portfolio).
  - Uso de plantillas base con herencia para evitar duplicación de código HTML.

- **Documentación técnica**:
  - Uso de Markdown para README.md y documentación en la carpeta docs/.
  - Comentarios en el código para explicar funcionalidades específicas.

- **Diagramas y modelado**:
  - No se encontraron diagramas explícitos en el repositorio, pero la estructura sigue el patrón MVC de Django.

## Bases de Datos

- **Sistema gestor seleccionado**:
  - SQLite para desarrollo por su simplicidad y no requerir configuración.
  - Recomendación de PostgreSQL o MySQL para producción por rendimiento y concurrencia.

- **Diseño del modelo entidad-relación**:
  - Modelo principal: Project con campos title, description, image, created, updated, url.
  - Relaciones: No hay relaciones entre entidades ya que solo existe un modelo principal.

- **Uso de características avanzadas**:
  - No se implementan vistas, procedimientos almacenados o disparadores explícitos.
  - Se utilizan campos de solo lectura en el admin (created, updated).

- **Mecanismos de protección y recuperación**:
  - Migraciones de Django para gestionar cambios en el esquema.
  - Backups de la base de datos recomendados en producción.

## Lenguajes de Marcas y Sistemas de Gestión de Información

- **Estructura de documentos HTML**:
  - Uso de plantilla base (base.html) con bloques para contenido específico.
  - Implementación de buenas prácticas con etiquetas semánticas HTML5.
  - Estructura responsive con Bootstrap.

- **Tecnologías frontend**:
  - CSS: Bootstrap para el diseño responsive y componentes UI.
  - JavaScript: jQuery para interactividad básica y funcionalidades de Bootstrap.
  - Elegidas por su facilidad de uso y amplia adopción en la comunidad.

- **Interacción con el DOM**:
  - JavaScript para menú responsive y efectos de scroll.
  - Integración con Bootstrap para componentes interactivos.

- **Validación de documentos**:
  - No se menciona validación explícita, pero se siguen estándares HTML5.

- **Conversión entre formatos**:
  - Django serializa automáticamente datos entre Python y HTML.
  - No hay implementación explícita de conversión entre XML/JSON.

- **Interacción con sistemas de gestión**:
  - La aplicación puede considerarse una herramienta de gestión de portafolio profesional.
  - Tipo: Sistema de gestión de contenidos (CMS) especializado en portafolios.

## Proyecto Intermodular

- **Objetivo del software**:
  - Crear una plataforma web para mostrar el portafolio profesional de desarrolladores, freelancers o agencias.

- **Necesidad cubierta**:
  - Facilitar la presentación profesional de proyectos para atraer clientes o reclutadores.
  - Potenciar la marca personal de profesionales del desarrollo web.

- **Stack tecnológico elegido**:
  - Backend: Python con Django 5.2 por su robustez y rapidez de desarrollo.
  - Frontend: HTML5, CSS3 con Bootstrap para diseño responsive.
  - Base de datos: SQLite para desarrollo, PostgreSQL/MySQL recomendado para producción.
  - Despliegue: Gunicorn/Waitress como servidores de aplicaciones, Nginx como proxy inverso.
  - Elegido por la combinación de facilidad de desarrollo y potencia para aplicaciones web.

- **Desarrollo por versiones**:
  - Versión inicial con funcionalidad básica de visualización de proyectos.
  - Actualizaciones documentadas en MEMORIAS.md (última actualización: 2025-04-24).
  - Mejoras como la configuración de WhiteNoise para servir archivos estáticos en producción.
