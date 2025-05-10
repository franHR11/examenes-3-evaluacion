# 📚 Documentación del Proyecto PCpro Chatbot

## 📋 Índice de Contenidos

1. [Descripción General](#descripción-general)
2. [Guía de Instalación](#guía-de-instalación)
3. [Guía de Uso](#guía-de-uso)
4. [Arquitectura del Sistema](#arquitectura-del-sistema)
5. [Personalización](#personalización)
6. [Documentación Técnica](#documentación-técnica)
7. [Preguntas Frecuentes](#preguntas-frecuentes)

## 📝 Descripción General

PCpro Chatbot es una solución de atención al cliente basada en inteligencia artificial, diseñada específicamente para negocios del sector alimentario como supermercados, tiendas de comestibles y otros comercios similares.

La aplicación utiliza el modelo GPT-3.5 Turbo de OpenAI para proporcionar respuestas contextualizadas sobre la información del negocio, como horarios, productos disponibles, ubicación y métodos de pago.

## 🚀 Guía de Instalación

Consulta el archivo [README.md](../README.md) principal del proyecto para las instrucciones detalladas de instalación.

## 👨‍💻 Guía de Uso

### Para Usuarios Finales

1. Accede a la página web del chatbot
2. Escribe tu pregunta en el campo de texto
3. Presiona "Enviar" o la tecla Enter
4. Recibe la respuesta del asistente virtual

### Para Administradores

Para personalizar el chatbot para tu negocio:

1. Edita el archivo `app.js`
2. Modifica la constante `context` con la información específica de tu negocio
3. Reinicia el servidor

## 🏗️ Arquitectura del Sistema

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

## 🔄 Personalización

### Contexto del Chatbot

El comportamiento del chatbot está definido por el contexto proporcionado en el archivo `app.js`. Este contexto incluye:

- Información sobre el negocio
- Productos disponibles
- Ubicación y horarios
- Marcas disponibles
- Métodos de pago aceptados

### Estilos de la Interfaz

Los estilos visuales pueden modificarse editando el archivo `public/assets/css/styles.css`. La interfaz está diseñada para ser responsiva y adaptarse a diferentes tamaños de pantalla.

## 📘 Documentación Técnica

Para información técnica más detallada, consulta los siguientes documentos:

- [MEMORIAS.md](./MEMORIAS.md) - Registro de cambios y decisiones clave
- [CONEXIONES_BD.md](./CONEXIONES_BD.md) - Detalles sobre la gestión de datos (actual y futura)

## ❓ Preguntas Frecuentes

### ¿El chatbot puede procesar pagos?
No, el chatbot actual solo proporciona información. No está diseñado para procesar pagos o realizar transacciones.

### ¿Cómo se controla qué información comparte el bot?
El bot solo comparte la información especificada en el contexto definido en `app.js`. Se le instruye explícitamente para responder solo preguntas relacionadas con el negocio.

### ¿Las conversaciones se guardan permanentemente?
No, en la versión actual las conversaciones se almacenan en memoria y se pierden al reiniciar el servidor. Consulta [CONEXIONES_BD.md](./CONEXIONES_BD.md) para ver propuestas futuras de persistencia.

### ¿Necesito una clave API de OpenAI?
Sí, necesitas crear una cuenta en OpenAI y obtener una clave API para que el chatbot funcione. Esta clave debe configurarse en el archivo `.env`. 