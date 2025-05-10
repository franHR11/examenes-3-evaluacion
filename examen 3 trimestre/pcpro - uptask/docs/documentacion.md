# Documentación Técnica del Proyecto UpTask

## Programación

- **Elementos fundamentales incluidos en el código**: He utilizado variables para almacenar datos temporales como información de usuarios, proyectos y tareas. Constantes para definir valores fijos como rutas y configuraciones. Operadores aritméticos, de comparación y lógicos para realizar operaciones y validaciones. Tipos de datos principalmente string para textos, int para identificadores, boolean para estados de confirmación y arrays asociativos para transferencia de datos.

- **Estructuras de control utilizadas**: Implementé estructuras de selección (if-else) para validar datos de formularios y autenticación de usuarios. Utilicé estructuras de repetición (foreach) para iterar sobre colecciones de proyectos y tareas. Apliqué saltos de control con return para finalizar la ejecución de funciones tras validaciones o redirecciones con header().

- **Control de excepciones**: He implementado un sistema de validación de errores mediante alertas. En los modelos (Usuario, Proyecto, Tarea) se validan los datos de entrada y se almacenan los errores en un array de alertas que luego se muestran al usuario. En la parte de conexión a la base de datos capturamos errores de conexión y mostramos mensajes detallados.

- **Documentación del código**: He documentado el código con comentarios explicativos en puntos clave, especialmente en funciones complejas. Por ejemplo, en tareas.js hay comentarios que explican el propósito de cada función y el flujo de ejecución, como "// Crear elemento virtual para representar una tarea" o "// Comparar DOM virtual con actual y actualizar solo lo necesario".

- **Paradigma aplicado**: He aplicado programación orientada a objetos porque permite una mejor organización del código, reutilización mediante herencia, y separación clara de responsabilidades. Esto facilita el mantenimiento y la extensión del sistema a medida que crecen las funcionalidades.

- **Clases y objetos principales**: Las clases principales son Usuario, Proyecto, Tarea (modelos) y LoginController, DashboardController, TareaController (controladores). Se relacionan siguiendo el patrón MVC: los controladores reciben peticiones, usan los modelos para acceder a datos y envían la información a las vistas para su presentación.

- **Conceptos avanzados de POO**: He implementado herencia mediante la clase ActiveRecord que es extendida por los modelos (Usuario, Proyecto, Tarea), permitiendo compartir funcionalidad de acceso a datos. Utilizo polimorfismo en los métodos de validación que se comportan de manera diferente según el modelo. No he definido interfaces formales pero hay métodos con firmas consistentes en diferentes clases.

- **Gestión de información mediante archivos**: Gestiono la información principalmente mediante base de datos MySQL, no con archivos planos. Para la interacción del usuario utilizo interfaces gráficas web con formularios HTML que envían datos mediante POST para operaciones CRUD, y peticiones fetch() en JavaScript para actualizar tareas sin recargar la página.

- **Estructuras de datos utilizadas**: He usado arrays asociativos para transferir datos entre controladores y vistas, objetos para representar entidades del dominio, y colecciones (arrays de objetos) para manejar listas de proyectos y tareas. También implementé un DOM virtual en JavaScript para optimizar actualizaciones de la interfaz.

- **Técnicas avanzadas aplicadas**: He aplicado expresiones regulares para validar emails con filter_var() y FILTER_VALIDATE_EMAIL. Uso flujos de entrada/salida con fetch() para comunicación asíncrona entre el cliente y el servidor. Implementé el hashing de contraseñas con password_hash() y password_verify() para aumentar la seguridad.

## Sistemas Informáticos

- **Características del hardware**: En desarrollo trabajo con un equipo Windows 11 Pro con procesador Intel i11, tarjeta gráfica RTX 3090, que proporciona alto rendimiento para desarrollo y pruebas. En producción, el sistema se ejecuta en una máquina virtual Linux con 2 vCores, 2GB de RAM y 80GB NVMe SSD, suficiente para gestionar las peticiones de la aplicación web.

- **Sistema operativo seleccionado**: Para desarrollo he elegido Windows 11 Pro por su compatibilidad con las herramientas de desarrollo utilizadas y su interfaz gráfica intuitiva. Para producción utilizo Ubuntu 24.04 por su estabilidad, seguridad, menor consumo de recursos y mejor rendimiento para aplicaciones web.

