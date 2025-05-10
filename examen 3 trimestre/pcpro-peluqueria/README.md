# 💇‍♀️ PCPro - Aplicación de Gestión para Peluquerías

![Logo PCProgramación](https://www.pcprogramacion.es/images/logo-pcprogramacion.png)

## 📝 Descripción del Proyecto

**PCPro App Peluquería** es una aplicación web profesional diseñada específicamente para la gestión integral de salones de belleza y peluquerías. Esta solución ofrece una forma elegante y eficiente de administrar citas, servicios, clientes y el negocio en general.

### 🎯 Para quién está pensado
Esta aplicación está dirigida a:
- Dueños de peluquerías y salones de belleza
- Estilistas independientes
- Cadenas de salones de belleza
- Profesionales de la belleza que desean digitalizar y optimizar su gestión

### 🌟 Utilidad y enfoque comercial
PCPro App Peluquería permite a los negocios:
- Reducir hasta un 70% el tiempo dedicado a la gestión de citas
- Minimizar cancelaciones y ausencias mediante recordatorios automáticos
- Mejorar la experiencia del cliente con un sistema de reservas online 24/7
- Analizar el rendimiento del negocio con informes detallados
- Fidelizar clientes a través de un servicio más organizado y profesional

## ✨ Características Principales

- 📅 **Sistema de citas avanzado**: Gestión inteligente con detección de conflictos y duración de servicios
- 👥 **Gestión de clientes**: Perfiles completos con historial y preferencias
- 💼 **Panel administrativo**: Control total para propietarios y gestores
- 🔒 **Sistema de autenticación**: Registro y login seguro para clientes y administradores
- ⚙️ **Personalización**: Adaptable a la imagen y necesidades específicas del negocio
- 📱 **Diseño responsivo**: Experiencia óptima en cualquier dispositivo
- 🔄 **Verificación de disponibilidad**: Comprobación en tiempo real de horarios
- 📊 **Control de asistencia**: Seguimiento de faltas para mejorar la gestión
- 🎨 **Personalización visual**: Cambio de colores, logotipos e imágenes

## ⚙️ Funcionalidades

### Módulo de Citas
- Creación y gestión de citas con validación de disponibilidad
- Selección de servicios múltiples por cita
- Cálculo automático de duración según servicios seleccionados
- Confirmación de citas para clientes prioritarios
- Sistema de marcado de asistencia/falta

### Módulo de Servicios
- Catálogo de servicios con precios y duración
- Categorización y gestión de servicios
- Asignación de múltiples servicios a una cita

### Módulo de Usuarios/Clientes
- Registro y autenticación de clientes
- Perfiles de usuario con información de contacto
- Historial de citas por cliente
- Control de faltas para gestión de clientes problemáticos

### Panel Administrativo
- Vista de agenda diaria con filtros
- Configuración de horarios de apertura/cierre
- Personalización de la apariencia de la aplicación
- Gestión de clientes y servicios
- Reportes y estadísticas

### Sistema de Configuración
- Ajuste de horarios de apertura/cierre
- Configuración de intervalos de citas
- Personalización de colores, logos e imágenes
- Opciones de horario partido (mañana/tarde)

## 🔧 Tecnologías Utilizadas

### Backend
- 🐘 **PHP 8**: Lenguaje principal de desarrollo
- 🧩 **Patrón MVC**: Arquitectura Modelo-Vista-Controlador personalizada
- 🔄 **Router personalizado**: Sistema de enrutamiento simple y efectivo
- 🐬 **MySQL**: Base de datos relacional
- 📧 **PHPMailer**: Envío de correos electrónicos
- 🌐 **Dotenv**: Gestión de variables de entorno

### Frontend
- 🎨 **SASS/CSS**: Estilos con preprocesador SASS
- 📱 **Diseño responsivo**: Adaptable a diferentes dispositivos
- 🖌️ **Gulp**: Automatización de tareas de desarrollo
- 📦 **JavaScript**: Interactividad y validaciones en el cliente
- 🔄 **Fetch API**: Comunicación con el backend mediante AJAX

### Herramientas de desarrollo
- 🛠️ **Composer**: Gestión de dependencias PHP
- 📦 **NPM**: Gestión de dependencias JavaScript
- 🔄 **Git**: Control de versiones
- 🚀 **Laragon**: Entorno de desarrollo local

## 🧪 Estructura de Archivos y Carpetas

```
pcpro-app-peluqueria/
├── classes/           # Clases auxiliares
├── controllers/       # Controladores MVC (AdminController, APIController, etc.)
├── models/            # Modelos de datos (Usuario, Cita, Servicio, etc.)
├── views/             # Vistas y plantillas
│   ├── admin/         # Vistas del panel administrativo
│   ├── auth/          # Vistas de autenticación
│   ├── cita/          # Vistas de gestión de citas
│   ├── servicios/     # Vistas de servicios
│   └── templates/     # Plantillas reutilizables
├── public/            # Archivos públicos accesibles
│   ├── build/         # Assets compilados (CSS, JS, imágenes)
│   └── index.php      # Punto de entrada
├── src/               # Código fuente para compilar
│   ├── js/            # JavaScript
│   ├── scss/          # Archivos SASS
│   └── img/           # Imágenes sin optimizar
├── includes/          # Archivos de inclusión PHP
├── docs/              # Documentación del proyecto
├── Router.php         # Sistema de enrutamiento
├── gulpfile.js        # Configuración de Gulp
├── composer.json      # Dependencias PHP
└── package.json       # Dependencias JavaScript
```

## 🛠️ Instrucciones de Uso

### Requisitos previos
- PHP 8.0 o superior
- MySQL 5.7 o superior
- Composer
- Node.js y NPM

### Instalación

1. **Clonar el repositorio**
```bash
git clone https://github.com/franHR11/pcpro-app-peluqueria.git
cd pcpro-app-peluqueria
```

2. **Instalar dependencias PHP**
```bash
composer install
```

3. **Instalar dependencias JavaScript**
```bash
npm install
```

4. **Configurar variables de entorno**
```bash
# Crear archivo .env basado en el ejemplo
cp .env.example .env
# Editar .env con los datos de tu entorno
```

5. **Configurar la base de datos**
```sql
CREATE DATABASE pcpro_peluqueria;
# Importar el archivo SQL incluido en /database/schema.sql
```

6. **Compilar assets**
```bash
npm run build
```

7. **Iniciar servidor de desarrollo**
```bash
# Con Laragon, simplemente accede a http://pcpro-app-peluqueria.test
# O usar el servidor integrado de PHP
php -S localhost:8000 -t public
```

### Acceso al sistema

- **Panel de administración**: `/admin` (usuario: admin@test.com, contraseña: password)
- **Área de clientes**: `/` (registro de usuarios disponible)

## 📝 Ejemplo de Uso

### Creación de una cita (API)

```javascript
// Ejemplo de petición para crear una cita
fetch('/api/citas', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    fecha: '2025-05-15',
    hora: '10:00',
    usuarioId: 1,
    servicios: '1,3,5' // IDs de servicios separados por coma
  })
})
.then(response => response.json())
.then(data => console.log(data));
```

### Consulta de disponibilidad horaria

```javascript
// Ejemplo de consulta de horarios disponibles
fetch('/api/horarios-disponibles?fecha=2025-05-15&servicios=1,3')
.then(response => response.json())
.then(horarios => console.log(horarios));
```

## 📝 Licencia

### Español
Copyright (c) 2025 Francisco José Herreros (franHR) / PCProgramación

Todos los derechos reservados.

Este software es propiedad de Francisco José Herreros (franHR), desarrollador de PCProgramación (https://www.pcprogramacion.es). No está permitido copiar, modificar, distribuir o utilizar este código, ni total ni parcialmente, sin una autorización expresa y por escrito del autor.

El acceso a este repositorio tiene únicamente fines de revisión, auditoría o demostración, y no implica la cesión de ningún derecho de uso o explotación.

Para solicitar una licencia o permiso de uso, contacta con: desarrollo@pcprogramacion.es

### English
Copyright (c) 2025 Francisco José Herreros (franHR) / PCProgramación

All rights reserved.

This software is the property of Francisco José Herreros (franHR), developer of PCProgramación (https://www.pcprogramacion.es). You may not copy, modify, distribute, or use this code, in whole or in part, without the express written permission of the author.

Access to this repository is strictly for review, auditing, or demonstration purposes, and does not grant any rights to use or exploit the software.

To request a license or permission, contact: desarrollo@pcprogramacion.es
