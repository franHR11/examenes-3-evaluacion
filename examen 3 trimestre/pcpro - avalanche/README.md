# 📧 Avalanche Email Marketing System

¡Bienvenido a **Avalanche Email Marketing**! Este sistema profesional permite gestionar campañas de email marketing de forma eficiente, segura y escalable. Diseñado para empresas, agencias y profesionales que buscan automatizar y optimizar la comunicación con sus contactos.

---

## 📌 Descripción del Proyecto

**Avalanche Email Marketing** es una plataforma web completa para la gestión de campañas de correo electrónico, listas de contactos, plantillas personalizadas, estadísticas avanzadas y administración de usuarios. Pensado tanto para pequeñas empresas como para grandes organizaciones, su objetivo es facilitar la automatización y el análisis de campañas, centralizando la gestión desde un panel intuitivo.

- **¿Qué hace?**
  - Permite crear, enviar y analizar campañas de email.
  - Gestiona listas de contactos y segmentación.
  - Ofrece plantillas editables y seguimiento de aperturas/clics.
  - Proporciona panel de administración y estadísticas en tiempo real.
- **¿Para quién está pensado?**
  - Empresas, agencias de marketing, equipos de ventas y profesionales que necesitan gestionar campañas masivas.
- **Utilidad y enfoque comercial:**
  - Automatización del marketing, mejora de la comunicación, análisis de resultados y optimización de campañas.

---

## ✨ Características Principales

- 🛠️ **Gestión de campañas**: Crea, edita, programa y envía campañas de email.
- 📦 **Listas y segmentación**: Administra contactos y listas, importa/exporta datos.
- 🔒 **Autenticación segura**: Login, registro, recuperación y gestión de usuarios.
- 📊 **Panel de control**: Dashboard con estadísticas y KPIs en tiempo real.
- 🖌️ **Plantillas editables**: Editor visual para emails personalizados.
- 🔗 **Integración tracking**: Seguimiento de aperturas y clics.
- 🗂️ **Gestión de plantillas**: CRUD completo de plantillas de correo.
- 🧑‍💼 **Panel admin**: Administración avanzada de usuarios y ajustes del sistema.
- 🗄️ **Backups y logs**: Sistema de respaldo y registro de eventos.
- 🛡️ **Control de permisos**: Acceso diferenciado para admin/usuarios.

---

## ⚙️ Funcionalidades

- **Módulos principales:**
  - `admin/`: Gestión de usuarios, logs, backups, configuración avanzada.
  - `auth/`: Login, registro, recuperación y gestión de sesiones.
  - `dashboard/`: Panel principal con KPIs y resumen de actividad.
  - `campaigns/`: Creación, edición, envío, duplicado y estadísticas de campañas.
  - `contacts/`: Gestión de contactos, importación/exportación, segmentación.
  - `templates/`: Editor visual, gestión y vista de plantillas.
  - `settings/`: Configuración general del sistema.
  - `profile/`: Gestión de perfil de usuario.
- **Servicios y utilidades:**
  - Envío de emails con PHPMailer.
  - Seguimiento de campañas (tracking de aperturas y clics).
  - Sistema de logs y backups.
  - Scripts de mantenimiento y actualización.
- **Base de datos:**
  - Conexión segura vía PDO a MySQL.
  - Tablas principales: usuarios, campañas, contactos, plantillas, logs, tracking.
- **APIs y scripts:**
  - Integración de rutas centralizadas.
  - Scripts para actualización y mantenimiento de datos.

---

## 🔧 Tecnologías Utilizadas

- 🐘 **PHP** >= 7.4
- 🐬 **MySQL** (vía PDO)
- 📦 **PHPMailer** ^6.8
- 🟦 **HTML5 / CSS3 / JS**
- 🛠️ **Composer** (gestión de dependencias)
- 📁 **PSR-4 Autoloading**
- 🐧 **Linux-ready** (compatible con entornos Windows y Linux)

---

## 🧪 Estructura de Archivos y Carpetas

```
/ (raíz)
├── admin/           # Panel de administración, gestión avanzada
├── assets/          # Recursos estáticos (CSS, JS, imágenes, librerías)
│   ├── css/         # Hojas de estilo
│   ├── js/          # Scripts JS
│   ├── phpmailer/   # Librería PHPMailer
│   └── device-detector/ # Detección de dispositivos
├── backups/         # Copias de seguridad
├── config/          # Configuración (base de datos, rutas, paths)
├── database/        # Scripts SQL y migraciones
├── error/           # Páginas de error personalizadas
├── includes/        # Funciones comunes, rutas, cabecera/pie
├── install/         # Instalador del sistema
├── libs/            # Librerías auxiliares
├── logs/            # Archivos de logs
├── modules/         # Módulos funcionales (admin, auth, campaigns, etc.)
├── scripts/         # Scripts de mantenimiento
├── templates/       # Plantillas de emails y vistas
├── tracking/        # Endpoints de tracking (aperturas/clics)
├── uploads/         # Archivos subidos
├── utils/           # Utilidades y helpers
└── index.php        # Entrada principal
```

