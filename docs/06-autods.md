# 06 · AutoDS

Cómo se usa AutoDS dentro de este repo, tanto desde la app como desde las
herramientas MCP conectadas en Claude Code.

---

## Conexión

AutoDS está conectado como servidor MCP (`claude_ai_AutoDS`). Herramientas
disponibles en esta sesión:

| Herramienta | Para qué |
|---|---|
| `get_current_user` | Verificar la cuenta conectada |
| `list_stores_api` | Listar las tiendas Shopify vinculadas |
| `search_products` | Buscar productos por palabra clave |
| `get_winning_products` | Productos con buen rendimiento validado (punto de partida ideal en Fase 0) |
| `get_recommended_products` | Recomendaciones personalizadas |
| `get_similar_products` | Alternativas a un producto dado — útil al rotar |
| `get_product_by_id` | Ficha completa: coste, envío, variantes, imágenes |
| `list_products` | Productos ya importados a la tienda |
| `upload_products` | Importar producto(s) a la tienda Shopify conectada |
| `get_bulk_action_items` | Estado de importaciones/acciones en lote |
| `publish_drafts_to_marketplace` | Publicar borradores |

Si alguna aparece como *deferred* (no cargada), se carga con:
`ToolSearch("select:mcp__claude_ai_AutoDS__<nombre>")` antes de usarla —
Claude lo hace automático al ejecutar el flujo.

## Flujo típico dentro de "nuevo producto"

1. `get_current_user` + `list_stores_api` → confirmar tienda destino
2. Buscar candidatos:
   - Con idea concreta → `search_products`
   - Sin idea concreta → `get_winning_products` o `get_recommended_products`
   - Para rotar desde un producto que falló → `get_similar_products` con el
     ID del producto anterior
3. `get_product_by_id` sobre el finalista → extraer coste, envío, variantes,
   imágenes para rellenar `brief.md`
4. Decisión humana en Fase 0 (`docs/00-flujo-nuevo-producto.md`) — AutoDS da
   datos, no decide el ángulo ni el posicionamiento
5. `upload_products` → importa a Shopify
6. `get_bulk_action_items` → confirmar que la importación terminó sin errores
7. Fijar precio de venta manualmente en Shopify (el margen se calcula en el
   brief, no se confía en el precio sugerido)

## Qué copiar al brief desde AutoDS

| Campo del brief | Viene de |
|---|---|
| Coste proveedor | `get_product_by_id` → cost |
| Envío (coste/días) | `get_product_by_id` → shipping |
| Variantes | `get_product_by_id` → variants |
| Imágenes | `get_product_by_id` → images (revisar calidad antes de usar) |
| Certificaciones | Ficha del proveedor, si las declara |

## Señales para descartar un producto en `get_winning_products`

Que aparezca como "ganador" en AutoDS no lo hace apto para *este* sistema
(tienda premium, un solo producto, sin trucos de urgencia falsa):

- Depende de que el anuncio prometa algo que el disclaimer legal no permite
  sostener (ver `05-claims-y-legal.md`)
- Fotos irrecuperables (baja resolución, marcas de agua imposibles de quitar,
  fondos que no se pueden limpiar)
- Envío > 15 días al mercado objetivo
- Margen que no llega a 3× con el precio de venta realista del mercado
- Producto ya saturado con el mismo ángulo obvio en TikTok/Meta — si el
  primer resultado al buscarlo ya es "as seen on TikTok" con el mismo hook,
  hace falta un ángulo distinto o pasar al siguiente candidato

## Al rotar de producto

`get_similar_products` con el ID del producto archivado es el punto de
partida más rápido — mantiene la categoría que ya se investigó (mercado,
proveedor, tiempos de envío conocidos) mientras cambia el ángulo o el
producto exacto. Combinarlo con el post-mortem de `notas-rendimiento.md`
para no repetir el mismo error de ángulo.
