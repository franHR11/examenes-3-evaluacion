# WebPersonal - Portafolio Django

## 📢 Sección Comercial
Proyecto web para mostrar el portafolio profesional de franHR, desarrollador web. Perfecto para compartir en redes sociales y atraer clientes o empleadores.

## 📝 Descripción y Características
- Sitio web hecho en Django.
- Gestión de proyectos con imágenes, descripciones y enlaces.
- Panel de administración para gestionar el contenido.
- Subida y visualización de imágenes en la sección de portafolio.
- Responsive y preparado para producción.

## ⚙️ Sección Técnica
### Instalación y despliegue en producción (Render)

1. **Clona el repositorio o conecta tu repo a Render.**
2. **Asegúrate de que el archivo `requirements.txt` contiene `gunicorn` y `whitenoise`.**
3. **En Render, configura los comandos así:**
   - **Build Command:**
     ```bash
     pip install -r requirements.txt
     ```
   - **Pre-Deploy Command:**
     ```bash
     python manage.py collectstatic --noinput
     python manage.py migrate --noinput
     ```
   - **Start Command:**
     ```bash
     gunicorn webpersonal.wsgi:application
     ```
4. **Edita `ALLOWED_HOSTS` en `webpersonal/settings.py` e incluye:**
   ```python
   ALLOWED_HOSTS = [
       'localhost',
       '127.0.0.1',
       'pcpro-blog-django.onrender.com',
   ]
   ```
5. **Agrega y configura WhiteNoise en `settings.py` para servir archivos estáticos en producción:**
   - Instala whitenoise añadiendo la línea `whitenoise` en `requirements.txt`.
   - Añade `'whitenoise.middleware.WhiteNoiseMiddleware',` en la lista `MIDDLEWARE` justo después de `'django.middleware.security.SecurityMiddleware',`.
   - Asegúrate de tener:
     ```python
     STATIC_ROOT = BASE_DIR / 'staticfiles'
     ```
   - Ejecuta `python manage.py collectstatic` en cada despliegue.
6. **Haz push de los cambios y Render desplegará automáticamente.**
7. **Accede a tu web en la URL de Render (`https://pcpro-blog-django.onrender.com`).**

#### Instalación local (opcional)

1. **Crea y activa un entorno virtual:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate   # Windows
   ```
2. **Instala las dependencias:**
   ```bash
   pip install -r requirements.txt
   ```
3. **Aplica migraciones y crea superusuario:**
   ```bash
   python manage.py migrate
   python manage.py createsuperuser
   ```
4. **Ejecuta el servidor de desarrollo:**
   ```bash
   python manage.py runserver
   ```

### Estructura de carpetas relevante
- `webpersonal/portfolio/templates/portfolio/portfolio.html`: Plantilla principal del portafolio.
- `webpersonal/media/projects/`: Carpeta donde se suben las imágenes de proyectos.

---

## 🚀 ¡Listo para producción!
Sigue estos pasos y tu web estará online de forma segura y profesional.
