# 🛒 PCpro - Chatbot para Supermercado

[![Node.js](https://img.shields.io/badge/Node.js-v16+-green.svg)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-v4.21+-blue.svg)](https://expressjs.com/)
[![OpenAI](https://img.shields.io/badge/OpenAI-API-orange.svg)](https://openai.com/)

![Banner del Proyecto](https://via.placeholder.com/800x200/30475d/9ba5ac?text=PCpro+Chatbot+para+Supermercado)

## 📋 Tabla de Contenido

- [Descripción](#-descripción)
- [Características Principales](#-características-principales)
- [Funcionalidades](#-funcionalidades)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación y Configuración](#-instalación-y-configuración)
- [Personalización](#-personalización)
- [Arquitectura](#-arquitectura)
- [Documentación Adicional](#-documentación-adicional)
- [Preguntas Frecuentes](#-preguntas-frecuentes)
- [Licencia](#-licencia)

## 🔍 Descripción

PCpro Chatbot es una **solución innovadora de atención al cliente automatizada** diseñada específicamente para supermercados y tiendas de alimentación. Esta aplicación web integra tecnología avanzada de inteligencia artificial para proporcionar respuestas instantáneas y precisas a las consultas de los clientes sobre horarios, productos disponibles, ubicación, métodos de pago y más.

Desarrollada con Node.js y la API de OpenAI, esta herramienta puede funcionar 24/7, reduciendo la carga de trabajo del personal de atención al cliente y mejorando significativamente la experiencia del usuario en la web o aplicación de tu negocio.

## ✨ Características Principales

- **🤖 IA Avanzada**: Utiliza el modelo GPT-3.5 Turbo de OpenAI para respuestas naturales e inteligentes
- **⚡ Respuestas Instantáneas**: Sin tiempos de espera para los clientes
- **📱 Diseño Responsivo**: Experiencia óptima en cualquier dispositivo
- **🔒 Contexto Controlado**: Solo responde preguntas relacionadas con el negocio
- **💬 Conversaciones Fluidas**: Mantiene el historial para ofrecer respuestas contextualizadas
- **🛠️ Fácil Personalización**: Adapta la información a las necesidades específicas de tu negocio
- **📊 Optimización de Tokens**: Configurado para minimizar costos de API

## 🚀 Funcionalidades

### Para Usuarios Finales
- **Consulta de Información Básica**: Horarios, ubicación, métodos de pago
- **Consulta de Productos**: Disponibilidad y marcas
- **Interfaz Intuitiva**: Diseño tipo chat familiar para cualquier usuario
- **Experiencia Conversacional**: Mantiene el contexto de la conversación

### Para Administradores
- **Personalización del Contexto**: Modifica fácilmente la información del negocio
- **Gestión de Conversaciones**: Sistema de control de sesiones por ID de usuario
- **Optimización de Recursos**: Limitación de tokens y mensajes para controlar costos
- **Fácil Implementación**: Despliegue sencillo en cualquier servidor Node.js

## 💻 Tecnologías Utilizadas

| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| Node.js    | v16+    | Entorno de ejecución del servidor |
| Express    | v4.21+  | Framework web para la API REST |
| OpenAI API | Último  | Motor de inteligencia artificial |
| HTML5      | -       | Estructura de la interfaz de usuario |
| CSS3       | -       | Estilos visuales responsivos |
| JavaScript | ES6+    | Lógica del cliente y servidor |
| dotenv     | v16.4+  | Gestión de variables de entorno |

## 📋 Requisitos Previos

- Node.js (v16 o superior)
- npm o yarn
- Cuenta en OpenAI con acceso a API
- API Key de OpenAI
- Conexión a internet para las llamadas a la API

## 🔧 Instalación y Configuración

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/pcpro-ia-comercio.git
cd pcpro-ia-comercio
```

### 2. Instalar dependencias

```bash
npm install
```

### 3. Configurar variables de entorno

```bash
cp .env.example .env
```

Edita el archivo `.env` y añade tu API Key de OpenAI:

```
OPENAI_API_KEY=tu_clave_api_de_openai
PORT=3000
```

### 4. Iniciar el servidor

Para desarrollo (con recarga automática):
```bash
npm start
```

Para producción:
```bash
npm run serve
```

### 5. Acceder a la aplicación

Abre tu navegador web y visita:
```
http://localhost:3000
```

## 🎨 Personalización

### Modificar la información del negocio

Edita el archivo `app.js` y busca el bloque de código con la constante `context`:

```javascript
const context = `
Eres un asistente de soporte para un supermercado.

Informacion del negocio:

 - Ubicacion: [TU DIRECCIÓN]
 - horario: [TUS HORARIOS]
 - productos: [TUS PRODUCTOS]
 - Marcas: [TUS MARCAS]
 - metodos de pago: [TUS MÉTODOS DE PAGO]
Solo puedes responder preguntas sobre la tienda, cualquier otra pregunta esta prohibida.
`;
```

### Personalizar la interfaz

Los estilos visuales pueden modificarse en el archivo `public/assets/css/styles.css`.

## 🏗️ Arquitectura

El sistema está estructurado en tres componentes principales:

```
+------------------+     +------------------+     +------------------+
|                  |     |                  |     |                  |
|  Cliente (HTML,  |     |  Servidor Node   |     |    API OpenAI    |
|   CSS, JS)       | --> |    (Express)     | --> |    (GPT-3.5)     |
|                  |     |                  |     |                  |
+------------------+     +------------------+     +------------------+
        ^                        |                        |
        |                        v                        v
+------------------+     +------------------+     +------------------+
|                  |     |                  |     |                  |
|  Interfaz de     |     |  Gestión de      |     |  Procesamiento  |
|  Usuario         |     |  Conversaciones  |     |  de Lenguaje    |
|                  |     |                  |     |  Natural         |
+------------------+     +------------------+     +------------------+
```

### Estructura de Archivos

```
pcpro-ia-comercio/
├── app.js                   # Punto de entrada y lógica del servidor
├── .env                     # Variables de entorno (no incluido en Git)
├── .env.example             # Plantilla para variables de entorno
├── package.json             # Dependencias y scripts
├── public/                  # Frontend de la aplicación
│   ├── index.html           # Estructura HTML
│   └── assets/              # Recursos estáticos
│       ├── css/             # Estilos CSS
│       │   └── styles.css   # Estilos principales
│       ├── js/              # JavaScript del cliente
│       │   └── main.js      # Lógica del frontend
│       └── img/             # Imágenes del proyecto
│           └── logo.png     # Logo del chatbot
└── docs/                    # Documentación detallada
    ├── README.md            # Guía completa
    ├── MEMORIAS.md          # Registro de cambios
    └── CONEXIONES_BD.md     # Documentación de bases de datos
```

## 📚 Documentación Adicional

Para información más detallada sobre el proyecto, consulta:

- [📖 Guía Completa](docs/README.md) - Documentación detallada del proyecto
- [📝 Registro de Cambios](docs/MEMORIAS.md) - Historial de cambios y decisiones técnicas
- [🗄️ Base de Datos](docs/CONEXIONES_BD.md) - Gestión de datos actual y propuestas futuras

## ❓ Preguntas Frecuentes

### ¿Puedo usar este chatbot sin conocimientos de programación?
Sí, la configuración básica solo requiere modificar texto en un archivo y disponer de una API Key de OpenAI.

### ¿Cuánto cuesta operar este chatbot?
El coste depende del uso que tenga. La configuración actual limita las respuestas a 200 tokens para optimizar costos. Consulta los precios actuales en la web de OpenAI.

### ¿El chatbot aprende con el tiempo?
No, este chatbot utiliza GPT-3.5 con un contexto fijo. No aprende específicamente de las conversaciones anteriores más allá del histórico de la sesión actual.

### ¿Cómo puedo añadir más productos o servicios?
Modifica el texto en la constante `context` del archivo `app.js` para incluir más información específica de tu negocio.

### ¿Las conversaciones se guardan permanentemente?
No, en esta versión las conversaciones se mantienen en memoria y se pierden al reiniciar el servidor. Para persistencia, consulta el documento [CONEXIONES_BD.md](docs/CONEXIONES_BD.md).

## 📄 Licencia

Este proyecto está licenciado bajo los términos de la licencia ISC. Ver el archivo `package.json` para más detalles.
