# MEMORIAS.md

## 22/04/2025 - Implementación CRUD y Gráficos
- Se ha planificado y aprobado la creación de endpoints REST para gestionar productos en `primeros_10_productos.json`.
- Se implementarán endpoints para datos de gráficos (precios por marca y número de productos por marca).
- Se crea una nueva página `graficos.html` y lógica JS para mostrar gráficos con Chart.js.
- Se actualiza la documentación técnica y de memoria.

## 22/04/2025 - Validación y flujo conversacional en alta de productos
- Ahora, al añadir productos desde el chat, si falta o es incorrecto algún dato (ID, nombre, marca, precio, cantidad en stock), el asistente pregunta específicamente por ese campo.
- El sistema valida que el nombre no sea solo un número, que el precio sea positivo, que la marca no esté vacía y que la cantidad en stock sea un número entero positivo.
- Si el usuario introduce un dato inválido, el asistente muestra un mensaje claro y vuelve a preguntar solo por ese campo.
- El flujo es más natural, robusto y a prueba de errores de usuario.

## 22/04/2025 - Botones flotantes CRUD sobre el chat
- Se han añadido cuatro botones flotantes minimalistas encima del botón de enviar, con iconos de FontAwesome y colores amarillo/naranja.
- Cada botón representa una acción CRUD (crear, leer, modificar, borrar) y al pulsarlo envía automáticamente un prompt adecuado al chat, facilitando el uso sin necesidad de escribir.
- Mejora la accesibilidad y la experiencia de usuario para operaciones rápidas.
