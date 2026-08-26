# Brief de producto — <NOMBRE DEL PRODUCTO>

> Fuente de verdad del producto. Si un dato no está aquí, no existe.
> Claude genera los 3 bloques `.liquid` **únicamente** a partir de este archivo.
> Rellenar todo lo que se pueda; marcar `TBD` lo que falte.

---

## 1. Identidad

| Campo | Valor |
|---|---|
| Marca | |
| Subdominio | `<marca>.automatepty.com` |
| Slug interno | `<NN>-<slug>` |
| Handle en Shopify | |
| Fecha de lanzamiento | |
| Plazo de prueba | 21 días / $___ de ads |
| Criterio de muerte | Si CPA > $___ o conversión < ___% al cierre del plazo → archivar |

## 2. Producto

| Campo | Valor |
|---|---|
| Qué es (una frase) | |
| Link AutoDS | |
| ID AutoDS | |
| Coste proveedor | |
| Envío (coste / días) | |
| Precio de venta | |
| Precio tachado (compare-at) | |
| Margen bruto | |
| Variantes | |
| Peso / dimensiones | |
| Certificaciones (CE, FDA, etc.) | |

## 3. Cliente

- **Quién es:**
- **Qué le duele (el problema real, en sus palabras):**
- **Qué ha intentado antes y le falló:**
- **Qué objeción le frena a comprar:**
- **Dónde está:** (plataforma de ads, franja horaria, idioma)

## 4. Posicionamiento

- **Promesa central** (una frase, sin claims médicos):
- **Mecanismo** (por qué funciona — el "cómo" concreto):
- **Diferenciador vs. la alternativa barata:**
- **Prueba** (qué respalda la promesa: estudios, garantía, reseñas reales):

## 5. Copy — bloques clave

Rellenar en **ES y EN**. Van directo a la ZONA EDITABLE de los `.liquid`.

| Elemento | ES | EN |
|---|---|---|
| Barra de anuncio 1 | | |
| Barra de anuncio 2 | | |
| Barra de anuncio 3 | | |
| Eyebrow del hero | | |
| **H1** | | |
| Subtítulo del hero | | |
| CTA principal | | |
| Micro-confianza bajo CTA | | |

### Los 3 dolores (sección "problema")
| # | ES | EN |
|---|---|---|
| 1 | | |
| 2 | | |
| 3 | | |

### Los 3 pasos (sección "cómo funciona")
| # | Título ES / EN | Descripción ES / EN |
|---|---|---|
| 1 | | |
| 2 | | |
| 3 | | |

### Los 4 beneficios
| # | Título ES / EN | Línea de apoyo ES / EN |
|---|---|---|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |

### Especificaciones técnicas
| Spec | Valor |
|---|---|
| | |

### Comparativa
| Criterio | Nosotros | Alternativa |
|---|---|---|
| | | |

### Testimonios (reales o marcados como ilustrativos)
| Nombre | Texto ES | Texto EN | ¿Verificado? |
|---|---|---|---|
| | | | |

### FAQ (mínimo 6, atacando objeciones reales)
| Pregunta ES / EN | Respuesta ES / EN |
|---|---|
| | |

## 6. Recursos visuales

| Recurso | Estado | URL / ruta |
|---|---|---|
| Imagen hero (transparente o fondo limpio) | | |
| Galería (mín. 4) | | |
| Vídeo de uso | | |
| Logo / wordmark | | |

> Regla: si las fotos del proveedor son malas, el producto no se lanza hasta
> tener fotos decentes. La foto es el 80% de la conversión en un producto físico.

## 7. Diseño

| Token | Valor | Nota |
|---|---|---|
| `--op-accent` | `#______` | Un solo acento. Debe pasar contraste AA sobre papel. |
| `--op-accent-ink` | `#______` | Color del texto sobre el acento |
| Fuente titular | | serif de alto contraste |
| Fuente cuerpo | | sans neutra |

## 8. Legal y claims

- [ ] Copy revisado contra `docs/05-claims-y-legal.md`
- [ ] Disclaimer añadido al footer si aplica
- [ ] Políticas publicadas: envío, devoluciones, privacidad, términos
- [ ] Datos de contacto reales y visibles

## 9. Checklist de lanzamiento

- [ ] Producto importado desde AutoDS con precio y envío correctos
- [ ] Los 3 bloques pegados y revisados en móvil
- [ ] Subdominio conectado con SSL activo
- [ ] Pago de prueba completado de principio a fin
- [ ] Email de confirmación de pedido revisado
- [ ] Píxel / Conversions API instalado y disparando
- [ ] Velocidad móvil comprobada (PageSpeed > 60)
