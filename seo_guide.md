# Guía de SEO Local Agresivo y Plantilla de Prompt Reutilizable

Esta guía sirve como marco metodológico y plantilla de prompt interactiva y universal para auditar y optimizar sitios web de pequeños y medianos negocios con un enfoque de **SEO Local Agresivo**. Su objetivo es lograr el máximo posicionamiento orgánico en búsquedas por proximidad y consultas transaccionales específicas en la zona de influencia del negocio.

---

## 1. Auditoría NAP y Consistencia de Datos (Nombre, Dirección, Teléfono)

El primer paso de cualquier campaña de SEO local es garantizar la **consistencia NAP (Name, Address, Phone)** absoluta. Las discrepancias de datos confunden a los motores de búsqueda y dañan la reputación de confianza del sitio.

### Lista de Chequeo NAP:
- [ ] **Consistencia de Teléfonos:**
  - El teléfono expuesto visualmente en cabeceras, pies de página o secciones de contacto debe ser *exactamente el mismo* que se utiliza en los enlaces interactivos (`tel:` o links de chat como `https://wa.me/`).
  - Debe coincidir con el teléfono principal del Perfil de Negocio en Google (Google Business Profile / GMB).
- [ ] **Consistencia de Dirección:**
  - La dirección textual expuesta en la web debe coincidir letra por letra con la dirección registrada en Google Maps.
  - Asegurar que referencias clave locales (mercados, centros comerciales, urbanizaciones o avenidas principales) estén redactadas de igual forma.
- [ ] **Consistencia de Nombre de Marca:**
  - Utilizar el nombre comercial oficial de forma consistente en todo el sitio, incluyendo las páginas legales (Políticas de Privacidad, Términos y Condiciones).
- [ ] **Crawlability de Páginas de Soporte:**
  - Asegurar que páginas legales o de políticas lleven `<meta name="robots" content="noindex, follow" />`. Esto evita que indexen y canibalicen las búsquedas principales, pero permite que los robots rastreen sus enlaces para transferir autoridad interna (*link juice*).

---

## 2. Estructura Semántica de Encabezados y Metadatos

### Título y Descripción de la Página (SEO On-Page)
El tag de título debe seguir una estructura que priorice la categoría de negocio y la ubicación geográfica antes del nombre de marca:
*   **Estructura del Título (máx. 60 caracteres):** `[Categoría Principal] y [Subcategoría/Servicio] en [Referencia/Barrio] - [Distrito/Ciudad] | [Nombre del Negocio]`
    *   *Ejemplo:* `Tienda de Cosméticos y Tintes en VMT José Gálvez - Mercado Ateca | Zafiro Color`
*   **Estructura de la Descripción (máx. 155 caracteres):** Debe iniciar con un verbo de acción, incluir las palabras clave locales primarias y cerrar con un llamado a la acción claro (CTA).
    *   *Ejemplo:* `Compra cosméticos y tintes por mayor y menor en José Gálvez, VMT (Mercado Ateca). Artículos de belleza y cuidado personal económicos. ¡Escríbenos!`

### Jerarquía Semántica (H1-H4)
*   **`<h1>` (Único en la página):** Debe contener el nombre del negocio y su actividad principal asociada a la ubicación local más representativa.
*   **`<h2>` (Secciones principales):** Enfocados en resolver intenciones de búsqueda localizadas (ej. "¿Cómo llegar a nuestra tienda en [Ubicación]?", "Distribución al por mayor para negocios locales").
*   **`<h3>` (Sub-elementos / Catálogos):** Para detallar tipos de servicios, marcas o productos que ofrece el negocio, tejiendo palabras clave geográficas secundarias.

---

## 3. Enriquecimiento del Marcado de Datos Estructurados (JSON-LD)

No limites el marcado al tipo genérico `LocalBusiness`. Utiliza la subclase más específica de Schema.org según la categoría de negocio principal configurada en Google Maps:

| Tipo de Negocio GMB | Tipo de Schema.org Recomendado |
| :--- | :--- |
| Tienda de Cosméticos / Belleza | `CosmeticStore` |
| Salón de Belleza / Peluquería | `BeautySalon` / `HairSalon` |
| Restaurante / Cafetería | `Restaurant` / `CafeOrCoffeeShop` |
| Tienda de Ropa | `ClothingStore` |
| Tienda General / Distribuidora | `Store` / `WholesaleStore` |
| Florería | `Florist` |
| Servicio Profesional (Abogado, etc.) | `ProfessionalService` |
| Consultorio Médico / Clínica | `MedicalBusiness` / `Physician` |

### Propiedades Clave de SEO Local en JSON-LD:
1.  **`alternateName`**: Nombres comunes, siglas o abreviaciones que el público local usa para buscar el negocio.
2.  **`hasMap` / `map`**: URL corta oficial para compartir la ubicación desde Google Maps.
3.  **`currenciesAccepted` & `paymentAccepted`**: Divisas locales (ej. `USD`, `PEN`, `MXN`) y métodos de pago permitidos (ej. `Cash, Credit Card, Mobile Transfer`).
4.  **`priceRange`**: Indicador estándar de rango de precios (ej. `$$` o `S/ - S$$`).
5.  **`hasOfferCatalog`**: Desglose estructurado de las principales categorías de productos o servicios del negocio para vincular semánticamente la oferta con palabras clave en los motores de búsqueda.

---

## 4. Copywriting de Enfoque Local y Densidad de Palabras Clave

