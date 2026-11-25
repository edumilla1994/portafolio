---
name: portafolio-design
description: Sistema de diseño del portafolio de Eduardo Milla. Úsalo antes de editar index.html o cualquier página del portafolio para mantener la identidad visual, la tipografía local, la paleta, los componentes y el tono del contenido.
---

# Portafolio Design — Eduardo Milla

Sistema de diseño vivo del portafolio. La página es un solo `index.html` con CSS y JS embebidos; no hay framework ni build. Antes de cambiar el diseño, leer esta skill y respetar los tokens existentes.

## Cuándo usarla

- Editar `index.html`, `fonts/fuentes.css`, `logos/` o `capturas/`.
- Agregar secciones, tarjetas de proyectos, métricas o experiencia.
- Revisar que un cambio no rompa la identidad visual ni el responsive.
- Actualizar el CV público o los enlaces de descarga.

## Fuentes de verdad

| Dato | Archivo |
|---|---|
| Contenido biográfico y experiencia | `cv/mi-perfil.md` |
| CV público de 2 páginas | `cv/build_cv_ats.py` → `CV-Eduardo-Milla-2026.pdf` |
| CV completo con anexos | `cv/build_cv_completo.py` → `cv/CV-Eduardo-Milla-2026-COMPLETO.pdf` |
| Diseño y copy de la web | `index.html` |
| Tipografías locales | `fonts/fuentes.css` |
| Logos del stack | `logos/*.svg` |

No inventar fechas, cargos, métricas ni clientes. Si un dato no está en `cv/mi-perfil.md`, preguntar antes de publicarlo.

## Paleta

| Token | Valor | Uso |
|---|---|---|
| `--bg` | `#0b0b0d` | Fondo base |
| `--bg-2` | `#111114` | Fondo secundario |
| `--panel` | `#151519` | Tarjetas y paneles |
| `--panel-2` | `#191920` | Hover de paneles |
| `--line` | `rgba(255,255,255,.10)` | Bordes suaves |
| `--line-2` | `rgba(255,255,255,.18)` | Bordes activos |
| `--txt` | `#f3f3ef` | Texto principal |
| `--muted` | `#9b9ba4` | Texto secundario |
| `--dim` | `#6d6d76` | Metadatos y labels |
| `--accent` | `#c7f464` | Acento lima (acción, foco, métricas) |
| `--accent-ink` | `#101204` | Texto sobre lima |

El lima es el único acento fuerte. No agregar una segunda familia de acentos (azul, violeta, coral). Los estados hover usan lima o `--line-2`.

## Tipografía

Todas las fuentes se sirven localmente desde `fonts/` con `font-display: swap`.

| Rol | Familia | Detalle |
|---|---|---|
| Display / H1 | **Anton** 400 | Mayúsculas, `letter-spacing:-.015em`, `line-height:.9` |
| H2 y títulos de tarjeta | **Bricolage Grotesque** 600–800 | Mayúsculas en H2, `letter-spacing:-.03em` |
| Cuerpo | **Manrope** 400–700 | `16px`, `line-height:1.6` |
| Marca / nav pequeña | **Barlow Condensed** 600 | Mayúsculas, tracking amplio |
| Acento editorial | **Instrument Serif** 400 italic | Solo para énfasis en frases |
| Labels / datos | **JetBrains Mono** 400–600 | `.6rem`–`.68rem`, mayúsculas, tracking `.12em`–`.18em` |

No introducir una fuente nueva sin una razón de contenido. Si hace falta otra familia, justificarla y agregarla a `fonts/fuentes.css` con sus woff2.

## Layout

- Ancho máximo: `1180px`; padding lateral: `32px`; en mobile, `26px` en CTA.
- Hero: grid `1.32fr .68fr`, alineado al final; el retrato va a la derecha y pasa arriba en mobile.
- Secciones: `padding:86px 0 4px`, `scroll-margin-top:96px`.
- Proyectos: grid de 3 columnas; 1 columna bajo `900px`.
- Capacidades: 2 columnas con separadores de 1px; 1 columna bajo `760px`.
- Stack: `1.4fr .6fr`; 1 columna bajo `900px`.
- Proceso: 5 columnas; 2 bajo `900px`; 1 bajo `520px`.
- Radios: `8px`–`16px`. No usar radios distintos para elementos del mismo nivel.

