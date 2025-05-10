# 🗃️ CONEXIONES A BASE DE DATOS

## 📝 Nota Importante

Este proyecto actualmente no utiliza una base de datos relacional o NoSQL. Toda la funcionalidad se basa en:

- Conexiones a la API de DeepSeek (a través de un cliente compatible con OpenAI)
- Procesamiento en memoria de las traducciones
- Interfaz de usuario sin almacenamiento persistente

## 🔄 Conexión API Actual

```javascript
// Configuración de la conexión a DeepSeek
import OpenAI from "openai";
import dotenv from "dotenv";

dotenv.config();

const openai = new OpenAI({
    baseURL: 'https://api.deepseek.com', // Endpoint de DeepSeek
    apiKey: process.env.DEEPSEEK_API_KEY // Clave de API desde variables de entorno
});

// Ejemplo de petición a la API para traducción
const translation = await openai.chat.completions.create({
    model: 'deepseek-chat',
    messages: [
        { role: "system", content: "Eres un traductor profesional." },
        { role: "user", content: `Traduce el siguiente texto al francés: Hola mundo` }
    ],
    max_tokens: 500
});
```

## 🔮 Posibles Implementaciones Futuras

Si se decidiera implementar una base de datos en el futuro, estas serían las consideraciones:

### 📋 Posible Estructura de Base de Datos

#### Tabla: `usuarios`
- `id` (PK): Identificador único
- `nombre`: Nombre del usuario
- `email`: Correo electrónico
- `fecha_registro`: Timestamp

#### Tabla: `traducciones`
- `id` (PK): Identificador único
- `usuario_id` (FK): Referencia a usuario
- `texto_original`: Texto enviado para traducir
- `texto_traducido`: Resultado de la traducción
- `idioma_origen`: Idioma detectado o seleccionado
- `idioma_destino`: Idioma al que se tradujo
- `fecha`: Timestamp

#### Tabla: `configuraciones`
- `usuario_id` (FK): Referencia a usuario
- `idioma_preferido`: Idioma predeterminado
- `tema_ui`: Preferencias visuales
- `api_key_personal`: Opcional para usuarios con clave propia

### 🚀 Posible Implementación Técnica

```javascript
// Ejemplo de código para conexión a base de datos (MongoDB)
import mongoose from 'mongoose';

mongoose.connect(process.env.MONGODB_URI, {
  useNewUrlParser: true,
  useUnifiedTopology: true
})
.then(() => console.log('Conexión a MongoDB establecida'))
.catch(err => console.error('Error conectando a MongoDB:', err));
```

```javascript
// Ejemplo de código para conexión a base de datos (MySQL/PostgreSQL)
import { Sequelize } from 'sequelize';

const sequelize = new Sequelize(
  process.env.DB_NAME,
  process.env.DB_USER,
  process.env.DB_PASSWORD,
  {
    host: process.env.DB_HOST,
    dialect: 'mysql' // o 'postgres'
  }
);

sequelize.authenticate()
  .then(() => console.log('Conexión a la base de datos establecida'))
  .catch(err => console.error('Error conectando a la base de datos:', err));
``` 