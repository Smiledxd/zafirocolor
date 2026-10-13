# CLAUDE.md

Landing page estática de **Zafiro Color**, tienda de cosméticos y tintes en el Mercado Ateca, José Gálvez (Villa María del Triunfo, Lima). Sin framework ni build: HTML + CSS + JS inline. Todo el contenido y el código en español. Datos legales del negocio y detalle de archivos: ver `README.md`.

## Comandos

- `pnpm dev` → servidor local en `http://localhost:1234` sirviendo `src/`
- `pnpm lint` / `pnpm format` → oxlint / oxfmt (requiere `pnpm install` antes)
- No hay paso de build: lo que está en `src/` es lo que se publica.

## Hosting y despliegue

- Publicado en **Cloudflare Pages** con `src/` como carpeta de salida (confirmado por las cabeceras de respuesta de zafirocolor.com). El script `deploy` (gh-pages) no es el despliegue real.
- `src/_headers` define las cabeceras de seguridad (CSP, HSTS, X-Frame-Options). Debe vivir dentro de `src/` o Cloudflare lo ignora.
- Cloudflare inyecta su script de Web Analytics (`static.cloudflareinsights.com`, envía datos a `cloudflareinsights.com`); ya está permitido en el CSP.
- **Si agregas un recurso externo nuevo** (script, fuente, imagen, iframe, endpoint), añade su dominio a la directiva correspondiente del CSP en `src/_headers`, o quedará bloqueado en producción.

## Datos del negocio (NAP): mantener idénticos en todo el sitio y en la ficha de Google

- **Nombre:** Zafiro Color
- **Dirección:** Mercado Ateca, Pueblo J.N. Progreso Grp 2 Mz. K Lt. 17, José Gálvez, Villa María del Triunfo, Lima (CP 15816)
- **WhatsApp / teléfono:** +51 917 236 616 (`https://wa.me/51917236616`)
- **Horario:** lunes a domingo, 8:30 a.m. – 8:30 p.m. (`08:30`–`20:30` en schema)
- **Google Maps:** `https://maps.app.goo.gl/z8dsLWWSMRvWQ7yD9` · CID `12314896689822918033` · kgmid `/g/11z4mcr8lm`
- **Pagos:** efectivo, Yape, Plin, tarjeta

Si cambia alguno de estos datos, hay que actualizarlo en **todos** estos lugares:

1. `src/index.html`: JSON-LD (`CosmeticStore` + `FAQPage`), meta description/OG, hero (`.hero-hours`), sección `#ubicacion`, FAQ visible, footer y el script de "Abierto ahora" (horas en minutos).
2. Footer de las 4 páginas en `src/legales/` (y el bloque de contacto de `cookies.html`).
3. `README.md`.

## Convenciones del sitio

- **SEO local:** los textos deben mencionar de forma natural José Gálvez, Mercado Ateca y VMT. Evitar keyword stuffing y traducciones al inglés.
- **FAQ:** el texto de cada pregunta en la sección `#preguntas` debe coincidir con el `FAQPage` del JSON-LD (Google lo exige).
- **Carrusel de marcas:** cada marca va **una sola vez** en `<ul class="brands-track">`. El script del final de `index.html` crea la copia para el loop con `aria-hidden`. No duplicar marcas en el HTML.
- **Productos:** tarjetas `.product-card` en `#productos`, con imagen `src/img/N.webp` y precio `S/ 0.00`. Si cambian los precios mínimo/máximo, actualizar `priceRange` del schema.
- **No afirmar servicios no confirmados** por la dueña (p. ej. delivery o separación de productos).
- **Páginas legales** (`src/legales/`): llevan `noindex` y por eso no van en `sitemap.xml`.
- **Estilos:** `src/css/style.css` es global; `src/css/style2.css` solo aplica a las páginas legales y al formulario. Breakpoints: 1000px, 768px y 600px.

## Imágenes

- **Productos:** WebP de máx. 600×600 px, calidad ~80 (se muestran a ~250 px).
- **Hero:** `img/hero.webp` (1024×854).
- **Redes sociales:** `img/og-image.jpg` (1200×630).
- **Favicons:** `favicon-32.png`, `favicon-192.png`, `apple-touch-icon.png`.
- No subir imágenes pesadas sin optimizar; antes pesaban varios MB. No hay herramienta de imágenes en el repo: usar `sharp` desde una carpeta temporal.

## Flujo de trabajo

- Claude no hace commits: dejar los cambios listos y sugerir el mensaje de commit.
- Estilo de commits del repo: prefijo tipo `feat:`, `style:`, `refactor:` y descripción breve en español.