El texto visible del sitio web debe optimizarse para búsquedas geográficas y transaccionales del vecindario o zona de influencia:
- **Redacción de Identidad Local:** Declarar abiertamente el tamaño del negocio, nivel de precios y público objetivo (ej. *"Somos una ferretería mediana bien abastecida enfocado en dar precios de distribuidor a los vecinos de..."*).
- **Integración de Hitos y Puntos Geográficos:** Incorporar avenidas principales, paraderos de transporte público, monumentos o mercados reconocidos de la zona.
- **Uso de Términos del Historial de Búsquedas (GMB Insights):** Revisar periódicamente los términos de búsqueda que activan la ficha de negocio (incluso si tienen errores ortográficos o están en otros idiomas) e integrarlos con naturalidad en el cuerpo de texto.

---

## 5. SEO de Imágenes y Carga Eficiente

- **Atributos `alt` Descriptivos y Locales:** Evitar etiquetas `alt` vacías o genéricas (ej. `alt="imagen1"`). Cada imagen de producto, local o servicio debe describir el objeto de la foto, la marca y un sufijo de ubicación local de forma rotativa:
  - *Fórmula alt:* `[Nombre del Producto/Servicio] [Marca] - [Categoría de Negocio] en [Ubicación/Distrito]`
- **Fetch Priority y Lazy Loading:**
  - La imagen principal (hero banner o logotipo arriba del pliegue) debe configurarse con `fetchpriority="high"` y **no** debe llevar `loading="lazy"`.
  - Todas las imágenes ubicadas abajo del primer scroll deben configurarse con `loading="lazy"` para mejorar las métricas de rendimiento (LCP e INP).

---

## 6. Prompt Universal Reutilizable para IA (Fórmula de SEO Local)

*Copia y pega este prompt en cualquier asistente de Inteligencia Artificial para aplicar este marco de optimización local en cualquier sitio web:*

```markdown
Actúa como un experto en SEO Local Técnico y Copywriting Avanzado. Necesito que realices una optimización SEO Local agresiva para el sitio web del siguiente negocio.

--- DATOS DEL NEGOCIO ---
- Nombre comercial: [Ingresa el nombre del negocio]
- Actividad / Rubro principal: [Ej: Veterinaria / Restaurante / Odontología]
- Ubicación Física Completa: [Ingresa dirección, referencias, mercados o avenidas]
- Distrito / Ciudad / País: [Ingresa distrito, ciudad y país]
- Teléfono Oficial de Contacto: [Ingresa el teléfono oficial]
- Enlace Oficial de Google Maps: [Ingresa la URL de compartir ubicación de Maps]
- Categorías en Google My Business (GMB):
  1. [Categoría principal GMB]
  2. [Subcategoría 1]
  3. [Subcategoría 2]
- Términos de búsqueda con los que ya nos descubren: [Ingresa los términos de búsqueda de GMB Insights]
- Enfoque comercial de la tienda: [Ej: Tienda mediana bien abastecida, precios económicos por mayor y menor, no es premium]

--- INSTRUCCIONES DE EJECUCIÓN ---
Por favor, analiza el código fuente del sitio (HTML, CSS, Sitemap, etc.) y realiza las siguientes tareas:

1. AUDITORÍA NAP Y CONSISTENCIA:
   - Identifica y corrige cualquier incoherencia entre los teléfonos que aparecen en texto visible y los configurados en los enlaces de llamada o WhatsApp (href).
   - Asegúrate de unificar la dirección física y el nombre comercial en la página de inicio, pie de página y páginas legales.

2. METADATOS OPTIMIZADOS:
   - Modifica el `<title>` del archivo HTML aplicando la fórmula: "[Categoría Principal GMB] en [Zona/Referencia] | [Nombre del Negocio]".
   - Reelabora la `<meta name="description">` (máximo 155 caracteres) incluyendo palabras clave geográficas y una llamada a la acción orientada a conversión local.

3. SCHEMA ORG JSON-LD ENRIQUECIDO:
   - Reemplaza el marcado genérico "LocalBusiness" por la subclase más específica de Schema.org según el rubro (ej: CosmeticStore, Restaurant, HairSalon, etc.).
   - Añade propiedades clave: coordinates, currenciesAccepted, paymentAccepted, priceRange, hasMap, alternateName, sameAs y un "hasOfferCatalog" estructurado que detalle las categorías de productos/servicios para inyectar semántica local.

4. COPYWRITING LOCAL Y JERARQUÍA SEMÁNTICA DE ENCABEZADOS:
   - Reorganiza la jerarquía de encabezados (garantiza un solo H1 potente y H2-H3 optimizados para búsquedas locales).
   - Reescribe o inserta bloques de texto naturales donde se detallen nuestras categorías principales de GMB, nuestra ubicación (referencias locales) y nuestro enfoque comercial (precios accesibles, por mayor y menor, etc.).

5. SEO DE IMÁGENES:
   - Optimiza todos los atributos "alt" de las imágenes para que incluyan el nombre exacto del producto, marca y una keyword local de forma rotativa.
   - Asegura la correcta carga prioritaria (fetchpriority="high" en la cabecera y loading="lazy" en el resto de la página).

6. MAPA DE SITIO:
   - Actualiza la etiqueta <lastmod> en sitemap.xml con la fecha actual para notificar a los crawlers del cambio masivo.

Dame una explicación detallada de cada cambio realizado y por qué beneficia al SEO local del negocio.
```
