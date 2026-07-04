# CLAUDE.md — Proyecto: Sitio web Joyería Oro Negro

## 1. Contexto del proyecto

Sitio web institucional/comercial para **Joyería Oro Negro** (referencia: joyeriaoronegro.com), construido replicando el patrón estructural de un portal moderno tipo viabcp.com adaptado a un negocio de joyería. Se replica solo la arquitectura de información y patrones de UI — **nunca** marca, logos, colores exactos ni textos de BCP ni de terceros. No se copian textos ni fotografías del sitio original: todo el contenido se redacta nuevo y las imágenes son gradientes/SVG inline.

- **Rubro:** joyería (oro, plata, piedras preciosas, aros de matrimonio, joyería personalizada).
- **País/tono:** Perú. Textos en español, precios en S/.
- **Tecnología por defecto:** HTML autocontenido (un solo archivo `index.html`, CSS y JS embebidos, sin dependencias externas).

## 2. Identidad visual (theming)

Toda la página se tematiza vía variables CSS en `:root`. Paleta inspirada en el concepto "oro negro" (elegancia, lujo accesible):

```css
:root {
  --primario: #C9A227;        /* dorado principal */
  --primario-oscuro: #8C6D1F; /* dorado profundo (hovers, top bar) */
  --acento: #E5C558;          /* dorado claro para CTAs y highlights */
  --fondo-oscuro: #121212;    /* negro carbón (top bar, footer, hero) */
  --fondo-alterno: #F7F5EF;   /* marfil para secciones alternas */
  --texto: #1F2937;
  --radio: 14px;
}
```

- **Logo:** texto estilizado "ORO NEGRO" (serif elegante del stack de sistema). Nada de logos reales.
- **Tipografía:** stack de sistema (system-ui, -apple-system, 'Segoe UI', Roboto, sans-serif); titulares con Georgia, 'Times New Roman', serif.
- Contraste AA verificado sobre dorado y sobre negro.

## 3. Estructura canónica adaptada a joyería (orden obligatorio)

1. **Barra superior de utilidades** — fondo `--fondo-oscuro`; izquierda: segmentos "Mujer / Hombre / Matrimonio"; derecha: teléfono/WhatsApp + botón pill "Mi cuenta".
2. **Header principal (sticky)** — logo izquierda; mega-menú por categorías: Anillos, Aros de matrimonio, Cadenas y pulseras, Aretes, Personalizados, Ayuda; CTA "Cotiza tu joya" a la derecha; hamburguesa en móvil.
3. **Hero con carrusel** — 3 slides: (a) colección destacada, (b) aros de matrimonio con grabado gratis, (c) joyería personalizada / campaña de temporada. Fondos: gradientes negro→dorado con formas SVG. Dots + flechas + autoplay ~5s.
4. **Accesos rápidos** "¿Qué estás buscando hoy?" — grilla 4×.
5. **Productos destacados** — bloques alternados imagen/texto: Aros de matrimonio, Anillos de compromiso, Línea personalizada.
6. **Beneficios / promociones** — tarjetas.
7. **Contenido educativo** — 3 tarjetas.
8. **Canales de atención** — tarjetas: Tienda física, WhatsApp, Teléfono, Redes/Instagram.
9. **Footer institucional** — columnas: Productos / Ayuda / Nosotros / Legal; copyright, RUC placeholder, redes SVG, enlace a Libro de Reclamaciones.
10. **Botón flotante de WhatsApp** — 56–60px, verde WhatsApp, fixed bottom-right.

## 4. Reglas transversales (no negociables)

- Responsive con breakpoints ~768px y ~1100px; mega-menú colapsa a acordeón en móvil; verificar a 375 / 768 / 1280 px.
- Cero activos externos: sin `<img src="http...">`, sin hotlinks; solo SVG inline, gradientes y patrones CSS.
- Sin localStorage/sessionStorage (estado solo en variables JS).
- `lang="es"`, meta viewport, alt en imágenes, navegación por teclado, aria-label en carrusel y botón flotante, cierre de menús con Escape.
- Enlaces reales `href="#seccion"`, nunca `href="#"` sueltos.
- El botón flotante no debe tapar los dots del carrusel en móvil.

## 5. Checklist de calidad antes de entregar

- Las 10 secciones aparecen en el orden canónico.
- Carrusel: autoplay 5s, pausa al hover, dots y flechas funcionan.
- Header sticky con sombra al scroll; mega-menú abre/cierra bien en desktop y móvil.
- Correcto a 375px, 768px y 1280px.
- Ningún texto, logo, foto ni color copiado de joyeriaoronegro.com, BCP u otra marca real.
- Cambiar las variables `:root` re-tematiza toda la página.

## 6. Archivos del proyecto

| Archivo | Descripción |
|---|---|
| `CLAUDE.md` | Este documento: contexto, tema y reglas del proyecto. |
| `index.html` | Página completa autocontenida. |

## 7. Pendientes / información por confirmar con el usuario

- Colores exactos de la marca real (si desea replicar su identidad propia y tiene derechos sobre ella).
- RUC, dirección de tienda, horarios, número de WhatsApp y redes sociales reales.
- Catálogo real de categorías y promociones vigentes.
- Si prefiere versión React en lugar de HTML autocontenido.
