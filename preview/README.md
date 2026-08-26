# Preview local

`index.html` es un espejo estático (HTML/CSS puro, sin Liquid) del sistema de
diseño y la estructura de `plantillas/02-template.liquid`. Sirve para ver y
ajustar visualmente los tokens, la tipografía y el ritmo de las secciones
**sin necesidad de tener Shopify abierto**.

## Uso

Abrir `index.html` directamente en el navegador (doble clic, o arrastrar a
una pestaña). No requiere servidor.

## Qué NO hace

- No ejecuta Liquid — el copy y el color de acento están hardcodeados con
  valores de ejemplo, se editan a mano en `index.html` si se quiere probar
  algo puntual.
- No tiene el `<form action="/cart/add">` funcional — el botón no hace nada.
- No refleja el header/carrito nativo real de tu tema de Shopify.

Es una herramienta de **diseño rápido**, no de QA final. El QA final siempre
se hace en el editor de temas real (`docs/02-como-pegar-bloques.md`, Fase 4
del flujo).

## Flujo recomendado

1. Ajustar aquí el color de acento, la tipografía o el espaciado hasta que
   se vea bien
2. Trasladar esos mismos valores a la ZONA EDITABLE de
   `productos/<slug>/01-header.liquid` y `02-template.liquid`
3. Pegar en Shopify y verificar en real
