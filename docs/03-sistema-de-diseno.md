# 03 · Sistema de diseño

Los principios que hacen que cualquier producto se vea "sumamente
profesional, minimalista, elegante y refinado" sin depender del producto en sí.
Si algo no está aquí, no se improvisa — se decide y se añade a este documento.

---

## Filosofía

**El producto es la estrella. El diseño es el marco, no el cuadro.**

Una tienda de un solo producto no compite en variedad, compite en confianza.
La confianza en dropshipping se construye con exactamente lo que la mayoría
de estas tiendas no tiene: aire, tipografía cuidada, y ausencia de trucos
baratos.

## Tokens (definidos en `01-header.liquid`)

### Color

```
--op-ink       texto principal, casi negro cálido
--op-paper     fondo base, blanco roto
--op-surface   blanco puro (tarjetas sobre paper)
--op-muted     texto secundario, gris cálido
--op-line      bordes, divisores — muy sutil
--op-accent    EL ÚNICO color de marca por tienda
--op-accent-ink  texto/icono sobre el acento
```

**Regla dura: un solo acento por tienda.** Nada de "acento primario +
secundario + terciario". Si hace falta llamar la atención sobre algo más,
se usa el mismo acento con más peso tipográfico o más espacio en blanco
alrededor — nunca un segundo color.

Elegir el acento según el producto, no por gusto:
- Producto de descanso/spa/bienestar → verdes apagados, terracotas
- Tech/gadget → azules fríos, grafito
- Belleza/cuidado personal → nudes, rosas apagados (nunca rosa chicle)

Comprobar contraste AA antes de fijarlo: `--op-accent` sobre `--op-paper` debe
ser legible como texto de apoyo; sobre `--op-accent-ink` debe pasar como botón.

### Tipografía

```
--op-font-display   Fraunces (serif de alto contraste) — titulares
--op-font-body      Inter (sans neutra) — todo lo demás
```

Por qué esta combinación y no otra: una serif con contraste alto en los
titulares es lo que separa visualmente "tienda de dropshipping" de "marca".
Es la misma lógica que usan DTC brands reales (Casper, Glossier-adjacent,
Our Place). Se puede sustituir Fraunces por otra serif editorial (Newsreader,
Canela si hay presupuesto) pero **nunca** por una sans en los titulares — ahí
es donde se pierde el "refinado".

Reglas de peso:
- Titulares: peso 300 (light), nunca bold. El contraste de la letra ya hace
  el trabajo visual.
- Cuerpo: 400, nunca por debajo del tamaño base para no forzar zoom en móvil.
- Mayúsculas + letter-spacing amplio: solo para microcopy (eyebrows, labels,
  botones). Nunca en titulares ni en párrafos.

### Espaciado

Escala de 4px (`--op-s-1` a `--op-s-24`). El espaciado entre secciones
(`--op-section`) es fluido y generoso a propósito — es lo primero que un ojo
entrenado nota como "esto no es una plantilla barata".

No comprimir el espaciado vertical para "que quepa más arriba del scroll".
El aire es la característica, no el desperdicio.

### Bordes y esquinas

`--op-radius: 2px`. Prácticamente recto. Nada de `border-radius: 20px` ni
sombras difuminadas de colores — eso lee como plantilla de Canva, no como
marca premium.

## Componentes — reglas de reutilización

| Componente | Dónde vive | Se reutiliza para |
|---|---|---|
| `.op-btn` | template | Cualquier CTA primario |
| `.op-card` | template | Dolor, paso, beneficio, testimonio |
| `.op-grid--3` / `--4` | template | Cualquier sección en rejilla |
| `.op-eyebrow` + `.op-h2` + `.op-lead` | template | Cabecera de cada sección |
| `.op-faq` (`<details>`) | template | Acordeones — sin JS, accesible por defecto |

Antes de escribir CSS nuevo para un producto: **¿ya existe un `.op-*` que
sirva?** El 90% de las veces sí. Un componente nuevo debe justificarse porque
el producto lo exige (ej. una tabla de tallas), no porque "se ve distinto".

## Lo que nunca se hace

Estas tácticas son comunes en tiendas de dropshiping de baja calidad y
activamente **dañan** el posicionamiento premium que se busca. Además, varias
son ilegales o violan los términos de Meta/TikTok Ads en US/UE:

- ❌ Countdown timers falsos que se reinician al recargar
- ❌ "Solo quedan 3 en stock" sin dato real detrás
- ❌ Pop-ups de "Fulano de Bogotá acaba de comprar" con nombres inventados
- ❌ Estrellas de reseñas sin reseñas reales debajo
- ❌ Sellos de pago ("100% seguro") sin que la tienda tenga certificado real
- ❌ Más de un color de acento
- ❌ Sombras de colores, gradientes decorativos, iconos genéricos de stock
- ❌ Fuentes del sistema en los titulares (Arial, Times) — mata el "refinado"
  en un segundo

## Checklist visual antes de publicar

- [ ] Un único color de acento, contraste verificado
- [ ] Cero elementos que parpadeen, cuenten o se muevan salvo la barra de
      anuncio (que es honesta) y el scroll
- [ ] Espaciado entre secciones consistente, nada apretado
- [ ] Tipografía: serif solo en titulares, nunca en botones ni microcopy
- [ ] Todas las imágenes con la misma relación de aspecto en cada rejilla
- [ ] Probado en móvil real (no solo el emulador del navegador)
- [ ] Probado con modo oscuro del sistema — el fondo `--op-paper` es claro por
      diseño; si el tema del cliente fuerza oscuro, verificar que el texto
      siga legible
