# 🌐 PCpro Traductor IA - DeepSeek

## 🚀 Sección Comercial
¡Rompe las barreras del idioma con inteligencia artificial! Esta aplicación web te permite traducir texto entre diferentes idiomas utilizando la avanzada IA de DeepSeek. Ideal para:

- 🌍 Comunicarte globalmente sin limitaciones
- 📚 Entender contenido en idiomas extranjeros
- 🎓 Aprender nuevos idiomas de forma interactiva
- 💼 Mejorar comunicaciones de negocios internacionales

## 📋 Descripción y Características

Este proyecto es una aplicación web elegante y funcional que ofrece traducción de texto en tiempo real mediante IA avanzada.

### ✨ Funcionalidades Principales

- 📝 **Interfaz de Chat Intuitiva**: Diseño amigable tipo chat que muestra tanto el texto original como la traducción
- 🔄 **Indicador de Traducción**: Muestra "Traduciendo..." mientras procesa tu solicitud
- 🌐 **Múltiples Idiomas**: Soporte para una amplia variedad de idiomas
- ⚡ **Respuesta Rápida**: Utiliza API DeepSeek para traducción instantánea
- 🧠 **IA de Alta Precisión**: Traducciones de calidad profesional

## 💻 Sección Técnica

### 🛠️ Tecnologías Utilizadas

- **Backend**: `Node.js`, `Express.js`
- **Frontend**: JavaScript Vanilla, HTML5, CSS3
- **API de IA**: DeepSeek (a través de cliente compatible con OpenAI)
- **Gestión de Configuración**: Variables de entorno con `dotenv`

### 📁 Estructura del Proyecto

```
/
├── app.js                # Servidor Express y lógica de backend
├── public/               # Archivos estáticos del frontend
│   ├── index.html        # Página principal
│   └── assets/
│       ├── css/          # Estilos CSS
│       ├── js/           # Scripts JavaScript
│       │   └── main.js   # Lógica de traducción del frontend
│       └── img/          # Imágenes y recursos
├── .env                  # Variables de entorno (no incluido en Git)
├── .env.example          # Plantilla para variables de entorno
└── package.json          # Dependencias y scripts
```

### 🔧 Instalación y Configuración

1. **Clona el repositorio**:
   ```bash
   git clone https://github.com/tu-usuario/pcpro-traductor-ia-deepseek.git
   cd pcpro-traductor-ia-deepseek
   ```

2. **Instala las dependencias**:
   ```bash
   npm install
   ```

3. **Configura las variables de entorno**:
   ```bash
   cp .env.example .env
   ```
   Edita el archivo `.env` y agrega tu clave API de DeepSeek:
   ```
   DEEPSEEK_API_KEY=tu_clave_api_aqui
   PORT=3000
   ```

4. **Inicia el servidor**:
   ```bash
   node app.js
   ```

5. **Accede a la aplicación**:
   Abre tu navegador y visita `http://localhost:3000`

### 📊 Flujo de Datos

1. El usuario introduce texto y selecciona el idioma destino
2. Frontend muestra "Traduciendo..." mientras procesa
3. Se envía una solicitud POST a `/api/traducir` con el texto y el idioma
4. El backend conecta con la API de DeepSeek
5. La respuesta de la IA se devuelve al frontend
6. El mensaje "Traduciendo..." se reemplaza por la traducción

### ⚙️ API Endpoints

| Endpoint | Método | Cuerpo | Respuesta |
|----------|--------|--------|-----------|
| `/api/traducir` | POST | `{text: string, targetLang: string}` | `{translatedText: string}` |

## 📌 Notas Importantes

- Esta aplicación requiere una clave API válida de DeepSeek
- Las claves API son sensibles y no deben compartirse ni incluirse en el control de versiones
- El archivo `.env` está incluido en `.gitignore` para proteger información sensible

## 🔍 Solución de Problemas

- **Error "API key not valid"**: Verifica que tu clave API en el archivo `.env` sea correcta
- **Problemas de conexión**: Asegúrate de tener acceso a internet y que la API de DeepSeek esté disponible
- **No se muestra traducción**: Revisa la consola del navegador para ver errores detallados

## 👨‍💻 Desarrollado por

FranHR - [www.pcprogramacion.es](https://www.pcprogramacion.es)

---

© 2023 PCpro Traductor IA - DeepSeek. Todos los derechos reservados. 