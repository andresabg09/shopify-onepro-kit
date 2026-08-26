# CLAUDE.md — Contexto permanente del proyecto

> Este archivo se carga automáticamente en cada sesión de Claude Code.
> **No hay que re-explicar el proyecto nunca.** Si algo cambia de forma
> permanente, se edita aquí. Si es específico de un producto, va en
> `productos/<slug>/brief.md`.

---

## 1. Qué es este repo

Un **sistema reutilizable** para montar tiendas Shopify de **un solo producto**
(single-product dropshipping store). No es la tienda de un producto concreto:
es la fábrica que produce esas tiendas.

Ciclo de vida esperado:

```
elegir producto → generar los 3 bloques → pegar en Shopify → vender
    ↓ (si no funciona en el plazo de prueba)
archivar en productos/_archivo/ con post-mortem → siguiente producto
```

El valor del repo está en que **el diseño, el sistema de tokens, la estructura
de la landing y el copy framework ya están resueltos**. Cambiar de producto
debe costar horas, no semanas.

## 2. Contexto fijo del negocio

| Dato | Valor |
|---|---|
| Operador | andresabg09 |
| Modelo | Dropshipping, un producto por tienda |
| Proveedores | **AutoDS** (conectado vía MCP en Claude Code) |
| Plataforma | Shopify |
| Método de deploy | **Bloques Custom Liquid** pegados en el editor de temas |
| Dominio paraguas | `AutomatePTY.com` — se usa **un subdominio por producto** |
| Idiomas | **Bilingüe ES + EN** (toggle `LANG` dentro de cada bloque) |
| Mercado | LATAM + US |

### Por qué subdominios
`AutomatePTY.com` es un dominio genérico ya comprado que no se relaciona con
ningún producto. Cada tienda vive en `<marca>.automatepty.com`. Un dominio,
infinitas marcas, coste cero al rotar de producto.

## 3. Método de deploy (leer antes de tocar Liquid)

Shopify agrupa las secciones del editor de temas en tres zonas. Este repo
produce **exactamente un bloque `Custom Liquid` por zona**:

| Zona del editor | Archivo | Qué contiene |
|---|---|---|
| **Encabezado** | `01-header.liquid` | Fuentes, tokens CSS globales, re-estilado del header nativo, barra de anuncio |
| **Plantilla** | `02-template.liquid` | La landing completa: hero, beneficios, prueba social, FAQ, CTA, ATC sticky |
| **Pie de página** | `03-footer.liquid` | Confianza, políticas, newsletter, iconos de pago, disclaimer legal |

**Reglas críticas:**

1. El bloque de **Encabezado** carga los tokens `:root`. Sin él, los otros dos
   se ven rotos. Siempre se pega primero.
2. **No se reemplaza el header nativo de Shopify.** Se re-estila con CSS. El
   carrito, el menú y la búsqueda del tema deben seguir funcionando.
3. Todo CSS va namespaceado bajo `.op-` (onepro) para no romper el tema.
4. Cero dependencias externas salvo Google Fonts. Nada de CDNs de JS.
5. El `<form action="/cart/add">` es el único camino al carrito. No inventar
   endpoints.

## 4. Estructura del repo

```
plantillas/          Base neutra reutilizable. NO se edita por producto.
  brief.template.md  Cuestionario que define un producto nuevo
  01-header.liquid   |
  02-template.liquid | los 3 bloques con placeholders
  03-footer.liquid   |
  tokens.css         Sistema de diseño (referencia legible)

productos/
  <NN>-<slug>/       Un producto = una carpeta
    brief.md         Ficha rellenada. FUENTE DE VERDAD del producto.
    01-header.liquid |
    02-template.liquid| bloques ya adaptados, listos para pegar
    03-footer.liquid |
    notas-rendimiento.md  Métricas y aprendizajes
  _archivo/          Productos descartados + post-mortem

docs/                Manuales de proceso (ver índice en README)
preview/             Vista local de la landing sin necesidad de Shopify
```

## 5. Cómo trabajar conmigo (Claude) en este repo

### Lanzar un producto nuevo
Cuando el usuario diga *"nuevo producto"*:

1. Preguntar por el link o ID de AutoDS, o buscarlo con las herramientas
   `mcp__claude_ai_AutoDS__*` (search_products, get_product_by_id,
   get_winning_products).
2. Crear `productos/<NN>-<slug>/` copiando `plantillas/`.
3. Rellenar `brief.md` con datos reales del proveedor (coste, envío, imágenes,
   variantes) + el posicionamiento decidido con el usuario.
4. Generar los 3 `.liquid` a partir del brief. **Solo se toca la ZONA EDITABLE**
   de cada archivo — el resto es estructura probada.
5. Actualizar `productos/ACTUAL.md` apuntando al nuevo slug.

### Archivar un producto que no funcionó
1. `git mv productos/<slug> productos/_archivo/<slug>`
2. Rellenar la sección post-mortem en `notas-rendimiento.md`: gasto en ads,
   CTR, tasa de conversión, CPA, y **la hipótesis de por qué falló**.
3. Ese post-mortem es lo que evita repetir el error en el producto siguiente.

### Principios de diseño no negociables
- **Minimalista, elegante, refinado.** Mucho aire, poca decoración.
- Máximo **un color de acento** por tienda. El resto es tinta/papel/gris.
- Tipografía: serif de alto contraste para titulares, sans neutra para cuerpo.
- Nada de: contadores de cuenta atrás falsos, "solo quedan 3", estrellas
  inventadas, sellos de pago falsos. Rompen la credibilidad de una tienda que
  se presenta como premium — y varias son ilegales en US/UE.
- Ver `docs/03-sistema-de-diseno.md` antes de inventar estilos nuevos.

### Claims de producto (importante)
Estos productos rozan el terreno salud/belleza. **Nunca** escribir copy que
prometa curar, eliminar o tratar una condición médica. Ver
`docs/05-claims-y-legal.md` para la lista de fórmulas seguras. Esto no es
opcional: es lo que separa una cuenta publicitaria activa de una baneada.

## 6. Producto actual

Ver **`productos/ACTUAL.md`**.
