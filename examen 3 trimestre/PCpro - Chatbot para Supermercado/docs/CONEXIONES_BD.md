# 🗄️ Conexiones a Base de Datos

## 📊 Estado Actual

Actualmente, el proyecto **no utiliza una base de datos** para almacenar información. Las conversaciones se mantienen en memoria durante la ejecución del servidor usando un objeto JavaScript:

```javascript
let conversations = {};
```

Este objeto almacena las conversaciones indexadas por ID de usuario y se pierde cuando se reinicia el servidor.

## 🔄 Propuesta para Implementación Futura

### 📝 Esquema de Base de Datos Propuesto

Para futuras versiones, se recomienda implementar una base de datos con las siguientes tablas:

#### Tabla: `users`
| Campo      | Tipo         | Descripción                      |
|------------|--------------|----------------------------------|
| id         | VARCHAR(50)  | Identificador único del usuario  |
| created_at | TIMESTAMP    | Fecha de creación del usuario    |
| last_seen  | TIMESTAMP    | Última actividad del usuario     |

#### Tabla: `conversations`
| Campo        | Tipo         | Descripción                       |
|--------------|--------------|-----------------------------------|
| id           | INT AUTO_INC | Identificador único de conversación |
| user_id      | VARCHAR(50)  | ID del usuario (FK a users.id)    |
| created_at   | TIMESTAMP    | Inicio de la conversación         |
| last_message | TIMESTAMP    | Timestamp del último mensaje      |

#### Tabla: `messages`
| Campo            | Tipo          | Descripción                          |
|------------------|---------------|--------------------------------------|
| id               | INT AUTO_INC  | Identificador único del mensaje      |
| conversation_id  | INT           | ID de conversación (FK)              |
| role             | ENUM          | 'user' o 'assistant'                 |
| content          | TEXT          | Contenido del mensaje                |
| timestamp        | TIMESTAMP     | Momento en que se envió el mensaje   |
| tokens_used      | INT           | Contador de tokens consumidos        |

### 📑 Consultas SQL Frecuentes

Cuando se implemente la base de datos, estas serían las consultas más comunes:

```sql
-- Obtener las últimas 10 conversaciones para un usuario
SELECT * FROM conversations 
WHERE user_id = ? 
ORDER BY last_message DESC 
LIMIT 10;

-- Obtener los mensajes de una conversación
SELECT * FROM messages 
WHERE conversation_id = ? 
ORDER BY timestamp ASC;

-- Insertar un nuevo mensaje
INSERT INTO messages (conversation_id, role, content, timestamp, tokens_used) 
VALUES (?, ?, ?, NOW(), ?);

-- Actualizar el timestamp de última actividad
UPDATE conversations 
SET last_message = NOW() 
WHERE id = ?;
```

### 🔌 Instrucciones de Conexión (Futura)

Para implementar esta base de datos, se deberá:

1. Instalar MySQL/PostgreSQL u otro sistema de gestión de base de datos
2. Crear las tablas usando los esquemas proporcionados
3. Instalar el driver correspondiente:
   ```bash
   npm install mysql2
   # o
   npm install pg
   ```
4. Configurar las variables de entorno:
   ```
   DB_HOST=localhost
   DB_USER=usuario
   DB_PASSWORD=contraseña
   DB_NAME=pcpro_chatbot
   ```
5. Implementar un módulo para gestionar las conexiones

## 🚧 Próximos Pasos

1. Definir el sistema de gestión de bases de datos a utilizar
2. Implementar la persistencia de conversaciones
3. Añadir análisis de datos básico para entender preguntas frecuentes
4. Implementar un sistema de respaldo y recuperación 