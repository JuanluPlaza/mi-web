# Tipografías del sitio

Los `.woff2` de esta carpeta son los subconjuntos **latin** y **latin-ext** que sirve
Google Fonts, descargados y alojados en nuestro propio dominio. Se autoalojan por dos
motivos: cargarlos desde `fonts.gstatic.com` enviaba la IP de cada visitante a Google
sin declararlo en la política de privacidad, y la hoja de estilos de Google bloqueaba
el primer pintado de la página.

Las dos familias se publican bajo la **SIL Open Font License 1.1**, que permite
alojarlas y redistribuirlas siempre que se conserve el aviso de copyright y no se
vendan por separado.

| Familia | Copyright | Origen |
|---|---|---|
| Instrument Sans | © The Instrument Sans Project Authors | https://github.com/Instrument/instrument-sans |
| IBM Plex Mono | © IBM Corp. | https://github.com/IBM/plex |

Texto completo de la licencia: https://openfontlicense.org

## Archivos

| Archivo | Familia | Peso | Subconjunto |
|---|---|---|---|
| `instrument-sans-latin.woff2` | Instrument Sans (variable) | 400–700 | latin |
| `instrument-sans-latin-ext.woff2` | Instrument Sans (variable) | 400–700 | latin-ext |
| `ibm-plex-mono-400-latin.woff2` | IBM Plex Mono | 400 | latin |
| `ibm-plex-mono-400-latin-ext.woff2` | IBM Plex Mono | 400 | latin-ext |
| `ibm-plex-mono-500-latin.woff2` | IBM Plex Mono | 500 | latin |
| `ibm-plex-mono-500-latin-ext.woff2` | IBM Plex Mono | 500 | latin-ext |

No se incluyen los subconjuntos cirílico ni vietnamita: el sitio está en español y no
los usa. Las declaraciones `@font-face` van embebidas en el `<style>` de cada página
(`index.html`, `legal.html`, `privacidad.html`, `404.html`) — si se añade una página
nueva, hay que copiarlas también allí.
