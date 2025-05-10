# App Peluquería

## Sistema de URL Base

### Descripción
El sistema de URL Base permite que la aplicación funcione correctamente tanto en entornos de desarrollo como en producción, sin necesidad de modificar las rutas en cada entorno.

### Uso
Para generar URLs correctas en toda la aplicación, utiliza la función `url()`:

```php
// Enlace a la página de inicio
<a href="<?php echo url('/'); ?>">Inicio</a>

// Enlace a otra página
<a href="<?php echo url('/olvide'); ?>">Olvidé mi contraseña</a>

// Uso con recursos estáticos
<img src="<?php echo url('/build/img/logo.png'); ?>" alt="Logo">
```

### Configuración
La URL base se configura en el archivo `includes/config.php`. Para entornos de producción, ajustar la constante `URL_BASE` según sea necesario:

```php
// Para desarrollo
define('URL_BASE', '/pcpro-app-peluqueria/public');

// Para producción (si está en la raíz del dominio)
// define('URL_BASE', '');
```

### Variables disponibles en vistas
En todas las vistas se dispone de la variable `$url_base` que contiene la URL base configurada:

```php
<link rel="stylesheet" href="<?php echo $url_base; ?>/build/css/app.css">
```

## Autor
franHR - web - www.pcprogramacion.es 

# README - Sistema de Administración Dinámico para Peluquerías

## 1. Visión General del Proyecto

Este documento describe el plan para implementar un sistema de administración dinámico en la aplicación de gestión de citas para peluquerías. El objetivo es permitir que cada peluquería configure sus propios detalles, peluqueros, servicios, horarios y gestione sus citas de forma flexible.

## 2. Características Principales

*   **Gestión Multi-Peluquería (Potencial):** Aunque el enfoque inicial es una peluquería, la estructura permite escalar.
*   **Gestión de Peluqueros:** Añadir, editar, desactivar peluqueros.
*   **Gestión de Servicios:** Crear servicios con precios y duración variable (en minutos).
*   **Configuración de Horarios:** Establecer horarios de apertura y cierre por día (mañana/tarde) y gestionar días festivos/cerrados.
*   **Cálculo de Disponibilidad:** Sistema inteligente para calcular slots de tiempo disponibles basado en la duración del servicio, el horario de la peluquería y las citas existentes de cada peluquero.
*   **Interfaz de Administración:** Panel centralizado para gestionar todos los aspectos de la peluquería.
*   **API Robusta:** Endpoints para comunicar el frontend con el backend y obtener información dinámica (servicios, disponibilidad, etc.).
*   **Integración con Frontend:** Modificación de la interfaz de reserva de citas para reflejar la disponibilidad real y permitir la selección de peluquero (si aplica).

## 3. Estructura de la Base de Datos Propuesta

Se añadirán/modificarán las siguientes tablas:

*   **`peluquerias`**: Información general de cada peluquería.
    *   `id`, `nombre`, `direccion`, `telefono`, `email`, `logo`
*   **`peluqueros`**: Datos de los profesionales.
    *   `id`, `id_peluqueria`, `nombre`, `apellido`, `telefono`, `email`, `foto`, `activo`
*   **`servicios`**: Catálogo de servicios ofrecidos (modificación).
    *   `id`, `id_peluqueria`, `nombre`, `precio`, `duracion` (INT, en minutos), `descripcion`, `activo`
*   **`horarios`**: Horarios de apertura por día.
    *   `id`, `id_peluqueria`, `dia_semana` (1-7), `apertura_am`, `cierre_am`, `apertura_pm`, `cierre_pm`, `cerrado` (TINYINT)
*   **`citas`**: Registro de todas las citas.
    *   `id`, `id_peluqueria`, `id_peluquero`, `id_cliente`, `fecha`, `hora_inicio`, `hora_fin`, `total`, `estado`
*   **`servicios_citas`**: Relación N:M entre citas y servicios.
    *   `id`, `id_cita`, `id_servicio`, `precio`

*(Nota: Se asume la existencia previa de una tabla `usuarios` para clientes).*

## 4. Panel de Administración

Se creará una nueva sección `/admin` con las siguientes funcionalidades:

*   **Dashboard:** Resumen general y accesos directos.
*   **Peluquería:** Configuración básica.
*   **Peluqueros:** CRUD completo.
*   **Servicios:** CRUD completo (incluyendo duración).
*   **Horarios:** Interfaz visual para definir horarios semanales.
*   **Citas:** Listado, vista de calendario, gestión manual.

## 5. Lógica Central: Cálculo de Disponibilidad

Se implementarán funciones clave en PHP para determinar los horarios libres:

1.  `obtenerHorariosDisponibles($fecha, $id_peluqueria, $id_servicio)`: Orquesta el proceso.
2.  `obtenerDuracionServicio($id_servicio)`: Devuelve la duración en minutos.
3.  `obtenerHorarioPorDia($fecha, $id_peluqueria)`: Obtiene el horario aplicable.
4.  `obtenerPeluquerosActivos($id_peluqueria)`: Lista los peluqueros disponibles.
5.  `obtenerCitasPeluqueroPorDia($id_peluquero, $fecha)`: Obtiene las citas ya agendadas.
6.  `generarSlotsDisponibles($horario, $citas_ocupadas, $duracion_servicio)`: Genera los intervalos de tiempo libres (ej: cada 15 min).
7.  `estaOcupado($hora_inicio, $duracion, $citas_ocupadas)`: Verifica si un slot específico se solapa con citas existentes.

## 6. API para Frontend

Se crearán o modificarán los siguientes endpoints:

*   `GET /api/servicios?id_peluqueria={id}`: Devuelve los servicios de la peluquería.
*   `GET /api/peluqueros?id_peluqueria={id}`: Devuelve los peluqueros activos.
*   `GET /api/disponibilidad?fecha={fecha}&id_servicio={id}&id_peluqueria={id}`: Devuelve los slots de hora disponibles, agrupados por peluquero.
*   `POST /api/citas`: Guarda una nueva cita, realizando una última validación de disponibilidad.

## 7. Integración con el Frontend (JavaScript)

*   Actualizar la llamada a `consultarAPI` para obtener servicios dinámicamente.
*   Crear `consultarDisponibilidad` que se active al seleccionar fecha y servicio.
*   Implementar `mostrarHorariosDisponibles` para renderizar los botones de hora por peluquero.
*   Modificar `seleccionarHora` para guardar también el `id_peluquero` seleccionado.
*   Ajustar la vista `cita/index.php` para incluir los nuevos elementos (selector de fecha que active la consulta, contenedor para horas).

## 8. Pasos de Implementación Propuestos

1.  **Base de Datos:** Crear/modificar tablas SQL.
2.  **Modelos PHP:** Crear/actualizar clases `ActiveRecord`.
3.  **Controladores Admin:** Crear `AdminController` y sus métodos.
4.  **Controlador API:** Crear `APIController` o añadir métodos a uno existente.
5.  **Rutas:** Añadir rutas para admin y API en `Router.php`.
6.  **Vistas Admin:** Desarrollar las interfaces HTML/CSS para el panel.
7.  **Lógica Disponibilidad:** Implementar las funciones PHP de cálculo.
8.  **Vistas Citas:** Modificar `views/cita/index.php`.
9.  **JavaScript:** Actualizar `public/build/js/app.js` para interactuar con la nueva API y lógica.
10. **Pruebas:** Realizar pruebas exhaustivas de todo el flujo.
11. **Seguridad:** Asegurar validaciones y permisos.

---

Este plan proporciona una guía detallada para construir un sistema de administración robusto y flexible para la aplicación. 