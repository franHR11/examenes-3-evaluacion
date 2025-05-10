# 🌪️ PCpro-Tornado: Gestión de Sitios Web

**PCpro-Tornado** es una solución profesional para la gestión centralizada de sitios web, diseñada para agencias, desarrolladores y empresas que necesitan administrar múltiples proyectos digitales de manera eficiente y segura. Su enfoque modular y su panel de control intuitivo permiten controlar usuarios, categorías, estadísticas y accesos desde un único lugar.

---

## 📌 Descripción del Proyecto

- **¿Qué hace?**
  Centraliza la gestión de sitios web, permitiendo CRUD completo, categorización, estadísticas, control de usuarios y acceso rápido a paneles y herramientas asociadas a cada sitio.
- **¿Para quién está pensado?**
  Agencias, desarrolladores freelance, equipos IT y empresas que gestionan varios sitios web.
- **Utilidad y enfoque comercial:**
  Optimiza el tiempo de administración, mejora la seguridad y facilita la supervisión global de proyectos web.

---

## ✨ Características Principales

- 🛠️ **CRUD de Sitios Web:** Añade, edita, elimina y consulta proyectos web fácilmente.
- 📦 **Gestión de Categorías:** Clasifica sitios por tipo, sector o cliente.
- 🔒 **Autenticación Segura:** Login, registro, control de sesiones y roles.
- 👥 **Panel de Usuarios:** Administración avanzada de usuarios y permisos.
- 📊 **Dashboard:** Estadísticas y resumen visual de los sitios.
- 🖼️ **Gestión de Logos:** Subida y asignación de logos personalizados por sitio.
- 🔗 **Acceso Rápido:** Enlaces directos a paneles (admin, Plesk, phpMyAdmin, etc).
- 🕒 **Sesiones Prolongadas:** Mantiene la sesión activa hasta 8 horas.
- 🏷️ **Interfaz Moderna:** Basada en Bootstrap 5 y FontAwesome.

---

## ⚙️ Funcionalidades Detalladas

- **Autenticación y Seguridad:**
  - Registro y login de usuarios (roles: admin, user)
  - Hash de contraseñas y validación de estados (activo, pendiente, bloqueado)
  - Sistema de "recordar sesión" y ping para mantener la sesión activa
- **Panel de Administración:**
  - Gestión de usuarios: listado, filtro, activación/bloqueo, cambio de roles
  - Gestión de sitios web: CRUD completo, asignación de categorías y logos
  - Gestión de categorías: creación, edición, borrado y asignación de iconos
- **Estadísticas y Dashboard:**
  - Visualización de número de sitios, usuarios y categorías
  - Panel visual con Bootstrap y gráficos
- **Integración de Enlaces:**
  - Acceso directo a paneles de administración, Plesk y phpMyAdmin por cada sitio

---

## 🔧 Tecnologías Utilizadas

- 🐘 **PHP** (backend puro, modular)
- 🐬 **MySQL** (base de datos relacional)
- 🟦 **Bootstrap 5** (UI y responsive)
- 🎨 **FontAwesome** (iconos visuales)
- 🌐 **HTML5/CSS3**
- 🛡️ **Sesiones PHP** y validación de entrada

---

## 🧪 Estructura de Archivos y Carpetas

```
/ (raíz)
│
├── index.php              # Página principal (listado público de sitios)
├── admin/                 # Panel de administración
│   ├── assets/            # Recursos estáticos (css, img)
│   ├── config/            # Configuración de base de datos
│   ├── includes/          # Autenticación, cabecera, barra lateral
│   ├── modules/           # CRUD: categories, dashboard, users, websites
│   ├── uploads/           # Logos y archivos subidos
│   ├── login.php          # Login de usuario
│   ├── register.php       # Registro de usuario
│   ├── update-database.php# Scripts de actualización de BD
│   └── ...
├── docs/                  # Documentación técnica
│   ├── CONEXIONES_BD.md   # Esquema y conexión de BD
│   ├── MEMORIAS.md        # Memoria técnica y decisiones
│   └── README.md          # Este archivo
└── ...
```

- **admin/assets/**: CSS y logos
- **admin/config/**: Configuración base de datos
- **admin/includes/**: Lógica de autenticación y UI
- **admin/modules/**: CRUD por módulo (sitios, usuarios, categorías)
- **admin/uploads/**: Logos de los sitios

---

## 🛠️ Instrucciones de Uso

1. **Clona el repositorio**
   ```bash
   git clone https://github.com/franHR11/pcpro-tornado.git
   ```
2. **Configura la base de datos**
   - Crea una base de datos MySQL llamada `tornado`.
   - Importa el archivo `admin/database.sql` o los scripts en `docs/CONEXIONES_BD.md`.
3. **Configura las credenciales**
   - Edita `admin/config/database.php` con tus datos:
     ```php
     define('DB_HOST', 'localhost');
     define('DB_USER', 'usuario');
     define('DB_PASS', 'password');
     define('DB_NAME', 'tornado');
     ```
4. **Levanta el entorno local**
   - Usa Laragon/XAMPP/WAMP o tu stack LAMP preferido.
   - Accede a `http://localhost/pcpro-tornado/`.
5. **Configura usuarios**
   - Accede a `admin/register.php` para crear el primer usuario.
   - Usa `admin/update-users-database.php` para actualizar el sistema de usuarios si es necesario.

---

## 📝 Ejemplo de Uso

- **Endpoint de login:**
  - `POST /admin/login.php` con campos `username` y `password`
- **CRUD de sitios:**
  - Añade, edita y elimina sitios desde el panel `/admin/modules/websites/`
- **Gestión de usuarios:**
  - Cambia roles y estados desde `/admin/modules/users/`

---

## 🗄️ Base de Datos (Resumen)

- **users:** id, username, password (hash), email, name, status, role
- **categories:** id, name, description, icon, created_at
- **websites:** id, category_id, name, description, url, logo, admin_url, plesk_url, phpmyadmin_url

**Ejemplo de conexión:**
```php
// admin/config/database.php
$conn = new mysqli(DB_HOST, DB_USER, DB_PASS, DB_NAME);
```

---

## 📋 Variables de Entorno / Configuración

- `DB_HOST`, `DB_USER`, `DB_PASS`, `DB_NAME`: Parámetros de conexión MySQL (en `admin/config/database.php`)
- **No hay claves API públicas ni .env expuesto por defecto.**

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
