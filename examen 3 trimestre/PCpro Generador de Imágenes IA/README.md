# 🖼️ PCpro Generador de Imágenes IA

![Logo](./public/assets/img/logo.png)

## 📖 Descripción

PCpro Generador de Imágenes IA es una aplicación web sencilla que te permite generar avatares únicos en estilo cartoon utilizando la inteligencia artificial de OpenAI (modelo DALL-E 2). Selecciona una categoría y la aplicación se encargará de crear una imagen representativa.

## ✨ Características Principales

-   🎨 **Generación de Avatares**: Crea imágenes estilo cartoon basadas en categorías predefinidas (Hombre, Mujer, Animal, Objeto, Paisaje).
-   🤖 **Potenciado por OpenAI**: Utiliza el modelo DALL-E 2 a través de su API para la generación de imágenes.
-   ⚙️ **Interfaz Simple**: Una interfaz web limpia y fácil de usar para seleccionar la categoría y generar la imagen.
-   ⏳ **Indicador de Carga**: Muestra un mensaje "Cargando..." mientras la imagen se está generando.
-   🚀 **Backend Eficiente**: Construido con Node.js y Express para manejar las solicitudes a la API de OpenAI.

## 🛠️ Tecnologías Utilizadas

-   **Frontend**:
    -   <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="HTML5" width="20" height="20"/> HTML5
    -   <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="CSS3" width="20" height="20"/> CSS3
    -   <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="JavaScript" width="20" height="20"/> JavaScript (Vanilla)
-   **Backend**:
    -   <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="Node.js" width="20" height="20"/> Node.js
    -   <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original-wordmark.svg" alt="Express" width="20" height="20"/> Express.js
    -   <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/axios/axios-plain-wordmark.svg" alt="Axios" width="20" height="20"/> Axios (para llamadas a la API)
-   **API IA**: OpenAI DALL-E 2
-   **Entorno**:
    -   `dotenv` para gestión de variables de entorno.

## 📋 Requisitos Previos

-   Node.js (versión 14 o superior recomendado)
-   npm (normalmente viene con Node.js)
-   Cuenta en [OpenAI](https://openai.com/) y una API Key válida.

## 🚀 Instrucciones de Instalación y Uso

1.  **Clonar el Repositorio**

    ```bash
    git clone <URL_DEL_REPOSITORIO_AQUI> # Reemplaza con la URL real de tu repo
    cd pcpro-Generador-de-imagenes-IA
    ```

2.  **Instalar Dependencias**

    Navega a la carpeta raíz del proyecto en tu terminal y ejecuta:
    ```bash
    npm install
    ```
    Esto instalará todas las dependencias listadas en `package.json` (Express, Axios, Dotenv, etc.).

3.  **Configurar Variables de Entorno**

    -   Crea un archivo llamado `.env` en la raíz del proyecto.
    -   Abre el archivo `.env.example` que se incluye en el repositorio.
    -   Copia el contenido de `.env.example` a tu nuevo archivo `.env`.
    -   Reemplaza el placeholder con tu API Key real de OpenAI:

        ```dotenv
        # .env
        OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
        ```

4.  **Iniciar la Aplicación**

    Puedes iniciar el servidor de dos maneras:

    *   **Modo Desarrollo (con recarga automática si tienes `nodemon` instalado globalmente o como dependencia de desarrollo):**
        ```bash
        npm start
        ```
    *   **Modo Producción:**
        ```bash
        npm run serve
        ```

5.  **Acceder a la Aplicación**

    Una vez que el servidor esté corriendo (verás un mensaje como `servidor corriendo en http://localhost:3000`), abre tu navegador web y visita:
    [http://localhost:3000](http://localhost:3000)

6.  **Generar una Imagen**
    -   Selecciona una categoría del menú desplegable.
    -   Haz clic en el botón "Generar Avatar con IA".
    -   Espera a que el indicador "Cargando..." desaparezca y aparezca tu imagen generada.

## 🔒 Seguridad: API Key

-   El archivo `.env` donde guardas tu `OPENAI_API_KEY` **está incluido en el archivo `.gitignore` por defecto**. Esto es crucial para evitar que tu clave secreta se suba accidentalmente a repositorios públicos como GitHub.
-   **NUNCA** compartas tu archivo `.env` ni publiques tu API Key en lugares públicos.
-   El archivo `.env.example` sirve como plantilla y **no** debe contener claves reales.

## 👤 Autor

-   **franHR** - [www.pcprogramacion.es](https://www.pcprogramacion.es)

---

⭐ Si encuentras útil este proyecto, ¡considera darle una estrella! ⭐
