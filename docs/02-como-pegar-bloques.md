# 02 · Cómo pegar los bloques en Shopify

Los 3 archivos `.liquid` de `productos/<slug>/` se pegan como secciones
**Custom Liquid** en el editor de temas. No hace falta Shopify CLI, ni tocar
el código del tema, ni conectar GitHub.

---

## Antes de empezar

**Trabaja siempre sobre una copia del tema.**

> Admin → Tienda online → Temas → (⋯) en tu tema → **Duplicar**

Editas el duplicado. Cuando esté bien, lo publicas. Si algo se rompe, el tema
original sigue intacto. Esto no es opcional: un Custom Liquid mal cerrado
puede dejar la tienda en blanco.

## Orden de pegado

El orden importa. `01-header` define las variables CSS (`--op-*`) que usan los
otros dos. Si pegas la plantilla primero, se verá sin estilos.

```
1. Encabezado    →  01-header.liquid
2. Plantilla     →  02-template.liquid
3. Pie de página →  03-footer.liquid
```

---

## Bloque 1 — Encabezado

1. Admin → **Tienda online → Temas → Personalizar**
2. En la barra superior, selecciona la plantilla **Producto** (o la home,
   según dónde vaya la landing).
3. En la barra lateral izquierda, grupo **Encabezado** → **Añadir sección**
4. Busca **Custom Liquid** (en español puede aparecer como *Liquid personalizado*)
5. Arrástralo **arriba del todo** del grupo Encabezado
6. Pega el contenido completo de `01-header.liquid` en el campo de código
7. **Guardar**

> Si tu tema no ofrece "Añadir sección" dentro del grupo Encabezado, usa el
> grupo Plantilla y coloca el bloque como primera sección. Funciona igual: lo
> único que importa es que el CSS se cargue antes que el resto.

## Bloque 2 — Plantilla

1. Grupo **Plantilla** → **Añadir sección** → **Custom Liquid**
2. Pega `02-template.liquid`
3. **Oculta las secciones del tema que ahora duplican contenido**: la ficha de
   producto nativa, la galería, las secciones de texto enriquecido, productos
   relacionados. Se ocultan con el icono del ojo — no hace falta borrarlas.
4. Deja visibles: el header nativo y el carrito.
5. **Guardar**

### Configurar el producto

Dentro de `02-template.liquid`, en la zona editable:

```liquid
{%- assign PRODUCT_HANDLE = 'handle-del-producto' -%}
```

El *handle* está en la URL del producto: `tutienda.com/products/<handle>`.

- En la **página de producto** el bloque usa el objeto `product` automáticamente
  y `PRODUCT_HANDLE` se ignora.
- En la **home** hace falta que `PRODUCT_HANDLE` sea correcto, o el hero
  mostrará el aviso de "no se encuentra el producto".

## Bloque 3 — Pie de página

1. Grupo **Pie de página** → **Añadir sección** → **Custom Liquid**
2. Pega `03-footer.liquid`
3. **Oculta el footer nativo del tema** para no duplicar enlaces
4. **Guardar**

---

## Cambiar de idioma

Cada bloque tiene, arriba del todo:

```liquid
{%- assign LANG = 'es' -%}
```

Cambia a `'en'` en **los tres** bloques. Todo el copy conmuta a inglés.

Si quieres las dos versiones vivas a la vez, necesitas dos tiendas o el sistema
de mercados de Shopify — no lo resuelve un toggle de Liquid.

---

## Problemas comunes

| Síntoma | Causa | Solución |
|---|---|---|
| Todo sin estilos, texto plano | Falta el bloque de Encabezado, o está por debajo | Pega `01-header` y súbelo al principio |
| "No se encuentra el producto" en el hero | `PRODUCT_HANDLE` mal escrito | Cópialo de la URL del producto |
| El botón no añade al carrito | La variante está agotada, o el tema intercepta el submit | Comprueba stock; prueba con el carrito en modo página en vez de drawer |
| Contenido duplicado | Secciones nativas del tema aún visibles | Ocúltalas con el icono del ojo |
| Las fuentes no cargan | El tema o una app bloquea recursos externos | Sustituye Google Fonts por la pila del sistema en `01-header` |
| La barra ATC fija tapa el footer en iOS | `env(safe-area-inset-bottom)` | Ya contemplado; si persiste, sube el `padding-bottom` del footer |

## Editar sin miedo

**Todo lo que hay que tocar está entre estas dos marcas:**

```liquid
{%- comment -%} ══════════ ZONA EDITABLE ══════════ {%- endcomment -%}
   ... aquí ...
{%- comment -%} ══════════ NO EDITAR DEBAJO ══════════ {%- endcomment -%}
```

Debajo de la segunda marca está la estructura probada. Si necesitas cambiarla,
hazlo en el repo y con Claude — no directamente en el editor de Shopify, donde
no hay historial ni forma de volver atrás.

### Formato de las listas

Varias secciones se generan desde una sola cadena:

```liquid
{%- assign HOW_ES = 'Título uno::Descripción uno.|Título dos::Descripción dos.' -%}
```

- `|` separa elementos
- `::` separa título de descripción

Añadir un elemento = añadir `|Título::Descripción`. La rejilla se adapta sola.
