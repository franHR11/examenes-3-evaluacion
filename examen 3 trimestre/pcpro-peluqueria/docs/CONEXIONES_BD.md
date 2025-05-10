# Análisis de la Base de Datos: pcpro_peluqueria

Tipo de Base de Datos: mysql
Número de tablas: 5

## Tabla: citas

### Estructura de Columnas

| Columna | Tipo | Nullable | Key | Default | Extra |
|---------|------|----------|-----|---------|-------|
| id | int | NO | PRI | NULL | auto_increment |
| fecha | date | YES |   | NULL |   |
| hora | time | YES |   | NULL |   |
| usuarioId | int | YES | MUL | NULL |   |
| duracion_total | int | NO |   | 30 |   |
| asistio | tinyint(1) | YES |   | NULL |   |
| requiere_confirmacion | tinyint(1) | NO |   | 0 |   |
| confirmada | tinyint(1) | NO |   | 0 |   |

### Claves Primarias

- id

### Claves Foráneas

| Columna | Tabla Referenciada | Columna Referenciada |
|---------|-------------------|---------------------|
| usuarioId | usuarios | id |

---

## Tabla: citasservicios

### Estructura de Columnas

| Columna | Tipo | Nullable | Key | Default | Extra |
|---------|------|----------|-----|---------|-------|
| id | int | NO | PRI | NULL | auto_increment |
| citaId | int | YES | MUL | NULL |   |
| servicioId | int | YES | MUL | NULL |   |

### Claves Primarias

- id

### Claves Foráneas

| Columna | Tabla Referenciada | Columna Referenciada |
|---------|-------------------|---------------------|
| citaId | citas | id |
| servicioId | servicios | id |

---

## Tabla: configuracion

### Estructura de Columnas

| Columna | Tipo | Nullable | Key | Default | Extra |
|---------|------|----------|-----|---------|-------|
| id | int | NO | PRI | NULL | auto_increment |
| clave | varchar(50) | NO | UNI | NULL |   |
| valor | text | YES |   | NULL |   |
| descripcion | text | YES |   | NULL |   |
| tipo | varchar(20) | YES |   | texto |   |
| seccion | varchar(30) | YES |   | general |   |
| created_at | timestamp | YES |   | CURRENT_TIMESTAMP | DEFAULT_GENERATED |
| updated_at | timestamp | YES |   | CURRENT_TIMESTAMP | DEFAULT_GENERATED on update CURRENT_TIMESTAMP |

### Claves Primarias

- id

### Datos de Muestra

| id | clave | valor | descripcion | tipo | seccion | created_at | updated_at |
|---|---|---|---|---|---|---|---|
| 1 | horario_manana_apertura | 09:00 | Hora de apertura por la mañana | tiempo | horario | 2025-04-15 01:32:01 | 2025-04-15 01:32:01 |
| 2 | horario_manana_cierre | 14:00 | Hora de cierre por la mañana | tiempo | horario | 2025-04-15 01:32:01 | 2025-04-15 01:32:01 |
| 3 | horario_tarde_apertura | 17:00 | Hora de apertura por la tarde | tiempo | horario | 2025-04-15 01:32:01 | 2025-04-15 01:32:01 |
| 4 | horario_tarde_cierre | 20:00 | Hora de cierre por la tarde | tiempo | horario | 2025-04-15 01:32:01 | 2025-04-15 01:32:01 |
| 5 | horario_partido | 1 | ¿El negocio tiene horario partido? | booleano | horario | 2025-04-15 01:32:01 | 2025-04-15 01:32:01 |

---

## Tabla: servicios

### Estructura de Columnas

| Columna | Tipo | Nullable | Key | Default | Extra |
|---------|------|----------|-----|---------|-------|
| id | int | NO | PRI | NULL | auto_increment |
| nombre | varchar(60) | YES |   | NULL |   |
| precio | decimal(5,2) | YES |   | NULL |   |
| duracion | int | NO |   | 30 |   |

### Claves Primarias

- id

---

## Tabla: usuarios

### Estructura de Columnas

| Columna | Tipo | Nullable | Key | Default | Extra |
|---------|------|----------|-----|---------|-------|
| id | int | NO | PRI | NULL | auto_increment |
| nombre | varchar(60) | YES |   | NULL |   |
| apellido | varchar(60) | YES |   | NULL |   |
| email | varchar(40) | YES |   | NULL |   |
| password | varchar(60) | YES |   | NULL |   |
| telefono | varchar(9) | YES |   | NULL |   |
| admin | tinyint(1) | YES |   | 0 |   |
| confirmado | tinyint(1) | YES |   | 0 |   |
| token | varchar(15) | YES |   | NULL |   |
| faltas | int | NO |   | 0 |   |

### Claves Primarias

- id

---

## Tabla: configuracion

### Secciones disponibles

- general: Configuraciones generales del sitio
- seo: Configuraciones de SEO
- horario: Horarios y días de apertura
- negocio: Información del negocio
- apariencia: Configuración visual
- social: Redes sociales
- ubicacion: Ubicación y dirección
- citas: Configuración de citas

### Tipos de campos

- texto: Campo de texto simple
- textarea: Área de texto para textos largos
- booleano: Campo Si/No (1/0)
- tiempo: Hora (HH:MM)
- color: Selector de color
- numero: Campo numérico
- html: Editor de texto enriquecido

### Configuraciones clave

| Clave | Descripción | Tipo | Sección |
|-------|-------------|------|---------|
| cita_intervalo_minutos | Intervalo de tiempo para citas | numero | citas |
| horario_manana_apertura | Hora de apertura por la mañana | tiempo | horario |
| horario_manana_cierre | Hora de cierre por la mañana | tiempo | horario |
| horario_partido | ¿El negocio tiene horario partido? | booleano | horario |
| horario_tarde_apertura | Hora de apertura por la tarde | tiempo | horario |
| horario_tarde_cierre | Hora de cierre por la tarde | tiempo | horario |

---