- **Configuración de redes**: En desarrollo uso una red local configurada por Laragon que establece un entorno localhost para acceder a la aplicación. En producción, la aplicación es accesible a través de Internet mediante HTTP/HTTPS, con configuración de firewall y certificados SSL/TLS para conexiones seguras gestionadas a través de Plesk.

- **Sistemas de copias de seguridad**: En desarrollo utilizo control de versiones Git como principal mecanismo de respaldo del código. En producción aprovecho los servicios de backup automatizados de Plesk que realizan copias diarias de archivos y base de datos, almacenándolas de forma segura y permitiendo restauración rápida en caso de problemas.

- **Medidas de seguridad de datos**: Implemento hashing seguro de contraseñas con PHP, validación de entradas en formularios para prevenir inyección SQL y XSS, y autenticación con sesiones para proteger rutas privadas. En el servidor de producción, utilizo HTTPS para cifrar la comunicación, actualizaciones regulares de seguridad y configuración restrictiva de permisos de archivos.

- **Configuración de usuarios y permisos**: En desarrollo, la aplicación se ejecuta con los permisos del usuario de Windows que inicia Laragon. En producción, Plesk gestiona los usuarios del sistema (FTP, SSH) y los permisos de archivos/directorios específicos para el usuario bajo el cual se ejecuta el servidor web, configurados para permitir escritura solo en directorios necesarios.

- **Documentación de configuración técnica**: He documentado la configuración en varios archivos. El README.md incluye instrucciones de instalación y requisitos del sistema. El archivo CONEXIONES_BD.md detalla el esquema de la base de datos, consultas importantes y recomendaciones para su configuración.

## Entornos de Desarrollo

- **Entorno de desarrollo utilizado**: Utilizo Cursor como editor de código principal por sus funcionalidades avanzadas de autocompletado y su integración con asistentes IA para agilizar el desarrollo. Lo he configurado con extensiones para PHP, JavaScript y SASS para optimizar la experiencia de codificación con resaltado de sintaxis y herramientas de depuración.

- **Automatización de tareas**: He implementado automatización mediante Gulp para compilar archivos SASS a CSS, minificar JavaScript y optimizar activos. Esto mejora el flujo de trabajo y garantiza consistencia en el código generado. Las tareas están definidas en gulpfile.js y se ejecutan mediante los comandos npm run dev y npm run build.

- **Control de versiones**: Utilizo Git como sistema de control de versiones y GitHub como plataforma para alojar el repositorio. Gestiono el desarrollo con la rama principal (main) para código estable y ramas de características para nuevas funcionalidades. Realizo commits frecuentes con mensajes descriptivos para mantener un historial claro de cambios.

- **Estrategia de refactorización**: Mi estrategia incluye identificar código duplicado para extraerlo en funciones reutilizables, simplificar métodos complejos dividiéndolos en componentes más pequeños, y mejorar nombres de variables y funciones para aumentar la legibilidad. Aplico estos cambios incrementalmente, manteniendo la funcionalidad existente.

- **Documentación técnica del proyecto**: Documento el proyecto usando archivos Markdown que son fáciles de leer y mantener. El README.md principal describe la aplicación, su instalación y uso. El archivo CONEXIONES_BD.md detalla la estructura de la base de datos. Para documentar el código uso comentarios descriptivos en cada función importante.

- **Diagramas de modelado**: No he implementado diagramas formales UML, pero mantengo una estructura clara basada en el patrón MVC que define las relaciones entre clases. La arquitectura se puede inferir del código organizado en directorios (controllers, models, views) que reflejan las responsabilidades de cada componente.

## Bases de Datos

- **Sistema gestor de bases de datos seleccionado**: He elegido MySQL por su robustez, rendimiento optimizado para aplicaciones web, amplia documentación y compatibilidad con PHP. Además, es fácil de configurar tanto en entornos de desarrollo (Laragon) como en producción (Plesk).

- **Diseño del modelo entidad-relación**: Mi diseño incluye tres entidades principales: Usuario, Proyecto y Tarea. Un Usuario puede tener muchos Proyectos (relación 1:N). Un Proyecto puede tener muchas Tareas (relación 1:N). He implementado claves foráneas para mantener la integridad referencial, como propietarioId en Proyecto que referencia a Usuario, y proyectoId en Tarea que referencia a Proyecto.

