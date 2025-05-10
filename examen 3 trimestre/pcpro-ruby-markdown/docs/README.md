# Editor de Markdown con Categorías Jerárquicas

## Descripción Comercial 
Editor Markdown profesional con sistema de categorías jerárquicas para organizar tus documentos de forma eficiente. Ideal para desarrolladores, escritores técnicos y equipos que necesitan una gestión estructurada de su documentación.

## Descripción y Características

El Editor de Markdown es una aplicación web que permite crear, editar y gestionar documentos en formato Markdown con las siguientes características:

- **Editor Markdown completo** con vista previa en tiempo real
- **Sistema de categorías jerárquico** que permite organizar documentos en categorías y subcategorías
- **Gestión de documentos** con descripciones, fechas de creación y modificación
- **Búsqueda y filtrado** de documentos
- **Interfaz amigable y responsive** para trabajar en cualquier dispositivo
- **Sistema de autenticación** para proteger tus documentos

### Sistema de Categorías Jerárquicas

La última actualización del sistema incluye soporte para categorías jerárquicas, lo que permite:

- Crear categorías principales y subcategorías
- Añadir descripciones a las categorías
- Organizar documentos en una estructura de árbol
- Visualizar claramente la jerarquía en la interfaz de usuario
- Mantener la integridad referencial al eliminar categorías

## Sección Técnica

### Requisitos del Sistema

- Servidor web (Apache, Nginx)
- PHP 7.4 o superior
- MySQL 5.7 o superior
- Navegador web moderno

### Instalación

1. Clonar el repositorio en tu servidor web
2. Importar el archivo `markdown_editor.sql` a tu base de datos MySQL
3. Ejecutar el script `subcategories.sql` para añadir soporte de subcategorías
4. Configurar la conexión a la base de datos
5. Acceder a la aplicación a través del navegador

### Estructura del Proyecto

El proyecto sigue una arquitectura modular donde cada funcionalidad se divide en módulos independientes:

```
modules/
  auth/         # Autenticación y usuario
  category/     # Gestión de categorías
  markdown/     # Editor y gestión de documentos
```

Cada módulo contiene su propia estructura MVC:

```
modules/category/
  back/
    controllers/    # Lógica de negocio
    models/         # Acceso a datos
  front/
    css/            # Estilos específicos
    js/             # JavaScript específico
    views/          # Plantillas HTML
```

### Uso del Sistema de Categorías

Para utilizar el sistema jerárquico de categorías:

1. Accede a la sección "Categorías" en el menú principal
2. Para crear una categoría principal, deja el campo "Categoría Padre" en blanco
3. Para crear una subcategoría, selecciona una categoría padre del desplegable
4. Puedes añadir descripciones opcionales a tus categorías
5. Al crear o editar documentos, selecciona la categoría o subcategoría correspondiente

### Mejores Prácticas

- Crea una estructura jerárquica lógica (evita más de dos niveles para mantener la usabilidad)
- Utiliza nombres descriptivos para tus categorías
- Aprovecha el campo de descripción para añadir contexto
- Revisa regularmente tu estructura de categorías para mantenerla organizada 