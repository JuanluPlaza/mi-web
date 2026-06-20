# PlazaSys — Web corporativa

Código de la página web de **PlazaSys** (Plaza Automated Systems S.L.), especialista en
automatización industrial, IoT, ingeniería mecánica y prototipado de máquinas.

🌐 En producción: https://plazasys.com

## Tecnología

Web **estática** de una sola página: HTML + CSS + JavaScript, sin frameworks ni dependencias.
Todo el estilo y los scripts van embebidos en `index.html`.

## Ver en local

Al ser estática, basta con abrir `index.html` en el navegador:

```bash
git clone https://github.com/JuanluPlaza/mi-web.git
cd mi-web
# Abre index.html con doble clic, o sirve la carpeta con un mini-servidor:
python -m http.server 8000   # luego abre http://localhost:8000
```

## Despliegue

El sitio está desplegado en **Cloudflare Pages**. Al subir cambios a la rama principal de
GitHub, Cloudflare publica automáticamente la nueva versión.

El archivo `_redirects` (compatible con Cloudflare Pages y Netlify) gestiona la página de
error 404.

## Estructura

| Archivo | Para qué sirve |
|---------|----------------|
| `index.html`        | La web completa (estructura, estilos y scripts) |
| `404.html`          | Página de error "no encontrada" |
| `plazasys-logo.svg` | Logotipo |
| `favicon.ico`       | Icono de la pestaña del navegador |
| `robots.txt`        | Instrucciones para buscadores |
| `sitemap.xml`       | Mapa del sitio para buscadores |
| `_redirects`        | Reglas de redirección del hosting |
