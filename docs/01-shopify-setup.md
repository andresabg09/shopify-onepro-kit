# 01 · Setup de Shopify

Todo lo que hay que dejar listo en Shopify antes de pegar los bloques.
Se hace **una vez por producto** (algunas cosas solo una vez en total, marcadas
como *· una vez*).

---

## 1. Tienda

- [ ] Plan activo (Basic alcanza para una tienda de un solo producto)
- [ ] Moneda del checkout correcta para el mercado objetivo
- [ ] Tema base instalado — cualquier tema gratuito de Shopify sirve, los
      bloques Custom Liquid re-estilan lo esencial. **Dawn** es el más limpio
      para partir de él.
- [ ] Duplicar el tema antes de tocar nada (ver `02-como-pegar-bloques.md`)

## 2. Producto — importar desde AutoDS

1. En AutoDS, conectar la tienda de Shopify (si no está ya conectada — *una vez*)
2. Importar el producto elegido en Fase 0 del flujo
3. Revisar y **fijar el precio de venta manualmente** — el precio automático
   de AutoDS suele ser conservador; recalcula con el margen del brief
4. Revisar variantes: eliminar las que no interesan (colores feos, tallas sin
   sentido) para no diluir la decisión de compra
5. Revisar imágenes importadas — sustituir las que tengan marcas de agua o
   fondos sucios por las de mejor calidad del proveedor
6. Confirmar tiempo de envío estimado — este dato va literal en el FAQ y en
   la página de envíos, no se puede prometer de más

## 3. Subdominio — `<marca>.automatepty.com`

*(una vez por producto nuevo, la configuración del dominio raíz es de una sola vez)*

**En el proveedor DNS de AutomatePTY.com** (donde se compró el dominio):

1. Añadir registro `CNAME`:
   - Host: `<marca>` (ej. `lumea`)
   - Apunta a: `shops.myshopify.com`
2. Esperar propagación (minutos a un par de horas)

**En Shopify:**

1. Admin → **Configuración → Dominios → Conectar dominio existente**
2. Introducir `<marca>.automatepty.com`
3. Shopify verifica el CNAME y emite SSL automáticamente (puede tardar hasta
   48 h, normalmente minutos)
4. Marcar como dominio principal de la tienda

> Cada producto nuevo = un subdominio nuevo. El dominio raíz `automatepty.com`
> queda libre; no lo apuntes a ninguna tienda de producto.

## 4. Pagos

- [ ] Shopify Payments activo (o la pasarela disponible en tu país — Panamá
      puede requerir un proveedor de terceros; revisar disponibilidad)
- [ ] Métodos alternativos si aplica (tarjeta, billeteras digitales)
- [ ] **Prueba de pago real completada** antes de lanzar ads (Fase 4 del flujo)

## 5. Envíos

- [ ] Zona de envío configurada para el mercado objetivo
- [ ] Tarifa de envío coherente con el copy ("envío gratis" en la barra de
      anuncio implica que la tarifa configurada es $0, o el margen ya lo
      absorbe)
- [ ] Tiempos de entrega en la política de envíos coinciden con los del brief

## 6. Páginas y políticas — *obligatorio, no cosmético*

Sin esto, Meta/TikTok Ads puede rechazar la cuenta y las pasarelas de pago
pueden retener fondos.

- [ ] **Política de envíos** (Configuración → Políticas, genera plantilla base)
- [ ] **Política de devoluciones/reembolsos**
- [ ] **Política de privacidad**
- [ ] **Términos del servicio**
- [ ] **Página de contacto** con email real (el que va en `03-footer.liquid`)
- [ ] Datos de la empresa/operador visibles (nombre legal, país) — va en el
      footer como `LEGAL_NAME`

## 7. Checkout y emails

- [ ] Editar el email de confirmación de pedido (Configuración → Notificaciones)
      — el de Shopify por defecto es genérico, al menos poner el logo/nombre
- [ ] Revisar el texto del checkout (Configuración → Checkout) — quitar
      cualquier mención al tema original

## 8. Tracking

- [ ] Meta Pixel + Conversions API conectados (Configuración → Apps y canales
      de venta, o vía el Pixel de Shopify)
- [ ] TikTok Pixel si se usa ese canal
- [ ] Google Analytics 4 (opcional pero recomendable)
- [ ] Verificar eventos `ViewContent`, `AddToCart`, `Purchase` en el Event
      Manager con una compra de prueba real

## 9. App store — lo mínimo, no más

Regla del repo: **cuantas menos apps, más rápida y más limpia la tienda.**
Los bloques Custom Liquid ya cubren countdown/reviews/upsell de forma nativa
y sin JS de terceros. Antes de instalar una app, comprobar si ya lo resuelve
uno de los 3 bloques.

Si hace falta algo que el repo no cubre (ej. reseñas importadas con fotos):

- [ ] Verificar que la app no inyecta su propio CSS agresivo sobre `.op-*`
- [ ] Medir el impacto en PageSpeed antes/después de instalarla
