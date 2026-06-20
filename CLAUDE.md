# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Qué es esto

Web corporativa de **PlazaSys** (Plaza Automated Systems S.L.), empresa de automatización industrial / IoT / ingeniería mecánica. Sitio en producción: https://plazasys.com

Es un sitio **estático de una sola página** — HTML + CSS + JavaScript puro, **sin frameworks, sin paso de compilación y sin dependencias**. Todo el marcado, los estilos (`<style>`) y los scripts (`<script>`) van embebidos dentro de `index.html`.

## Ejecutar en local

No hay build ni instalación. Abre `index.html` directamente, o sirve la carpeta:

```bash
python -m http.server 8000   # luego abre http://localhost:8000
```

No hay herramientas de lint ni de tests. Verifica los cambios cargando la página en el navegador.

## Despliegue

Desplegado en **Cloudflare Pages**: cualquier push a la rama `main` se publica automáticamente. No hay entorno de staging, así que trata `main` como producción.

`_redirects` (formato Cloudflare Pages / Netlify) redirige las rutas inexistentes a `404.html` con un código 404 real.

## Notas de arquitectura

- **`index.html` es toda la aplicación.** Está organizado de arriba a abajo así: bloque `<style>` → datos estructurados JSON-LD (`application/ld+json`) → `<nav>` → `<section>`s de la página (`#inicio`, `#servicios`, `#nosotros`, `#contacto`) → `<footer>` → un único bloque `<script>` al final. Al editar, busca la región correspondiente en vez de asumir que hay archivos separados.
- **El `<script>` final controla varios widgets animados de "demo en vivo" independientes**, ligados por completo a los `id` de los elementos del marcado — medidores/gauges (`gT`/`gR`), sparklines (`spTL`/`spRL`...), un terminal de estado simulado (`term`) y un simulador de motor interactivo (`simS`/`simQ`/`simB`...). Si cambias o eliminas el HTML de un widget, actualiza también la lógica `getElementById` correspondiente en el script (y viceversa), ya que solo están acoplados por esas cadenas de `id`.
- El simulador de motor y los gauges usan bucles `setInterval`/`requestAnimationFrame` con constantes tipo física codificadas a mano (factores de suavizado, rangos de rpm/temperatura) — son cosméticos, no datos reales.

## SEO / metadatos a mantener sincronizados

Varios archivos codifican los mismos datos del sitio y deben actualizarse juntos cuando cambie el contenido, la URL o la estructura:
- Las meta etiquetas del `<head>` de `index.html` + el bloque JSON-LD
- `sitemap.xml` (`loc`, `lastmod`)
- `robots.txt` y `_redirects`
- `404.html` (página independiente; no comparte los estilos de `index.html`)

El contenido está en **español** — mantén los textos, el alt y los metadatos en español.
