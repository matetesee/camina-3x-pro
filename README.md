# Método Camina 3X™ — Quiz Funnel

Quiz funnel de venta para **Método Camina 3X™**, construido a partir del
ángulo de mercado de un funnel competidor (`inlead.digital/appmetodo217` —
"Método 21/7™", un quiz de metabolismo/plan de alimentación), sobre el motor
config-driven de la skill `quiz-funnel-builder`.

## Qué se reusó del competidor (el ángulo que ya funciona)
- **Promesa central:** "tu metabolismo cambió, calculá tu plan personalizado
  para esta etapa" — adaptada acá al **método de caminata por intervalos**
  (3 min rápido / 3 min normal) en vez de un plan de alimentación.
- **Estructura del quiz:** edad → interstitial de prueba social → talle
  actual → objetivo → cajas de empatía (vergüenza/pareja/social) → qué te
  frena → motivación → nivel de actividad diaria → hábitos → peso/altura →
  sueño → agua → evento próximo → compromiso → nombre → resultado con
  gráfico de proyección → loader → oferta.
- **Gatillos:** urgencia (timer + "oferta solo por hoy"), prueba social
  (+76.000 personas), aversión a la pérdida (cajas de empatía), identidad.

## Qué se mejoró (con el motor de la skill)
- Testimonios con nombre + edad + resultado concreto (el competidor tenía
  solo 2 testimonios genéricos).
- FAQ, garantía de 30 días, badges de pago, gráfico de proyección animado
  y medidor de "potencial" — más completo que la oferta original (que solo
  tenía antes/después + timer + 1 plan).
- 3 planes (7 / 21 / 90 días) con decoy de "más elegido", en vez de 1 solo
  plan.

## Qué es propio de Camina 3X (no se copió nada del sitio original)
- Nombre, marca, paleta de colores, copy completo, precios, testimonios,
  FAQ y estructura de planes son propios.
- No se usaron fotos, nombres, coach ni credenciales del sitio competidor.
- No hay imágenes reales generadas para este funnel todavía (no había un
  generador de imágenes conectado en esta sesión) — las tarjetas se
  muestran como tarjetas de texto limpias (el motor las soporta así
  nativamente). Se pueden agregar fotos después reemplazando `img:""` por
  URLs en el `CONFIG` de `index.html`.

## Pendientes antes de lanzar campañas
- [ ] **Checkout real:** hoy el botón de compra es un placeholder (`#`).
      Reemplazar `STORE` y los `variantId` de cada plan en `CONFIG.TIERS`
      (`index.html`) cuando exista la tienda/checkout.
- [ ] **Meta Pixel:** agregar el snippet del Pixel en el `<head>` de
      `index.html` y las variables `META_PIXEL_ID` / `META_ACCESS_TOKEN` en
      Railway → Variables (el endpoint server-side `/api/capi-event` ya
      está listo en `server.js`).
- [ ] **Precios:** el plan "MÉTODO 21 DÍAS" usa el precio dado ($9,90 antes
      $55). Los otros dos planes (7 y 90 días) son decoys estimados —
      ajustalos si tenés precios reales.

## Correr en local
```bash
npm start
```
Sirve en `http://localhost:3000`.

## Deploy
Desplegado en Railway, conectado al repo de GitHub
`matetesee/camina-3x-pro` para deploys automáticos en cada push a `main`.
