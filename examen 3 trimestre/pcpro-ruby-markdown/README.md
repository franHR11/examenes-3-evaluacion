# 📝 Editor de Markdown Privado

![PHP](https://img.shields.io/badge/PHP-8.0+-777BB4?style=for-the-badge&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)

## 📌 Descripción del Proyecto

El **Editor de Markdown Privado** es una aplicación web desarrollada en PHP que permite a los usuarios crear, editar, organizar y visualizar documentos en formato Markdown. Esta herramienta está diseñada para equipos de trabajo, desarrolladores, escritores técnicos y creadores de contenido que necesitan un sistema centralizado para gestionar su documentación técnica, guías, manuales o cualquier tipo de contenido formateado en Markdown.

Este sistema ofrece un enfoque modular y seguro, con autenticación de usuarios, categorización de documentos y una interfaz de edición intuitiva que mejora el flujo de trabajo para la creación de documentación.

### 🎯 Para quién está pensado

- Equipos de desarrollo que necesitan mantener documentación técnica
- Escritores técnicos que trabajan con formato Markdown
- Empresas que requieren un sistema privado para gestionar manuales y guías
- Bloggers y creadores de contenido que prefieren escribir en Markdown

### 🚀 Utilidad y enfoque comercial

La aplicación ofrece una alternativa privada y autogestionada a servicios en la nube, permitiendo a las empresas mantener el control total sobre su documentación y datos. La gestión de permisos de usuario y la organización por categorías facilita la colaboración en equipos de cualquier tamaño.

## ✨ Características Principales

- 🔒 **Sistema de autenticación seguro** con protección de rutas y sesiones
- 📂 **Organización jerárquica** con categorías y subcategorías para una gestión avanzada
- 📝 **Editor integrado** con vista previa en tiempo real
- 🎨 **Visualización estilizada** con colores personalizados para los encabezados
- 📑 **Tabla de contenidos automática** con colores diferenciados según nivel de encabezado
- 🔍 **Búsqueda y filtrado** por título y categoría
- 📄 **Paginación intuitiva** para navegar por grandes colecciones de documentos
- 📋 **Botón de copiar código** para bloques de código (especialmente SQL)
- 📦 **Almacenamiento dual** en base de datos y sistema de archivos
- 🔗 **Enlaces internos mejorados** con navegación suave entre secciones
- 📱 **Diseño responsive** adaptable a diferentes dispositivos
- ⬆️ **Botón de scroll rápido** para navegar fácilmente en documentos extensos

## ⚙️ Funcionalidades

### 📋 Gestión de Documentos

- **Crear documentos** con título, descripción, contenido y categoría
- **Editar documentos** existentes con actualización automática de fecha
- **Eliminar documentos** con confirmación para prevenir eliminaciones accidentales
- **Visualizar documentos** con formato Markdown renderizado
- **Descargar documentos** en formato .md para uso local
- **Navegar por páginas** con un sistema de paginación para organizar grandes colecciones

### 🗂️ Gestión de Categorías

- **Crear categorías** para organizar documentos
- **Establecer jerarquías** con categorías principales y subcategorías
- **Visualización estructurada** con subcategorías agrupadas visualmente bajo sus categorías padre
- **Editar categorías** existentes
- **Eliminar categorías** (con validación para evitar eliminar categorías con documentos)
- **Filtrar documentos** por categoría principal o subcategoría

### 👤 Sistema de Usuarios

- **Login seguro** con contraseñas hasheadas
- **Protección de rutas** que requieren autenticación
- **Sesiones persistentes** para mayor comodidad

### 🎨 Presentación y UX

- **Colores personalizados** para diferentes niveles de encabezados
- **Tabla de contenidos automática** generada a partir de los encabezados del documento
- **Navegación por colores** que facilita la identificación de la estructura jerárquica
- **Estilos especiales** para bloques de código SQL
- **Botones de copiar** para código
- **Navegación mejorada** con enlaces internos
- **Botón de retorno rápido** para documentos extensos
- **Interfaz limpia** y fácil de usar
- **Paginación intuitiva** con indicadores claros de páginas actuales y totales

## 🔧 Tecnologías Utilizadas

- 🐘 **PHP** como lenguaje principal de backend
- 🐬 **MySQL** para almacenamiento persistente
- 🔄 **Vanilla JavaScript** para interacciones del lado del cliente
- 📄 **HTML5 & CSS3** para la estructura y presentación
- 📝 **Marked.js** para renderizado de Markdown a HTML
- ✏️ **EasyMDE** como editor de Markdown con vista previa
- 🔐 **BCrypt** para hash seguro de contraseñas
- 🧩 **Arquitectura MVC modular** para organización del código

## 🧪 Estructura de Archivos y Carpetas

```
pcpro-ruby/
├── config/               # Configuraciones globales
│   ├── config.php        # Configuración principal
│   └── database.php      # Configuración de base de datos
├── core/                 # Funciones principales del sistema
│   ├── functions.php     # Funciones helpers
│   └── router.php        # Sistema de enrutamiento
├── docs/                 # Documentación del proyecto
├── markdowns/            # Archivos markdown físicos
├── modules/              # Módulos del sistema (estructura MVC)
│   ├── auth/             # Módulo de autenticación
│   │   ├── back/         # Backend (controllers, models)
│   │   └── front/        # Frontend (views, css, js)
│   ├── category/         # Módulo de categorías
│   │   ├── back/
│   │   └── front/
│   └── markdown/         # Módulo principal de documentos
│       ├── back/
│       └── front/
├── public/               # Archivos públicos
│   ├── css/              # Hojas de estilo
│   ├── js/               # Scripts JavaScript
│   └── lib/              # Bibliotecas de terceros
├── create_user_script.php # Script para crear usuarios
├── generate_hash.php     # Utilidad para generar hashes
├── index.php             # Punto de entrada principal
└── markdown_editor.sql   # Esquema de la base de datos
```

## 🛠️ Instrucciones de Uso

### Requisitos previos

- PHP 7.4 o superior
- MySQL 5.7 o superior
- Servidor web (Apache, Nginx)

### Instalación

1. **Clonar el repositorio**

```bash
git clone https://github.com/tu-usuario/pcpro-ruby.git
cd pcpro-ruby
```

2. **Crear la base de datos**

```bash
mysql -u root -p < markdown_editor.sql
```

3. **Configurar la conexión a la base de datos**

Editar el archivo `config/database.php` con los datos de conexión:

```php
define('DB_HOST', 'localhost');
define('DB_NAME', 'ruby');  // O el nombre que hayas elegido
define('DB_USER', 'root');  // Tu usuario de MySQL
define('DB_PASS', '');      // Tu contraseña de MySQL
```

4. **Configurar la URL base**

Editar el archivo `config/config.php`:

```php
define('BASE_URL', 'http://tu-dominio.com/');  // O http://localhost/pcpro-ruby/
```

5. **Configurar permisos de escritura**

```bash
chmod 755 markdowns
```

6. **Acceder a la aplicación**

Visita la URL configurada en tu navegador:
- **Usuario por defecto**: admin
- **Contraseña por defecto**: admin123

### Uso básico

1. **Iniciar sesión** con las credenciales proporcionadas
2. **Crear categorías** para organizar tus documentos
3. **Crear subcategorías** para una organización más detallada
4. **Crear documentos Markdown** utilizando el editor integrado
5. **Visualizar documentos** con formato renderizado
6. **Buscar y filtrar** para encontrar documentos específicos
7. **Navegar por páginas** cuando la colección de documentos sea extensa

## 📝 Ejemplos de Uso

### Crear un nuevo documento con código SQL

1. Accede a la sección "Crear Documento"
2. Completa el formulario con título y descripción
3. En el contenido, puedes incluir bloques de código SQL:

````markdown
# Consulta de usuarios activos

La siguiente consulta SQL muestra todos los usuarios activos:

```sql
SELECT username, email, last_login 
FROM users 
WHERE status = 'active' 
ORDER BY last_login DESC;
```
````

4. Al visualizar el documento, el código SQL tendrá un estilo especial y un botón para copiarlo.

### Organizar documentos con categorías y subcategorías

Para crear una estructura jerárquica de documentación:

1. Primero crea categorías principales como "Desarrollo", "Marketing", "Administración"
2. Luego crea subcategorías dentro de cada categoría principal:
   - Bajo "Desarrollo": "Frontend", "Backend", "DevOps"
   - Bajo "Marketing": "SEO", "Redes Sociales", "Email Marketing"
3. Al crear o editar documentos, selecciona la categoría o subcategoría correspondiente
4. En el listado de documentos, verás una estructura jerárquica clara con las subcategorías agrupadas visualmente bajo sus categorías padre

### Documentos con tabla de contenidos automática

Todos los documentos con encabezados generan automáticamente una tabla de contenidos, facilitando la navegación:

```markdown
# Manual de Usuario

## 1. Introducción
Contenido de introducción...

## 2. Instalación y preparación
Pasos para instalar...

### 2.1 Requisitos previos
Lista de requisitos...

### 2.2 Pasos para la instalación
Instrucciones detalladas...

## 3. Estructura de un proyecto
Explicación de la estructura...
```

El documento generará una tabla de contenidos con enlaces a cada sección, coloreada según el nivel jerárquico.

### Usar enlaces internos en documentos

Puedes crear un índice al inicio de tu documento y enlazar a secciones dentro del mismo:

```markdown
## Índice

1. [Introducción](#1-introducción)
2. [Requisitos](#2-requisitos)
3. [Instalación](#3-instalación)

## 1. Introducción

Contenido de la introducción...

## 2. Requisitos

Listado de requisitos...

## 3. Instalación

Pasos de instalación...
```

## Licencia

Copyright (c) 2025 Francisco José Herreros (franHR) / PCProgramación

Todos los derechos reservados.

Este software es propiedad de Francisco José Herreros (franHR), desarrollador de PCProgramación (https://www.pcprogramacion.es). No está permitido copiar, modificar, distribuir o utilizar este código, ni total ni parcialmente, sin una autorización expresa y por escrito del autor.

El acceso a este repositorio tiene únicamente fines de revisión, auditoría o demostración, y no implica la cesión de ningún derecho de uso o explotación.

Para solicitar una licencia o permiso de uso, contacta con: desarrollo@pcprogramacion.es