---

## 🛠️ Instrucciones de Uso

1. **Clona el repositorio:**
   ```bash
   git clone https://github.com/franHR11/pcpro-avalancheweb.git
   ```
2. **Instala dependencias PHP:**
   ```bash
   composer install
   ```
3. **Configura la base de datos:**
   - Edita `config/config.php` y ajusta los valores de `DB_HOST`, `DB_NAME`, `DB_USER`, `DB_PASS` según tu entorno.
   - Ejecuta los scripts SQL en `/database` para crear las tablas necesarias.
4. **Configura variables de entorno (opcional):**
   - Puedes usar `.env` o variables de entorno para sobreescribir valores sensibles.
   - Ejemplo:
     ```env
     DB_HOST=localhost
     DB_NAME=avalanche
     DB_USER=usuario
     DB_PASS=contraseña
     BASE_URL=https://tusitio.com
     ```
5. **Levanta el servidor local:**
   - Con Laragon, XAMPP o similar, apunta el DocumentRoot a la carpeta del proyecto.
   - Accede a `http://localhost/` o la URL configurada.
6. **Primer acceso:**
   - El sistema detectará si no está instalado y lanzará el instalador automático.
   - Sigue los pasos para crear el usuario administrador y configurar el sistema.
7. **Build/Deploy:**
   - No requiere build frontend, pero puedes minificar CSS/JS en `assets/` si lo deseas.
   - Para producción, asegúrate de poner `APP_DEBUG` en `false` y configurar correctamente los permisos de carpetas (`logs/`, `uploads/`).
8. **Pruebas:**
   - Incluye scripts de diagnóstico y test en `/scripts` y `/debug_lists.php`.

---

## 📝 Ejemplo de Uso

- **Endpoint de login:** `POST /modules/auth/login.php`
- **Creación de campaña:** `POST /modules/campaigns/create.php`
- **Importar contactos:** `POST /modules/contacts/import.php`
- **Obtener estadísticas:** `GET /modules/campaigns/stats.php`

---

## 🗄️ Base de Datos (Resumen)

- **Tablas principales:**
  - `users` (usuarios, roles)
  - `campaigns` (campañas de email)
  - `contacts` (contactos y listas)
  - `templates` (plantillas de correo)
  - `logs` (eventos y auditoría)
  - `tracking` (aperturas, clics)
- **Conexión:**
  - Configurada vía `config/db.php` usando PDO y parámetros de `config/config.php`.

---

## 🔑 Variables de Configuración y Seguridad

- `config/config.php` define:
  - `DB_HOST`, `DB_NAME`, `DB_USER`, `DB_PASS`, `DB_CHARSET`, `DB_PORT`
  - `APP_NAME`, `APP_VERSION`, `APP_DEBUG`, `BASE_URL`, `TRACKING_URL`
- **Nunca expongas valores reales en repositorios públicos. Usa ejemplos.**

---

## 🏷️ Licencia (Español)

Copyright (c) 2025 Francisco José Herreros (franHR) / PCProgramación

Todos los derechos reservados.

Este software es propiedad de Francisco José Herreros (franHR), desarrollador de PCProgramación (https://www.pcprogramacion.es). No está permitido copiar, modificar, distribuir o utilizar este código, ni total ni parcialmente, sin una autorización expresa y por escrito del autor.

El acceso a este repositorio tiene únicamente fines de revisión, auditoría o demostración, y no implica la cesión de ningún derecho de uso o explotación.

Para solicitar una licencia o permiso de uso, contacta con: desarrollo@pcprogramacion.es

---

## 🏷️ License (English)

Copyright (c) 2025 Francisco José Herreros (franHR) / PCProgramación

All rights reserved.

This software is the property of Francisco José Herreros (franHR), developer of PCProgramación (https://www.pcprogramacion.es). You may not copy, modify, distribute, or use this code, in whole or in part, without the express written permission of the author.

Access to this repository is strictly for review, auditing, or demonstration purposes, and does not grant any rights to use or exploit the software.

To request a license or permission, contact: desarrollo@pcprogramacion.es
