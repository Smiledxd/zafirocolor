# Contexto del Proyecto: Zafiro Color

## 1. Descripción General
**Zafiro Color** es una tienda de belleza, cuidado personal y productos profesionales para el cabello ubicada en Villa María del Triunfo (VMT José Gálvez), Lima, Perú. El proyecto consiste en una página web estática (landing page) optimizada para dispositivos móviles y de escritorio que presenta los productos destacados del catálogo, las marcas aliadas, la ubicación fiscal/física del negocio y ofrece canales de comunicación directa (como enlaces rápidos a WhatsApp). También incluye el cumplimiento de las normativas legales vigentes en Perú (Libro de Reclamaciones y políticas obligatorias).

## 2. Datos del Negocio
* **Nombre Comercial:** Zafiro Color
* **Titular / Propietaria:** ESPERANZA CABANILLAS BARBOZA (Persona Natural con Negocio)
* **DNI del Titular:** 41443807
* **RUC:** 10414438071
* **Domicilio Fiscal / Físico:** Mercado Ateca, Pueblo J.N. Progreso Grp 2 Mz. K Lt.17, Villa María del Triunfo, Lima, Perú
* **Correo de Contacto / Administración:** davidzt125@gmail.com
* **WhatsApp de Consultas / Pedidos:** +51 929 965 687

## 3. Estructura de Archivos del Proyecto
El proyecto está organizado con `index.html` en la raíz y las páginas secundarias agrupadas en la carpeta `pages/`:
```
zafirocolor/
├── README.md               <-- (Este archivo de documentación)
├── index.html              <-- Página principal (Landing Page)
├── pages/
│   ├── libro.html          <-- Libro de Reclamaciones Virtual
│   ├── privacidad.html     <-- Política de Privacidad de Datos Personales
│   ├── terminos.html       <-- Términos y Condiciones del Sitio Web
│   └── cookies.html        <-- Política de Cookies
├── css/
│   ├── style.css           <-- Estilos globales (Landing page, header, footer, etc.)
│   └── style2.css          <-- Estilos específicos (Formulario y páginas legales)
└── img/
    ├── hero.jpg            <-- Imagen principal de la landing page
    ├── libro.jpg           <-- Icono oficial del Libro de Reclamaciones
    ├── producto1.png       <-- Imagen del producto 1
    ├── producto2.png       <-- Imagen del producto 2
    ├── producto3.png       <-- Imagen del producto 3
    └── producto4.png       <-- Imagen del producto 4
```

## 4. Descripción detallada de los archivos
### 4.1. Páginas HTML
* **`index.html`**: Presenta la identidad de Zafiro Color. Cuenta con las siguientes secciones:
  * **Header:** Barra de navegación sticky con el logo, enlaces internos de anclaje (`Inicio`, `Productos`, `Marcas`, `Ubicación`, `Horarios`) y un botón directo a WhatsApp.
  * **Hero Section:** Presentación del negocio, listado de características de valor (productos originales, buenos precios, atención cercana) e imagen destacada.
  * **Marcas:** Carrusel animado con efecto infinito que muestra las marcas destacadas con las que se trabaja (Kativa, Pantene, Sedal, etc.).
  * **Productos destacados:** Catálogo visual básico de productos con nombre, descripción y precio.
  * **Ubicación y Contacto:** Mapa embebido de Google Maps del local comercial (Mercado Ateca) y listado de horarios de atención física.
  * **Footer:** Información de copyright, enlaces de navegación y la sección legal obligatoria que incluye accesos a la privacidad, términos, cookies y el enlace visual al Libro de Reclamaciones.
* **`libro.html`**: Formulario virtual del Libro de Reclamaciones que cumple con las normativas de protección al consumidor (INDECOPI). El formulario recopila:
  1. Identificación del Consumidor Reclamante (Datos personales o apoderado si es menor de edad).
  2. Identificación del Bien Contratado (Producto/Servicio, Monto y Descripción).
  3. Detalle de la Reclamación (Tipo: Reclamo o Queja, detalle del sustento y pedido del consumidor).
  * *Envío de Datos:* Las quejas son enviadas usando el servicio gratuito de `formsubmit.co` al correo configurado: `davidzt125@gmail.com`.
  * *Impresión/PDF:* El sitio cuenta con un botón interactivo que ejecuta `window.print()` estilizado específicamente con CSS para ocultar la cabecera/pie de página web y mostrar zonas de firmas impresas obligatorias por ley.
* **`privacidad.html`**: Cumple con la Ley N° 29733 (Ley de Protección de Datos Personales de Perú). Detalla la identidad del titular, la finalidad del tratamiento (atender consultas y gestionar el libro de reclamaciones), tiempo de conservación de datos y el ejercicio de derechos ARCO.
* **`terminos.html`**: Contrato legal entre la tienda y el visitante sobre la propiedad intelectual, veracidad de los datos enviados en los formularios y limitación de responsabilidades.
* **`cookies.html`**: Detalla el uso de cookies técnicas y de estadísticas dentro del sitio web.

### 4.2. Hojas de Estilo CSS
* **`css/style.css`**: Contiene la base de diseño del sitio:
  * Reset CSS global.
  * Uso de tipografía moderna *Poppins*.
  * Paleta de colores cálida y moderna con un gradiente vibrante principal (`#ff3b3b` a `#DC5083`) para llamadas a la acción, fondos oscuros contrastantes para el footer (`#0d1020`) y colores claros para secciones de información (`#fffaf7`).
  * Estructura responsiva de grid y flex adaptada a dispositivos móviles.
  * Efecto de carrusel continuo para la sección de marcas (`@keyframes scrollBrands`).
* **`css/style2.css`**: Define los estilos necesarios para el contenido legal y formularios. Para no afectar la consistencia del encabezado y pie de página generales de `style.css`, estos estilos se encuentran encapsulados bajo:
  * `.libro-seccion`: Contenedor base de fondo `#f4f7f6`.
  * `.container-libro`: Contenedor centrado y limitado del formulario (máximo 850px de ancho).
  * `.legal-content`: Estilos específicos para la lectura de documentos de términos y políticas (fuente Arial, alineación justificada, etc.).
  * `@media print`: Reglas específicas para la impresión física de la Hoja de Reclamación.

## 5. Integración con FormSubmit.co
El formulario de reclamaciones está conectado a:
`action="https://formsubmit.co/davidzt125@gmail.com"`

**Configuración Importante:**
* Redirección exitosa: Una vez enviado el formulario, redirige automáticamente al usuario de regreso a la página principal mediante el input oculto `_next` configurado con valor `index.html`.
* **Activación obligatoria:** Al subir el sitio y realizar el primer envío de prueba, llegará un correo de activación a `davidzt125@gmail.com` por parte de *FormSubmit.co*. Es mandatorio abrir el correo y hacer clic en **"Activate Form"** para que los siguientes formularios empiecen a llegar directamente al buzón.
