# 📝 Registro de Cambios y Decisiones

## 📅 Versión 1.0.0 - Inicial

### 🔨 Configuración del Proyecto
- Inicialización del proyecto con Node.js y Express
- Configuración de dotenv para manejo de variables de entorno
- Integración de OpenAI API
- Estructura básica del frontend con HTML, CSS y JavaScript

### 🧠 Decisiones Clave
- **Elección del modelo**: Se optó por GPT-3.5 Turbo por su equilibrio entre capacidad y costo
- **Gestión de conversaciones**: Sistema propio para mantener conversaciones por ID de usuario
- **Límite de tokens**: Configurado a 200 tokens máximos para optimizar costos
- **Límite de historial**: Limitado a 10 mensajes para mantener el rendimiento

### 🚀 Características Implementadas
- Chat interactivo para responder consultas sobre el supermercado
- Interfaz responsiva adaptada a dispositivos móviles
- Sistema de context prompt para definir la personalidad del bot
- Limitación de respuestas a la información específica del negocio

### 🛠️ Aspectos Técnicos
- Sistema de enrutamiento con Express para manejar las peticiones API
- Manejo de JSON para la comunicación entre frontend y backend
- Evento de "Enter" para enviar mensajes más cómodamente
- Auto-scroll del chat para mejor experiencia de usuario

## 📋 Tareas Pendientes para Futuras Versiones
- [ ] Implementar autenticación para proteger el API
- [ ] Añadir base de datos para persistencia de conversaciones
- [ ] Desarrollar panel de administración para gestionar el contexto
- [ ] Incorporar análisis de sentimiento para mejorar respuestas 