- **Uso de características avanzadas de BD**: No he implementado procedimientos almacenados ni disparadores directamente en la base de datos, ya que la lógica de negocio está principalmente en el código PHP. Sin embargo, utilizo consultas parametrizadas y vistas implícitas a través del ORM implementado en la clase ActiveRecord para abstraer las operaciones comunes de la base de datos.

- **Mecanismos de protección de datos**: Implemento validación de entradas para prevenir inyección SQL, uso consultas preparadas a través de mysqli, y aplico un patrón Active Record para abstraer y encapsular el acceso a la base de datos. En producción, utilizo backups automatizados para la recuperación de datos en caso de fallos.

## Lenguajes de Marcas y Sistemas de Gestión de Información

- **Estructura de documentos HTML**: He estructurado los documentos HTML siguiendo buenas prácticas, con una clara separación entre estructura (HTML), presentación (CSS) y comportamiento (JavaScript). Utilizo etiquetas semánticas como header, main, section y footer, y atributos ARIA donde es necesario para mejorar la accesibilidad.

- **Tecnologías frontend utilizadas**: Para el frontend utilizo SASS como preprocesador de CSS, lo que permite usar variables, anidamiento y mixins para escribir estilos más mantenibles. JavaScript es utilizado para la interactividad, especialmente en la gestión de tareas donde implemento actualizaciones asíncronas mediante fetch API. Estas tecnologías proporcionan una experiencia de usuario fluida y responsive.

- **Interacción con el DOM mediante JavaScript**: Implemento manipulación del DOM para añadir/eliminar tareas, cambiar estados y mostrar/ocultar formularios sin recargar la página. He optimizado el rendimiento usando un patrón de DOM virtual que compara cambios y actualiza solo los elementos necesarios, similar a frameworks modernos pero a menor escala.

- **Validación de documentos**: Aplico validación de formularios tanto en el cliente (JavaScript) como en el servidor (PHP) para garantizar la integridad de los datos. Los documentos HTML siguen la especificación HTML5 con doctype adecuado y etiquetas correctamente anidadas.

- **Conversión entre formatos de datos**: Implemento conversión entre formatos en la API de tareas, donde los datos se envían como JSON entre el cliente y el servidor. Utilizo json_encode() en PHP para convertir arrays a JSON en las respuestas de la API, y JSON.parse()/stringify() en JavaScript para procesar estos datos en el cliente.

- **Interacción con sistemas de gestión empresarial**: Mi aplicación UpTask es un sistema de gestión empresarial especializado en gestión de proyectos y tareas. Permite a equipos y empresas organizar su trabajo, asignar tareas y hacer seguimiento del progreso, lo que la convierte en una herramienta de gestión de recursos empresariales a pequeña escala, enfocada en la productividad y organización del trabajo.

## Proyecto Intermodular

- **Objetivo del software**: UpTask es un gestor de proyectos y tareas que permite a los usuarios organizar su trabajo de manera eficiente, con un sistema completo de gestión de usuarios, proyectos y tareas, incluyendo actualización en tiempo real del estado de las tareas.

- **Necesidad que cubre**: Cubre la necesidad de profesionales, equipos y empresas de mantener organizados sus proyectos y tareas en un entorno digital accesible, facilitando el seguimiento del progreso, la asignación de responsabilidades y la gestión eficiente del tiempo y recursos.

- **Stack tecnológico elegido**: He seleccionado un stack LAMP (Linux, Apache, MySQL, PHP) complementado con SASS y JavaScript para el frontend. Esta combinación ofrece un buen equilibrio entre rendimiento, facilidad de desarrollo y mantenimiento, siendo apropiado para una aplicación web de gestión con requisitos moderados de escalabilidad.

- **Desarrollo por versiones**: He planteado el desarrollo en versiones incrementales. La versión 1 incluye la funcionalidad básica de registro, autenticación, creación de proyectos y gestión de tareas. Las actualizaciones posteriores añadirán características como colaboración en proyectos, categorización de tareas, estadísticas de progreso y una interfaz móvil mejorada.
