# 📋 UpTask - Gestor de Proyectos y Tareas

![UpTask Logo](https://www.pcprogramacion.es/images/logo.png)

## 📝 Descripción del Proyecto

UpTask es una aplicación web completa para la gestión eficiente de proyectos y tareas, desarrollada por PCProgramación. Diseñada para profesionales, equipos y empresas que necesitan organizar su trabajo, UpTask permite crear proyectos, asignar tareas y monitorear su progreso en tiempo real.

### ¿Para quién está pensado?
- 👨‍💼 Profesionales independientes
- 👥 Equipos de trabajo pequeños y medianos
- 🏢 Empresas que necesitan organizar sus proyectos

### Utilidad y enfoque comercial
UpTask simplifica la gestión de proyectos permitiendo a sus usuarios aumentar la productividad, reducir el tiempo de seguimiento y mejorar la organización de tareas. Ideal para entornos donde se requiere una herramienta ligera pero potente para la gestión del trabajo.

## ✨ Características Principales

- 🔐 **Sistema de autenticación completo**: Registro, login, confirmación por email y recuperación de contraseña
- 📂 **Gestión de proyectos**: Creación y administración de múltiples proyectos por usuario
- ✅ **Administración de tareas**: Creación, actualización y eliminación de tareas dentro de cada proyecto
- 🔄 **Actualización en tiempo real**: Cambio de estado de tareas sin necesidad de recargar la página
- 👤 **Perfiles de usuario**: Gestión de información personal y cambio de contraseña
- 🛡️ **Seguridad integrada**: Protección de rutas y validación de propietarios de proyectos
- 📱 **Diseño responsive**: Funcional en dispositivos móviles y de escritorio

## ⚙️ Funcionalidades

### Sistema de Usuarios
- **Registro de usuarios** con validación de campos y confirmación por email
- **Inicio de sesión** seguro con verificación de credenciales
- **Recuperación de contraseña** mediante token único enviado por email
- **Gestión de perfil**: Actualización de datos personales
- **Cambio de contraseña** con validación de seguridad

### Gestión de Proyectos
- **Dashboard** para visualizar todos los proyectos del usuario
- **Creación de proyectos** con validación de campos
- **URL única** para cada proyecto mediante token generado automáticamente
- **Protección de acceso**: Solo el propietario puede acceder a sus proyectos

### Sistema de Tareas
- **API REST** para gestión de tareas (CRUD completo)
- **Listado de tareas** por proyecto
- **Creación de tareas** asociadas a proyectos específicos
- **Actualización de estado** (pendiente/completada) mediante interfaz interactiva
- **Eliminación de tareas** con confirmación

## 🔧 Tecnologías Utilizadas

### Backend
- 🐘 **PHP 8**: Lenguaje de programación principal
- 🧩 **MVC**: Arquitectura Modelo-Vista-Controlador personalizada
- 🔐 **PHPMailer**: Para envío de emails de confirmación y recuperación

### Frontend
- 🎨 **SASS**: Preprocesador CSS para estilos
- 🛠️ **Gulp**: Automatización de tareas (compilación de SASS, minificación)
- 📱 **CSS Grid/Flexbox**: Para diseño responsive
- 🔄 **JavaScript**: Interactividad y comunicación con API

### Base de Datos
- 🐬 **MySQL**: Sistema de gestión de base de datos relacional

### Herramientas de Desarrollo
- 📦 **Composer**: Gestión de dependencias PHP
- 📦 **NPM**: Gestión de dependencias JavaScript

## 🧪 Estructura de Archivos y Carpetas

```
pcpro-uptask/
├── classes/           # Clases auxiliares (Email, etc.)
├── controllers/       # Controladores de la aplicación
│   ├── DashboardController.php
│   ├── LoginController.php
│   └── TareaController.php
├── includes/          # Archivos de configuración y funciones
├── models/            # Modelos para interactuar con la base de datos
│   ├── ActiveRecord.php
│   ├── Proyecto.php
│   ├── Tarea.php
│   └── Usuario.php
├── public/            # Punto de entrada y assets públicos
│   ├── build/         # Archivos compilados (CSS, JS)
│   └── index.php      # Punto de entrada principal
├── src/               # Archivos fuente para frontend
│   ├── js/            # JavaScript
│   └── scss/          # Estilos SASS
├── vendor/            # Dependencias de Composer
├── views/             # Vistas de la aplicación
│   ├── auth/          # Vistas de autenticación
│   ├── dashboard/     # Vistas del panel principal
│   └── templates/     # Plantillas reutilizables
├── Router.php         # Sistema de enrutamiento
├── composer.json      # Configuración de dependencias PHP
├── package.json       # Configuración de dependencias JavaScript
└── gulpfile.js        # Configuración de tareas de Gulp
```

## 🛠️ Instrucciones de Uso

### Requisitos previos
- PHP 8.0 o superior
- MySQL/MariaDB
- Composer
- Node.js y NPM

### Instalación

1. Clonar el repositorio:
```bash
git clone https://github.com/franHR11/pcpro-uptask.git
cd pcpro-uptask
```

2. Instalar dependencias PHP:
```bash
composer install
```

3. Instalar dependencias JavaScript:
```bash
npm install
```

4. Configurar base de datos:
   - Crear una base de datos MySQL
   - Importar el esquema (consultar documentación)
   - Configurar las credenciales en el archivo de configuración correspondiente

5. Configurar variables de entorno:
   - Crear archivo `.env` basado en `.env.example` si está disponible
   - Configurar credenciales de base de datos y servidor SMTP para emails

### Desarrollo

1. Iniciar el servidor de desarrollo:
```bash
php -S localhost:3000 -t public
```

2. Compilar assets y observar cambios:
```bash
npm run dev
```

### Producción

1. Compilar assets para producción:
```bash
npm run build
```

2. Configurar un servidor web (Apache/Nginx) apuntando al directorio `public/`

## 📝 Ejemplo de Uso

### Creación de un proyecto
1. Iniciar sesión con tu cuenta
2. En el dashboard, hacer clic en "Crear Proyecto"
3. Ingresar nombre del proyecto
4. El sistema generará una URL única para acceder al proyecto

### Gestión de tareas
```javascript
// Ejemplo de creación de tarea con la API
fetch('/api/tarea', {
    method: 'POST',
    body: JSON.stringify({
        nombre: 'Nueva tarea',
        proyectoId: 'id-del-proyecto'
    }),
    headers: {
        'Content-Type': 'application/json'
    }
})
.then(respuesta => respuesta.json())
.then(datos => {
    // Procesar respuesta
});
```

## 📜 Licencia Español

Copyright (c) 2025 Francisco José Herreros (franHR) / PCProgramación

Todos los derechos reservados.

Este software es propiedad de Francisco José Herreros (franHR), desarrollador de PCProgramación (https://www.pcprogramacion.es). No está permitido copiar, modificar, distribuir o utilizar este código, ni total ni parcialmente, sin una autorización expresa y por escrito del autor.

El acceso a este repositorio tiene únicamente fines de revisión, auditoría o demostración, y no implica la cesión de ningún derecho de uso o explotación.

Para solicitar una licencia o permiso de uso, contacta con: desarrollo@pcprogramacion.es

## 📜 Licencia Ingles

Copyright (c) 2025 Francisco José Herreros (franHR) / PCProgramación

All rights reserved.

This software is the property of Francisco José Herreros (franHR), developer of PCProgramación (https://www.pcprogramacion.es). You may not copy, modify, distribute, or use this code, in whole or in part, without the express written permission of the author.

Access to this repository is strictly for review, auditing, or demonstration purposes, and does not grant any rights to use or exploit the software.

To request a license or permission, contact: desarrollo@pcprogramacion.es