## Componentes

- **Nav sticky** con blur, borde inferior y link activo subrayado en lima.
- **Barra de progreso** de 2px en lima, arriba de todo.
- **Marquesina** lima inclinada `-1.1deg`; se pausa al hover; respeta `prefers-reduced-motion`.
- **Stats**: 4 columnas, iconos de línea, número grande en Anton, label mono.
- **Tarjetas de proyecto**: “browser” con chrome de 3 puntos, screenshot arriba, título + categoría, descripción, chips de stack y flecha circular que rota al hover.
- **Capacidades**: icono de línea, título, descripción y número grande tenue en la esquina.
- **Experiencia**: fila `when` + contenido, borde inferior de 1px, bullets con guion corto.
- **Stack**: grupos con logos SVG monocromos (`opacity:.62`, hover a 1), título mono lima y lista.
- **Formación**: panel lateral con items y borde inferior.
- **Proceso**: 5 pasos numerados en mono.
- **CTA**: panel con gradiente oscuro, H2 con acento serif en lima y links tipo fila.

## Motion

- Entrada del H1: `rise` 1s, escalonada por línea.
- Reveal de secciones: 0.7s, `translateY(22px)`, delay escalonado de 70ms (máx. 350ms).
- Contadores: incremento por `requestAnimationFrame`; fallback a valor final a los 3s.
- Marquesina: 36s lineal infinita; pausa al hover.
- Respetar siempre `prefers-reduced-motion: reduce` (desactivar animaciones y transiciones).
- No agregar animaciones decorativas nuevas sin un propósito de lectura.

## Copy

- Español neutro/peruano, directo y cálido.
- Primera persona cuando se describe trabajo propio; tercera persona en metadatos.
- Beneficio concreto antes que adjetivo: “38/38 tests”, “240+ emisiones”, “13 años”, “6 sistemas en producción”.
- Evitar “apasionado”, “sinergia”, “revolucionario” y métricas sin respaldo.
- Los enlaces de descarga del CV deben apuntar a `CV-Eduardo-Milla-2026.pdf` (2 páginas). No publicar el COMPLETO con DNI.
- Mantener el tono híbrido: software + automatización + campo eléctrico, sin pedir disculpas por el perfil técnico.

## Reglas de edición

1. Leer `index.html` completo antes de un cambio grande; el CSS está embebido.
2. Reutilizar clases existentes (`.card`, `.cap`, `.job`, `.group`, `.btn`) antes de crear nuevas.
3. No agregar dependencias externas ni llamadas a Google Fonts; las fuentes ya están locales.
4. No romper la semántica: un `h1`, secciones con `id`, `nav` con anchors, `alt` en imágenes.
5. Verificar responsive a 1440px, 1024px, 768px y 390px.
6. Verificar foco visible de teclado y contraste de texto sobre fondo.
7. Si se agrega un logo, usar SVG monocromo blanco (`fill="#FFFFFF"`) como los de `logos/`.

## Verificación

```bash
python -m http.server 8000
```

Abrir `http://localhost:8000` y revisar:

- Hero y retrato en desktop/mobile.
- Marquesina sin saltos.
- Grid de proyectos (8 tarjetas; 3 columnas en desktop).
- Sección de capacidades (6 tarjetas; 2 columnas).
- Experiencia con Megamarcas y el periodo eléctrico 2013–2026.
- Formación 2018 y certificado de trabajo.
- Enlaces de CV, WhatsApp, GitHub y LinkedIn.
- `prefers-reduced-motion` y navegación por teclado.

## Skills globales relacionadas

- `frontend-design` — dirección visual y criterio editorial.
- `typeui` — jerarquía, tipografía y accesibilidad.
- `theme-factory` — paletas y temas para artefactos.
- `brand-guidelines` — consistencia de marca.
- `canvas-design` — piezas gráficas y PDFs.
