# 🚀 PCpro Publicaciones Redes Sociales - DeepSeek

## 📘 Descripción del Proyecto

**PCpro Publicaciones Redes Sociales - DeepSeek** es una herramienta web que utiliza inteligencia artificial para generar publicaciones creativas y personalizadas para redes sociales. Pensada para creadores de contenido, agencias de marketing, community managers y empresas que buscan optimizar su presencia digital con textos originales y de alto impacto.

Su utilidad radica en la capacidad de transformar gustos, intereses o palabras clave del usuario en publicaciones breves, ingeniosas y con un tono ácido, humorístico o sarcástico, listas para ser publicadas en redes sociales.

---

## ✨ Características Principales

- 🛠️ **Generación IA**: Publicaciones automáticas usando la API DeepSeek (compatible OpenAI)
- 📦 **Interfaz Web Moderna**: UI responsive, minimalista y fácil de usar
- 🔒 **Variables de Entorno**: Seguridad en la gestión de claves API
- 📊 **Sin Base de Datos**: Procesamiento en memoria, sin almacenamiento persistente
- 🔌 **Integración API**: Backend Node.js con Express para comunicación fluida
- 📝 **Personalización**: Genera textos según preferencias del usuario
- ⚡ **Despliegue Rápido**: Instalación y uso sencillos en local o servidor

---

## ⚙️ Funcionalidades

- **Frontend**: Interfaz web donde el usuario puede escribir o generar publicaciones con IA y publicarlas en pantalla.
- **Backend**: Servidor Express que expone el endpoint `/api/generate-post` para generar textos usando DeepSeek.
- **Generación de Publicaciones**: IA genera textos de máximo 177 caracteres, adaptados a los gustos del usuario.
- **Variables de Entorno**: Uso seguro de `DEEPSEEK_API_KEY` y configuración de puerto.
- **Sin login ni panel admin**: Toda la funcionalidad es anónima y sin persistencia.
- **Documentación y ejemplos**: Incluye documentación técnica y ejemplos de uso.

---

## 🔧 Tecnologías Utilizadas

- 🟦 **Node.js**: Entorno de ejecución para JavaScript
- ⚡ **Express.js**: Framework backend para APIs y servidor web
- 🟩 **JavaScript Vanilla**: Lógica de frontend sin frameworks pesados
- 🎨 **CSS Moderno**: Diseño responsive y accesible
- 🧩 **DeepSeek API**: Generación de textos IA (compatible OpenAI)
- 🌱 **dotenv**: Gestión de variables de entorno
- 🛠️ **Nodemon**: Recarga automática en desarrollo
- 📦 **Axios**: Cliente HTTP para peticiones API

---

## 🧪 Estructura de Archivos y Carpetas

```
/
├── app.js                  # Servidor Express y lógica backend
├── package.json            # Dependencias y scripts
├── .env.example            # Variables de entorno de ejemplo
├── public/                 # Frontend estático
│   ├── index.html          # Página principal
│   └── assets/
│       ├── css/            # Estilos (styles.css)
│       ├── js/             # Lógica frontend (main.js)
│       └── img/            # Imágenes y logos
├── docs/                   # Documentación técnica
│   ├── CONEXIONES_BD.md    # Info sobre conexiones API/BD
│   └── MEMORIAS.md         # Registro de cambios y decisiones
└── node_modules/           # Dependencias instaladas
```

- **/public**: Todo el frontend (HTML, CSS, JS, imágenes)
- **/docs**: Documentación técnica y memorias
- **app.js**: Lógica del backend y rutas API
- **.env.example**: Plantilla para configuración segura

---

## 🛠️ Instrucciones de Uso

### 1. Clonar el repositorio
```bash
git clone https://github.com/franHR11/pcpro-publicaciones-Redes-sociales-deepseek.git
cd pcpro-publicaciones-Redes-sociales-deepseek
```

### 2. Instalar dependencias
```bash
npm install
```

### 3. Configurar variables de entorno
Copia `.env.example` a `.env`.

- Si quieres usar la IA real, pon tu clave DeepSeek o OpenAI:
```env
DEEPSEEK_API_KEY=tu_clave_deepseek
OPENAI_API_KEY=tu_clave_openai
PORT=3000
```
- Si dejas las claves vacías, la app funcionará en modo DEMO y generará publicaciones simuladas.
### 4. Ejecutar en local
```bash
npm start
```
Accede a [http://localhost:3000](http://localhost:3000)

### 5. Build y Deploy
No requiere build. Para producción, ejecuta `npm run serve` en tu servidor Node.js.

---

## 📝 Ejemplo de Uso (API)

**Petición al endpoint:**
```http
POST /api/generate-post
Content-Type: application/json
{
  "userPreferences": "humor negro, tecnología, memes"
}
```
**Respuesta:**
```json
{
  "generatedText": "En un mundo de memes y tecnología, hasta los robots necesitan vacaciones. #HumorNegro"
}
```

---

## 🗄️ Base de Datos
Actualmente **no se utiliza base de datos**. Toda la información se procesa en memoria. Consulta `docs/CONEXIONES_BD.md` para futuras ampliaciones.

---

## 🔑 Variables de Entorno
Ejemplo de `.env`:
```env
# Opcional: Si quieres usar la IA real, pon aquí tu clave de DeepSeek o OpenAI
DEEPSEEK_API_KEY=tu_clave_deepseek
OPENAI_API_KEY=tu_clave_openai
PORT=3000
# Si dejas las claves vacías, la app funcionará en modo DEMO y generará publicaciones simuladas.

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
