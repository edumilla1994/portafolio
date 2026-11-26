# Portafolio — Eduardo Milla

Sitio personal de **Eduardo Itai Milla Rosillo**, Full-Stack Developer, automatización con IA y técnico electricista principal (Tumbes, Perú).

- HTML, CSS y JavaScript puros: sin frameworks ni build.
- Tipografías y capturas servidas localmente (no depende de Google Fonts ni de internet).
- Secciones: hero, métricas, proyectos, capacidades, experiencia, stack, proceso y contacto.
- Contenido alineado con el CV 2026: 13 años de campo eléctrico, 10+ entre operaciones y software, Megamarcas y TermoInforme/ANALISISQ.

## Estructura

```
index.html                  Página completa (CSS y JS embebidos)
fonts/                      Fuentes woff2 + fuentes.css
capturas/                   Capturas de los proyectos (jpg 1400px)
logos/                      Logos SVG del stack
fotoia.jpg                  Retrato optimizado
logo-primitivopie.png       Favicon
og.jpg                      Imagen para compartir (1200x630)
CV-Eduardo-Milla-2026.pdf   CV ATS de 2 páginas (descargable)
cv/                         Fuentes del CV: perfil maestro + scripts DOCX/PDF
.opencode/skills/           Skill de diseño del portafolio
```

## Ver en local

Abrir `index.html` con doble clic, o servirlo:

```bash
python -m http.server 8000
```

## CV

- `CV-Eduardo-Milla-2026.pdf` es la versión pública de 2 páginas, generada desde `cv/build_cv_ats.py`.
- `cv/CV-Eduardo-Milla-2026-COMPLETO.pdf` es el expediente de 16 páginas con DNI, CUL, diploma, certificados de trabajo, cursos y licencia. **No se publica en la web.**
- La fuente de verdad es `cv/mi-perfil.md`; si cambia un dato, actualizarlo ahí y regenerar:

```bash
cd cv
python build_cv_ats.py
```

## Diseño

La identidad visual está documentada en `.opencode/skills/portafolio-design/SKILL.md`: paleta, tipografías locales, componentes y reglas de motion. Antes de rediseñar, leer esa skill.

Skills globales relacionadas: `frontend-design`, `typeui`, `theme-factory`, `brand-guidelines` y `canvas-design`.

## Deploy

Sitio estático: se publica en Vercel sin configuración extra (framework "Other", sin build).

Enlaces:

- Portafolio: https://edumilla.vercel.app
- GitHub: https://github.com/edumilla1994
- LinkedIn: https://linkedin.com/in/edumilla1994
- PrimitivoPie: https://primitivopie.shop
