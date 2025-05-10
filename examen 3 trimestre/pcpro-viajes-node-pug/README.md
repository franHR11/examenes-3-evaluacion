# 🌍 Agencia de Viajes Node.js

¡Bienvenido a **Agencia de Viajes**! Este proyecto es una aplicación web moderna desarrollada con Node.js y Express, diseñada para gestionar y mostrar destinos turísticos, testimonios de clientes y promociones de viajes de manera profesional y visualmente atractiva.

---

## 📌 Descripción del Proyecto

**¿Qué hace este proyecto?**

Esta plataforma permite a los usuarios:
- Explorar destinos turísticos destacados con información detallada y visual.
- Leer y agregar testimonios de clientes reales.
- Consultar promociones y detalles de viajes disponibles.

**¿Para quién está pensado?**
- Agencias de viajes, operadores turísticos y empresas del sector turismo.
- Clientes interesados en reservar viajes y conocer experiencias previas.

**Utilidad y enfoque comercial:**
- Mejora la presencia digital de agencias de viajes.
- Facilita la interacción y confianza con clientes potenciales.
- Permite mostrar ofertas y captar leads mediante formularios de testimonios.

---

## ✨ Características Principales

- 🛠️ **Gestión de destinos turísticos**
- 📦 **Listado y detalle de viajes**
- 🔒 **Formulario de testimonios con validación**
- 📊 **Panel visual de promociones**
- 🖥️ **Interfaz responsive y moderna (Bootstrap + Pug)**
- 🗄️ **Integración con base de datos MySQL**
- 📨 **Sistema de rutas y controladores Express**
- 🖼️ **Gestión de imágenes y recursos visuales**

---

## ⚙️ Funcionalidades

- **Página principal:** Slider visual, sección de "Sobre Nosotros", bloque de viajes destacados y testimonios recientes.
- **Página de viajes:** Listado de todos los viajes disponibles, con detalles (precio, fechas, imagen, descripción, plazas disponibles).
- **Página de detalle de viaje:** Información ampliada de cada destino.
- **Página de testimonios:** Visualización y formulario para agregar opiniones de clientes (con validación y persistencia en BD).
- **Sistema de rutas:** Navegación amigable con URLs limpias y slugs para los viajes.
- **Backend:** Controladores para lógica de negocio, modelos Sequelize para acceso y manipulación de datos.
- **Base de datos:** Modelos `viajes` y `testimoniales`.

---

## 🔧 Tecnologías Utilizadas

- 🟦 **Node.js**
- 🚂 **Express.js**
- 🐘 **Sequelize** (ORM)
- 🐬 **MySQL**
- 🐦 **Pug** (motor de plantillas)
- 🎨 **Bootstrap** (CSS framework)
- 📦 **Nodemon** (dev)

**Dependencias principales:**
- `express`, `mysql2`, `sequelize`, `pug`, `nodemon`

---

## 🧪 Estructura de Archivos y Carpetas

```
/
├── config/           # Configuración de base de datos
│   └── db.js
├── controllers/      # Lógica de negocio y controladores de rutas
│   ├── paginasController.js
│   └── testimonialController.js
├── models/           # Modelos Sequelize (ORM)
│   ├── Viaje.js
│   └── testimoniales.js
├── public/           # Archivos estáticos (CSS, imágenes)
│   ├── css/
│   └── img/
├── routes/           # Definición de rutas Express
│   └── index.js
├── views/            # Vistas Pug (plantillas)
│   ├── inicio.pug
│   ├── nosotros.pug
│   ├── viajes.pug
│   ├── viaje.pug
│   ├── testimoniales.pug
│   └── layout/
├── index.js          # Punto de entrada principal
├── package.json      # Dependencias y scripts
└── ...
```

- **config/**: Configuración de la conexión a MySQL.
- **controllers/**: Lógica de negocio de páginas y testimonios.
- **models/**: Definición de tablas y relaciones.
- **public/**: Recursos públicos (CSS, imágenes, etc.).
- **routes/**: Definición de rutas de la app.
- **views/**: Plantillas Pug para renderizado del frontend.

---

## 🛠️ Instrucciones de Uso

### 1. Clonar el repositorio
```bash
git clone <url-del-repo>
cd pcpro-agenciaviajes
```

### 2. Instalar dependencias
```bash
npm install
```

### 3. Configurar variables de entorno
Crea un archivo `.env` en la raíz (opcional, si quieres personalizar la configuración):

```
PORT=5002
DB_HOST=127.0.0.1
DB_PORT=3306
DB_USER=franhr
DB_PASS=franhr
DB_NAME=agenciaviajes
```

> **Nota:** Por defecto, la configuración de conexión está en `config/db.js`.

### 4. Levantar el proyecto en local
```bash
npm run dev
```
La app estará disponible en [http://localhost:5002](http://localhost:5002)

### 5. Base de datos
- Asegúrate de tener MySQL levantado y una base de datos llamada `agenciaviajes`.
- Tablas principales:
  - `viajes`: título, precio, fechas, imagen, descripción, plazas disponibles, slug.
  - `testimoniales`: nombre, correo, mensaje.
- Puedes usar Sequelize para sincronizar los modelos.

### 6. Build y Deploy
Este proyecto está pensado para entorno de desarrollo. Para producción, adapta la configuración y usa un proceso como PM2 o un servidor Node.js dedicado.

---

## 📝 Ejemplo de Uso

### Endpoint para agregar testimonial

- **POST** `/testimoniales`
- Parámetros: `nombre`, `correo`, `mensaje`
- Respuesta: Renderiza la página con el nuevo testimonial o errores de validación.

---

## 📄 Licencia (Español)

Copyright (c) 2025 Francisco José Herreros (franHR) / PCProgramación

Todos los derechos reservados.

Este software es propiedad de Francisco José Herreros (franHR), desarrollador de PCProgramación (https://www.pcprogramacion.es). No está permitido copiar, modificar, distribuir o utilizar este código, ni total ni parcialmente, sin una autorización expresa y por escrito del autor.

El acceso a este repositorio tiene únicamente fines de revisión, auditoría o demostración, y no implica la cesión de ningún derecho de uso o explotación.

Para solicitar una licencia o permiso de uso, contacta con: desarrollo@pcprogramacion.es

---

## 📄 License (English)

Copyright (c) 2025 Francisco José Herreros (franHR) / PCProgramación

All rights reserved.

This software is the property of Francisco José Herreros (franHR), developer of PCProgramación (https://www.pcprogramacion.es). You may not copy, modify, distribute, or use this code, in whole or in part, without the express written permission of the author.

Access to this repository is strictly for review, auditing, or demonstration purposes, and does not grant any rights to use or exploit the software.

To request a license or permission, contact: desarrollo@pcprogramacion.es
