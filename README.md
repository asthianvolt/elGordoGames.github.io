# El Atajo — blog base para GitHub Pages

Blog mínimo en Jekyll, listo para publicar guías, embeber tus shorts y meter anuncios de AdSense. Costo: **$0**, salvo que más adelante quieras un dominio propio (~$10-15 USD/año, opcional).

## 1. Publicarlo en GitHub Pages (5 minutos)

1. Crea un repositorio nuevo en GitHub (público). Si lo llamas exactamente `tu-usuario.github.io`, el sitio queda en esa URL directo. Si le pones otro nombre, queda en `tu-usuario.github.io/nombre-del-repo`.
2. Sube todo el contenido de esta carpeta a ese repositorio (arrastrando los archivos en la web de GitHub, o con `git push` si prefieres terminal).
3. En el repo, ve a **Settings → Pages**.
4. En "Build and deployment", selecciona **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guarda.
5. Espera 1-2 minutos y tu sitio ya está en línea en la URL que te muestra esa misma página.

No necesitas instalar Jekyll ni Ruby para esto — GitHub lo construye automáticamente al hacer push.

## 2. Escribir una guía nueva

Copia `_posts/2026-07-23-editar-pdf-gratis-sin-instalar-nada.md` como plantilla. El nombre del archivo debe empezar con la fecha: `YYYY-MM-DD-titulo-corto.md`. Cambia el `title`, `category` y `excerpt` del encabezado, y escribe el contenido debajo en Markdown normal (o HTML si quieres usar los bloques `.step` como en el ejemplo).

## 3. Agregar tus videos

Edita `videos.html` y reemplaza cada `VIDEO_ID_X` por el ID real del video (la parte final de `youtube.com/shorts/ESTE_ID`).

## 4. Activar Google AdSense

1. Aplica en [google.com/adsense](https://www.google.com/adsense) con la URL de tu sitio ya publicado (necesitas tener contenido real primero, no una página vacía).
2. Cuando te aprueben, te dan un **Publisher ID** (`pub-XXXXXXXXXXXXXXXX`). Reemplázalo en `ads.txt` y en `adsense_client` dentro de `_config.yml`.
3. Descomenta la línea del script de AdSense en `_layouts/default.html` (está marcada con un comentario).
4. Los `<div class="ad-slot">` en `index.html` y `_layouts/post.html` son donde va cada bloque de anuncio — sustitúyelos por el código que AdSense te da para cada "unidad de anuncio".

**Ojo:** AdSense revisa el sitio antes de aprobar. Con solo la plantilla vacía casi seguro te rechazan — publica 3-5 guías reales primero.

## 5. Dominio propio (opcional)

Si más adelante compras un dominio (Namecheap, Porkbun, etc.), en **Settings → Pages** de GitHub agregas el dominio en "Custom domain", y en tu proveedor del dominio apuntas los DNS a GitHub Pages (ellos mismos te dan las instrucciones exactas al escribir el dominio ahí).

## Estructura del proyecto

```
_config.yml       → título, descripción, IDs de AdSense y del canal
_layouts/         → plantillas HTML (default.html, post.html)
_posts/           → tus guías, una por archivo
assets/css/       → todos los estilos
index.html        → portada
videos.html       → página de videos embebidos
ads.txt           → requerido por AdSense una vez tengas dominio propio
```
