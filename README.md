# Previsualizador de grilla PLP — BURGUES

App de una sola página (React + Tailwind vía CDN, sin backend, todo en memoria/localStorage del navegador) para previsualizar el orden de la grilla de productos de una categoría antes de cargarlo en Magento.

## Uso
Es un único archivo HTML autocontenido (`index.html`). No requiere build ni instalación: se abre directamente en el navegador (doble clic, o servido como archivo estático desde cualquier hosting/CDN).

Carga las librerías (React, ReactDOM, Babel standalone, Tailwind) desde CDN en tiempo de ejecución, así que necesita conexión a internet la primera vez que se abre.

## Pestañas
- **Carga**: importar CSV (`sku,name,price,special_price,url_img`) o cargar productos a mano en una tabla editable.
- **Grilla**: previsualización tipo PLP con el orden calculado (descuento + reglas de adyacencia de categoría/artículo), reordenable con drag & drop, exportable a CSV.

Los datos cargados se guardan en el `localStorage` del navegador donde se abra el archivo.
