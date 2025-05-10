# MEMORIAS DEL PROYECTO

## Cambios y decisiones clave
- Se configuró el proyecto para que las imágenes de proyectos se suban a `media/projects`.
- Se organizó la plantilla del portafolio en `portfolio/templates/portfolio/portfolio.html` siguiendo buenas prácticas Django.
- Se documentó el proceso de despliegue en producción para servidores Linux y Windows.
- Se recomienda Gunicorn para Linux y Waitress para Windows como servidores de aplicaciones.
- Se añadió ejemplo de configuración para Nginx como proxy inverso.

## Última actualización
- 2025-04-24: Documentación de despliegue y estructura de carpetas actualizada.
- 2025-04-24: Se configuró WhiteNoise y STATIC_ROOT en settings.py para servir archivos estáticos correctamente en Render. Se añadió whitenoise a requirements.txt y se actualizó la documentación técnica para reflejar este cambio.
