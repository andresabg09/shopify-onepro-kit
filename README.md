# shopify-onepro-kit

Sistema reutilizable para montar tiendas Shopify de **un solo producto**.

Cambiar de producto no debería significar rehacer la tienda desde cero. Este
repo guarda el diseño, la estructura de la landing y el proceso; lo único que
cambia entre un producto y el siguiente es el contenido del *brief*.

---

## Arranque rápido

```bash
git clone https://github.com/andresabg09/shopify-onepro-kit.git
cd shopify-onepro-kit
claude          # CLAUDE.md se carga solo: no hay que explicar nada
```

Después, en Claude Code:

> **nuevo producto** — y pasar el link de AutoDS.

## Los 3 bloques

Shopify agrupa el editor de temas en tres zonas. Este repo genera un bloque
`Custom Liquid` para cada una:

| Zona | Archivo | Contenido |
|---|---|---|
| Encabezado | `01-header.liquid` | Tokens de diseño, fuentes, barra de anuncio |
| Plantilla | `02-template.liquid` | Landing completa del producto |
| Pie de página | `03-footer.liquid` | Confianza, políticas, newsletter |

Se pegan **en ese orden**. El de Encabezado define las variables CSS que usan
los otros dos.

Instrucciones detalladas: [`docs/02-como-pegar-bloques.md`](docs/02-como-pegar-bloques.md)

## Documentación

| Doc | Para qué |
|---|---|
| [00 — Flujo de producto nuevo](docs/00-flujo-nuevo-producto.md) | Checklist de lanzamiento, de AutoDS a la primera venta |
| [01 — Setup de Shopify](docs/01-shopify-setup.md) | Tienda, tema, subdominio, pagos, envíos |
| [02 — Cómo pegar los bloques](docs/02-como-pegar-bloques.md) | Paso a paso en el editor de temas |
| [03 — Sistema de diseño](docs/03-sistema-de-diseno.md) | Tokens, tipografía, espaciado, reglas |
| [04 — Copywriting](docs/04-copywriting.md) | Estructura de la landing y fórmulas ES/EN |
| [05 — Claims y legal](docs/05-claims-y-legal.md) | Qué se puede afirmar y qué no |
| [06 — AutoDS](docs/06-autods.md) | Importar, precios, tiempos de envío |

## Estructura

```
plantillas/     Base neutra. No se edita por producto.
productos/      Una carpeta por producto. brief.md es la fuente de verdad.
  _archivo/     Productos descartados + post-mortem
docs/           Manuales de proceso
preview/        Vista local de la landing, sin Shopify
```

## Estado

Producto activo: ver [`productos/ACTUAL.md`](productos/ACTUAL.md)
