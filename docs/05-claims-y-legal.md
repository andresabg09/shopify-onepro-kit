# 05 · Claims y legal

**No opcional.** Un claim de más puede: (a) tumbar la cuenta de Meta/TikTok
Ads sin aviso, (b) generar reembolsos masivos por incumplimiento de
expectativa, (c) exponer legalmente al negocio. Esta hoja se revisa en cada
brief nuevo, antes de escribir una sola línea de copy.

> Esto es una guía operativa, no asesoría legal. Para un producto que roce
> literalmente dispositivos médicos (cualquier cosa que mida, diagnostique o
> se inserte), consultar con un abogado antes de lanzar.

---

## La regla madre

**Se puede describir lo que el producto *hace* físicamente. No se puede
prometer lo que el producto *cura, trata, previene o diagnostica*.**

| ❌ No decir | ✅ Decir en su lugar |
|---|---|
| "Elimina las ojeras" | "Reduce visualmente la apariencia de las ojeras" |
| "Cura el insomnio" | "Diseñado para ayudarte a relajarte antes de dormir" |
| "Trata la inflamación" | "Ofrece una sensación de frescor y masaje" |
| "Repara la piel" | "Ayuda a que la piel luzca más descansada" |
| "Elimina el dolor" | "Proporciona alivio temporal de la tensión" |
| "Clínicamente probado" (sin estudio propio citable) | "Inspirado en técnicas de [mecanismo real, ej. terapia de luz/frío]" |

Vocabulario seguro y reutilizable: *ayuda a, favorece, diseñado para,
contribuye a, ofrece una sensación de, ideal para acompañar tu rutina de*.

Vocabulario prohibido salvo con respaldo clínico real y verificable: *cura,
elimina, trata, previene, diagnostica, clínicamente probado, garantizado
médicamente, resultados en X días* (promesa de tiempo = expectativa
contractual).

## Categorías especialmente sensibles para este tipo de producto

- **Ojos**: cualquier producto que toque la zona ocular (máscaras, gafas de
  luz) — nunca prometer mejora de visión, tratamiento de afecciones oculares,
  ni usar imágenes que sugieran uso médico (bata blanca, cruz roja, etc.)
- **Piel**: nunca prometer eliminar arrugas, manchas o cicatrices de forma
  permanente
- **Sueño**: nunca prometer curar insomnio o trastornos del sueño
  diagnosticados
- **Dispositivos con luz/vibración/calor**: describir el mecanismo físico
  (ej. "vibración suave", "luz LED de baja intensidad") sin prometer el
  resultado biológico que esa tecnología produciría en un contexto clínico

## Testimonios y prueba social

Hay dos caminos distintos — no confundirlos:

| Camino | Qué es | ¿Válido? |
|---|---|---|
| App de importación de reseñas (AutoDS, Loox, etc.) | Reseñas reales de compradores del listado de origen, con foto/fecha, instalada como su propia app en Shopify | ✅ Práctica estándar de la industria |
| Testimonios escritos a mano en el bloque `02-template.liquid` (`REV_ES`/`REV_EN`) | Texto redactado por nosotros, sin comprador real detrás | ❌ Nunca — es prueba social inventada |

- El bloque de testimonios de este repo (`SHOW_REVIEWS`) es **texto escrito a
  mano** — se mantiene en `false` hasta tener citas reales de clientas de
  *esta* tienda.
- Una app de reseñas importadas es una sección aparte del tema, no pasa por
  nuestro Liquid — puede convivir sin problema con los 3 bloques.
- No usar fotos de stock presentadas como "clientes reales".
- No usar batas blancas, logos de hospitales, o cualquier elemento que
  sugiera aval médico sin que exista.
- Contadores de ventas o "X personas comprando ahora mismo" — solo si el dato
  es real y verificable. Si no, no se usa.

## Disclaimer obligatorio

Ya incluido por defecto en `03-footer.liquid` (variable `DISCLAIMER`). No
eliminar ni vaciar esa variable en ningún producto de bienestar/belleza:

> "Este producto es un dispositivo de bienestar y cuidado personal. No es un
> producto sanitario y no está destinado a diagnosticar, tratar, curar ni
> prevenir ninguna enfermedad..."

Ajustar la redacción al producto concreto si hace falta, pero mantener las
tres piezas: (1) qué es, (2) qué NO es, (3) recomendación de consultar a un
profesional si aplica.

## Políticas de las plataformas de ads (resumen práctico)

Meta y TikTok banean con especial dureza en la categoría salud/belleza:

- No se permite implicar resultados "antes/después" sin evidencia verificable
- No se permite crear inseguridad corporal como gancho ("¿Te avergüenzan tus
  ojeras?" cruza la línea; "Luce más descansado" no)
- No se permite lenguaje de urgencia médica falsa
- Las imágenes de "antes/después" están altamente restringidas — evitarlas
  salvo que sean 100% propias y honestas

## Checklist legal antes de publicar

- [ ] Ningún verbo de la lista prohibida en H1, subtítulo, beneficios o FAQ
- [ ] Disclaimer presente en el footer y ajustado al producto
- [ ] Testimonios reales o sección oculta
- [ ] Políticas de envío/devolución/privacidad/términos publicadas
- [ ] Ninguna imagen sugiere aval médico sin que exista
- [ ] El ángulo de marketing no se apoya en inseguridad corporal como gancho
      principal
- [ ] Revisado: si esta tienda la viera un abogado de la FTC, ¿qué frase
      señalaría primero? Corregirla antes de lanzar, no después del baneo.
