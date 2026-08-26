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

- **Quién es:** Mujeres de 22-45 años. Ya tienen rutina de cuidado facial —
  el producto se integra a algo que ya hacen, no es un hábito nuevo que
  crear.
- **Qué le duele (el problema real, en sus palabras):** Ojeras (genéticas o
  por ritmo de vida agotador) + hinchazón por exceso de pantallas.
- **Qué ha intentado antes y le falló:** `TBD confirmar` — propuesta:
  corrector/concealer (tapa, no alivia), cremas de venta libre (resultado
  lento o nulo)
- **Qué objeción le frena a comprar:** `TBD confirmar` — propuesta: duda de
  que un aparato de $60 rinda más que uno de $8; miedo a que sea "otro
  gadget que junta polvo en el cajón"
- **Dónde está:** `TBD confirmar` — propuesta: Instagram/TikTok, contenido
  de rutina nocturna de skincare

> Lo marcado `TBD confirmar` es mi mejor propuesta a partir de lo que ya
> dijiste, no un dato tuyo. Ajústalo si no encaja.

### Nota — deseo del cliente vs. claim permitido
La clienta busca algo "garantizado y comprobado". Eso es lo que **siente
que necesita**, no algo que el copy pueda prometer literal (ver
`docs/05-claims-y-legal.md`). Se traduce a mecanismo concreto (EMS + luz
roja) y a la garantía real de 30 días — nunca a "resultado garantizado".

## 4. Posicionamiento

- **Promesa central:** "Una mirada descansada, aunque la noche no haya
  ayudado" — enfoque en apariencia/resultado visible, sin claim médico
- **Mecanismo:** Microcorriente (EMS) + luz roja LED en la zona del
  contorno de ojos, como parte del ritual nocturno de skincare
- **Diferenciador vs. la alternativa barata:** 3 niveles de intensidad
  ajustables · carga USB-C (30 min → 90 min de uso) · certificación CE ·
  garantía de 30 días. El de $8 típicamente no trae nada de esto y falla
  en semanas.
- **Prueba:** **Ninguna todavía.** Tienda nueva = cero reseñas reales.
  Sección de testimonios **oculta** en el lanzamiento hasta tener clientas
  reales (ver checklist más abajo).

## 5. Copy — bloques clave

**Ya escrito** en `02-header.liquid`/`02-template.liquid` de esta carpeta.
Resumen (ver el `.liquid` para la versión bilingüe completa):

| Elemento | ES |
|---|---|
| Eyebrow | Ritual de 15 minutos |
| H1 | Una mirada descansada, aunque la noche no haya ayudado |
| Subtítulo | Microcorriente y luz roja en tu rutina de siempre, antes de dormir |
| CTA | Empezar mi ritual |
| Micro-confianza | Envío gratis · Garantía de 30 días · Certificado CE |

**Pendiente (necesita un número real, no se inventa):** el ángulo de
"recuperas tu dinero" que propusiste — falta comparar contra el gasto
mensual real en corrector/parches para ojeras. Se añade cuando tengamos
ese dato.

**Testimonios:** vacíos a propósito. `SHOW_REVIEWS = false` en el bloque de
plantilla — ver Sección 4.

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
| `--op-accent` | `#4A3B47` | Ciruela apagado — conecta con "noche/descanso" sin lila genérico de belleza |
| `--op-accent-ink` | `#FFFFFF` | |
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
