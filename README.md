# Previsualizador de grilla PLP — BURGUES

App de una sola página (React + Tailwind vía CDN, sin backend, todo en memoria/localStorage del navegador) para previsualizar el orden de la grilla de productos de una categoría antes de cargarlo en Magento.

## Uso
Es un único archivo HTML autocontenido (`index.html`). No requiere build ni instalación: se abre directamente en el navegador (doble clic, o servido como archivo estático desde cualquier hosting/CDN).

Carga las librerías (React, ReactDOM, Babel standalone, Tailwind) desde CDN en tiempo de ejecución, así que necesita conexión a internet la primera vez que se abre.

## Pestañas
- **Carga**: en dos pasos —
  1. Subir (o pegar) el catálogo maestro `base.csv` (columnas: `sku;name;categoria;price;special_price;link_imagen;link_producto;talles;...`). Queda guardado en el navegador, no hace falta repetirlo cada vez.
  2. Pegar (o subir un archivo con) la lista de SKUs a mostrar, en el orden deseado. La app completa nombre, precio, categoría, imagen, talles disponibles y link del producto automáticamente desde la base, y avisa si algún SKU no se encuentra.
- **Grilla**: previsualización tipo PLP con el orden inicial igual al de la lista de SKUs pegada, reordenable con drag & drop. El listado de SKUs exportado/copiado siempre refleja el orden final de la grilla. También existe un botón opcional para recalcular el orden automáticamente según descuento y reglas de adyacencia de categoría/artículo.
  - Si la base tiene columna de talles (`talles`, `talles_disponibles` o `sizes`, con valores separados por `,` `/` o `|`), se muestran como una franja sutil abajo de la imagen.
  - Si la base tiene `link_producto`, la imagen es un link a `https://www.burgues.com/<link_producto>` que abre en una pestaña nueva.

Tanto la base de productos como la grilla generada se guardan en el `localStorage` del navegador donde se abra el archivo (en claves separadas, así reemplazar la base no borra la grilla y viceversa).
