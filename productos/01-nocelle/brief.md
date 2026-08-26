# Brief de producto — Nocelle

> Fuente de verdad del producto. Los 3 bloques `.liquid` de esta carpeta se
> generan únicamente a partir de este archivo.

---

## 1. Identidad

| Campo | Valor |
|---|---|
| Marca | **Nocelle** |
| Subdominio | `nocelle.automatepty.com` |
| Slug interno | `01-nocelle` |
| Handle en Shopify | `TBD` — se define al crear el producto en Shopify |
| Fecha de lanzamiento | `TBD` |
| Plazo de prueba | `TBD` — pendiente definir presupuesto de ads y días de prueba |
| Criterio de muerte | `TBD` — pendiente definir con Andrés (ver Fase 0 del flujo) |

## 2. Producto

| Campo | Valor |
|---|---|
| Qué es (una frase) | Masajeador de contorno de ojos con EMS (microcorriente) + luz roja |
| Link AutoDS | https://platform.autods.com/marketplace/all-products/6883e54ab6360464c542ac24 |
| ID AutoDS | `6883e54ab6360464c542ac24` |
| Proveedor origen | AliExpress — "Stone's Store" (marca en listado: foreverlily) |
| Coste proveedor | **$16.92** |
| Envío (coste / días) | **Gratis / 10 días** (almacén US) |
| Precio de venta | **$59.99** |
| Precio tachado (compare-at) | **$89.99** (-33%) |
| Margen bruto | **$43.07 (3.55×)** — cumple la regla de ≥3× |
| Variantes | 1 activa ("Type A"). Existe una "Type B" en la descripción del proveedor pero **no está cargada como variante comprable** — no ofrecer en la tienda hasta confirmarla en AutoDS |
| Peso / dimensiones | 38 g · 14 × 15 cm |
| Certificaciones | CE |
| Stock disponible (al momento del brief) | 41 unidades |
| Señal de demanda | 4.9★ · 1,022 valoraciones · 4,000 pedidos en el listado origen |

## 3. Cliente

- **Quién es:** `TBD`
- **Qué le duele (el problema real, en sus palabras):** `TBD`
- **Qué ha intentado antes y le falló:** `TBD`
- **Qué objeción le frena a comprar:** `TBD`
- **Dónde está:** `TBD`

> ⚠️ Esta sección no se puede automatizar — es la decisión de Andrés.
> Sin esto no se escribe el copy (H1, dolores, FAQ). Ver conversación para
> las 3 preguntas pendientes.

## 4. Posicionamiento

- **Promesa central:** `TBD`
- **Mecanismo:** `TBD`
- **Diferenciador vs. la alternativa barata:** `TBD`
- **Prueba:** `TBD`

## 5. Copy — bloques clave

`TBD` — se completa después de definir Secciones 3 y 4.

## 6. Recursos visuales

| Recurso | Estado | URL / ruta |
|---|---|---|
| Imágenes del proveedor (25) | Disponibles, sin revisar calidad | `productos/01-nocelle/imagenes/urls-proveedor.txt` |
| Imagen hero elegida | `TBD` | — |
| Vídeo de uso | No disponible en el listado origen | — |
| Logo / wordmark | `TBD` | — |

> Antes de usar cualquier imagen del proveedor: revisar que no tenga texto en
> chino ni marcas de agua. Ver `docs/00-flujo-nuevo-producto.md` Fase 1.

## 7. Diseño

| Token | Valor | Nota |
|---|---|---|
| `--op-accent` | `TBD` | Pendiente — se decide con el posicionamiento (Sección 4) |
| `--op-accent-ink` | `TBD` | |
| Fuente titular | Fraunces (por defecto del sistema) | |
| Fuente cuerpo | Inter (por defecto del sistema) | |

## 8. Legal y claims

- [ ] Copy revisado contra `docs/05-claims-y-legal.md`
- [x] **Alerta ya registrada:** la descripción original del proveedor usa
      "reduce dark circles", "reduce eye wrinkles", "metabolize melanin" —
      **no se puede copiar literal**. Traducir a lenguaje seguro al escribir
      el copy ("ayuda a reducir la apariencia de", nunca "elimina").
- [ ] Disclaimer añadido al footer (ya incluido por defecto en
      `03-footer.liquid`, revisar que siga ahí)
- [ ] Políticas publicadas: envío, devoluciones, privacidad, términos
- [ ] Datos de contacto reales y visibles

## 9. Checklist de lanzamiento

- [ ] Producto importado desde AutoDS con precio $59.99 / compare $89.99
- [ ] Los 3 bloques pegados y revisados en móvil
- [ ] Subdominio `nocelle.automatepty.com` conectado con SSL activo
- [ ] Pago de prueba completado de principio a fin
- [ ] Email de confirmación de pedido revisado
- [ ] Píxel / Conversions API instalado y disparando
- [ ] Velocidad móvil comprobada (PageSpeed > 60)

## Historial de decisiones

| Fecha | Decisión | Motivo |
|---|---|---|
| 2026-08-26 | Precio fijado en $59.99 (compare $89.99) | Cumple regla de margen ≥3×; coincide con el rango de venta sugerido por AutoDS ($47.94–$86.88, también = 3× costo) |
| 2026-08-26 | Marca "Lumina" descartada | Conflicto directo con competidor real "Lumina NRG" (vende el mismo tipo de producto: eye massage wand) |
| 2026-08-26 | Marca "Lumael" descartada | Conflicto con "Lumaé", marca de belleza enfocada en contorno de ojos |
| 2026-08-26 | Marca "Velure" descartada | Espacio de nombres saturado (Veloura, Velura, Vellura, Velare) |
| 2026-08-26 | Marca fijada: **Nocelle** | Sin conflictos encontrados en búsqueda web; funciona en ES/EN |
