# 00 · Flujo de producto nuevo

De "tengo un producto candidato" a "la tienda está viva". Este es el checklist
que se repite cada vez que se rota de producto.

---

## Fase 0 — Decidir (antes de tocar nada)

Un producto entra al sistema solo si pasa estos filtros. Si falla uno, no se
lanza: ahorrarse esta media hora cuesta semanas después.

- [ ] **Margen ≥ 3×** sobre el coste con envío incluido. Con 2× no hay dinero
      para ads y el producto muere aunque convierta.
- [ ] **Envío ≤ 15 días** al mercado objetivo. Por encima, la tasa de
      reembolsos se come el margen.
- [ ] **Resuelve un problema con nombre.** Si el cliente no puede describir su
      problema en una frase, no hay copy posible.
- [ ] **Fotos y vídeo utilizables** del proveedor, o presupuesto para hacerlos.
- [ ] **No es categoría restringida** en Meta/TikTok Ads (ver `05-claims-y-legal.md`).
- [ ] **Existe el ángulo** que lo hace distinto de la versión de $4 en Amazon.

Define ahora el **criterio de muerte** y escríbelo en el brief:
> "Si al gastar $X en ads el CPA supera $Y o la conversión está bajo Z%, archivo."

Sin criterio de muerte escrito de antemano, se acaba echando dinero bueno tras
el malo. Es la regla más importante de todo el repo.

## Fase 1 — Brief

```
En Claude Code:  nuevo producto
```

1. Pasar el link o ID de AutoDS. Claude extrae coste, envío, variantes e
   imágenes con las herramientas `mcp__claude_ai_AutoDS__*`.
2. Se crea `productos/<NN>-<slug>/` a partir de `plantillas/`.
3. Se rellena `brief.md`. Las secciones 3 (cliente) y 4 (posicionamiento) son
   las que no se pueden automatizar: hay que pensarlas.
4. Elegir el color de acento y comprobar contraste (ver `03-sistema-de-diseno.md`).

## Fase 2 — Shopify

Ver `01-shopify-setup.md` para el detalle. Resumen:

- [ ] Producto importado desde AutoDS con precio de venta fijado
- [ ] Variantes y stock correctos
- [ ] Políticas publicadas (envío, devoluciones, privacidad, términos)
- [ ] Página de contacto con datos reales
- [ ] Subdominio `<marca>.automatepty.com` conectado, SSL activo
- [ ] Pasarela de pago activa y probada

## Fase 3 — Los 3 bloques

Ver `02-como-pegar-bloques.md`.

- [ ] `01-header.liquid` pegado en **Encabezado**
- [ ] `02-template.liquid` pegado en **Plantilla**
- [ ] `03-footer.liquid` pegado en **Pie de página**
- [ ] Secciones del tema que duplican contenido, ocultadas
- [ ] Revisado en móvil real, no solo en el previsualizador

## Fase 4 — Verificación antes de gastar en ads

Esta fase se salta siempre y es la que más dinero quema.

- [ ] **Compra de prueba completa**: añadir al carrito → checkout → pago →
      email de confirmación. De principio a fin, con dinero real.
- [ ] Email de confirmación revisado (el de Shopify por defecto es feo; editarlo)
- [ ] Píxel de Meta / TikTok instalado, Conversions API conectada
- [ ] Eventos `ViewContent`, `AddToCart` y `Purchase` disparando de verdad
      (comprobar en el Event Manager, no asumir)
- [ ] PageSpeed móvil > 60
- [ ] Los 3 bloques revisados en Safari iOS (el `env(safe-area-inset)` de la
      ATC fija se comporta distinto)

## Fase 5 — Lanzar y medir

Registrar en `productos/<slug>/notas-rendimiento.md`, cada 48 h:

| Fecha | Gasto | Impresiones | CTR | Sesiones | ATC | Compras | CPA | Ingresos |
|---|---|---|---|---|---|---|---|---|

**Diagnóstico rápido según dónde se rompe el embudo:**

| Síntoma | Dónde está el problema |
|---|---|
| CTR bajo en ads | El creativo o el ángulo, no la tienda |
| CTR bien, pocas sesiones útiles | Velocidad de carga o mismatch ad↔landing |
| Sesiones bien, ATC bajo | Hero, precio u oferta poco claros |
| ATC bien, compras bajas | Checkout, gastos de envío sorpresa, o confianza |
| Compras bien, margen malo | Precio mal fijado — revisar Fase 0 |

## Fase 6 — Archivar

Cuando se cumple el criterio de muerte:

```bash
git mv productos/<slug> productos/_archivo/<slug>
```

Rellenar el post-mortem en `notas-rendimiento.md`. Tres preguntas:

1. ¿En qué punto del embudo se rompió?
2. ¿Fue el producto, el ángulo o la ejecución?
3. ¿Qué se hace distinto en el siguiente?

Actualizar `productos/ACTUAL.md` y volver a Fase 0.
