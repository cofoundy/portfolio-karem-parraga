# Propuesta de Diseno: Karem Parraga — PLUS S/.80

## Analisis

- **Profesion:** International Lawyer & Policy Analyst
- **Industria:** International Law, Cybersecurity, UN/Multilateral
- **Audiencia objetivo:** International organizations (UN, think tanks), academic journals, recruiters
- **Vibe deseado:** Professional, international, sophisticated
- **Idioma:** English (career is international, Vienna-based education)
- **Nota:** Ya tiene buen contenido en config.ts. Plus = mejoras visuales sobre base.

## Que Significa "Plus" (S/.80)

Mejoras sobre la base Arranca:

1. **Better typography** (serif + sans, replace IBM Plex Mono)
2. **Profile photo in hero** (ya tiene profile.jpg)
3. **Basic scroll reveal animations** (IntersectionObserver)
4. **Improved section headers** (accent-colored decorations)
5. **Better color integration** (navy accents throughout)
6. **Improved card designs** (shadows, borders, better spacing)

---

## Paleta Final — "Diplomatic Navy"

| Token | Color | Uso |
|-------|-------|-----|
| **Background** | `#ffffff` | Blanco puro. Limpio, profesional. |
| **Text Primary** | `#1a1a2e` | Near-black con tinte navy. |
| **Text Secondary** | `#64748b` | Slate-500. Metadata, fechas. |
| **Accent** | `#1e40af` | Blue-800. Su color actual. Diplomatico, serio. |
| **Accent Light** | `#dbeafe` | Blue-100. Badge backgrounds. |
| **Surface** | `#f8fafc` | Slate-50. Secciones alternas. |
| **Surface Border** | `#e2e8f0` | Slate-200. Bordes de cards. |

---

## Tipografia — Replace IBM Plex Mono

| Rol | Font | Justificacion |
|-----|------|---------------|
| **Headings** | **Libre Baskerville** | Serif clasico, diplomatico, academico. Perfect for international law. |
| **Body** | **Source Sans 3** | Sans-serif profesional, legible. |

**Nota:** IBM Plex Mono era incorrecto para una abogada/diplomatica. Monospace = developer, no lawyer. Serif headings + sans body = autoridad academica.

---

## Mejoras por Seccion

### 1. HERO — Agregar foto + mejorar layout
```
ANTES:
  "Hello! 👋" + nombre + titulo (sin foto)

AHORA:
  ┌─────────────────────────────────────────┐
  │                                          │
  │     ┌────────┐                           │
  │     │  FOTO  │   KAREM LIZBETH           │
  │     │profile │   PARRAGA ESPINOZA        │
  │     │  .jpg  │                           │
  │     └────────┘   International Lawyer     │
  │                  & Policy Analyst         │
  │                                          │
  │     Diplomatic Academy of Vienna         │
  │     UNODC | Cybercrime & Int'l Law       │
  │                                          │
  │     [📧 Email] [💼 LinkedIn]              │
  │                                          │
  └─────────────────────────────────────────┘
```
- Foto circular con borde sutil navy
- Fade-in animation: foto + text stagger
- Remove "Hello! 👋" (too casual for diplomat)
- Add institutional affiliations below title

### 2. ABOUT — Better visual structure
```
ANTES:
  Texto + skill badges grises

AHORA:
  Texto con Libre Baskerville para quote feel +
  Skill badges con navy background + white text +
  "4 languages" highlight pill +
  Reveal animation on scroll
```

### 3. PUBLICATIONS (was "Projects")
```
ANTES:
  Numbered cards (01-03) con "Publications" label

AHORA:
  ┌────────────────────────────────────────┐
  │  PUBLICATIONS                           │
  │  ── accent line ──                      │
  │                                         │
  │  ┌──────────────────────────────────┐   │
  │  │ 📄 The UN Cybercrime Convention   │   │
  │  │    Binding Hook, 2025             │   │
  │  │    [Read Article →]               │   │
  │  └──────────────────────────────────┘   │
  │  ┌──────────────────────────────────┐   │
  │  │ 📄 Justice by Algorithm           │   │
  │  │    Polemics Magazine, 2024        │   │
  │  │    [Read Article →]               │   │
  │  └──────────────────────────────────┘   │
  │  ┌──────────────────────────────────┐   │
  │  │ 📄 Governing Cybercrime           │   │
  │  │    Master's Thesis, DA Vienna     │   │
  │  └──────────────────────────────────┘   │
  │                                         │
  └────────────────────────────────────────┘
  ```
- Better card design with left accent border
- External link icon for articles with URLs
- Hover: translateY(-2px) + shadow
- Stagger reveal animation

### 4. EXPERIENCE — Timeline mejorado
```
ANTES:
  Timeline dots + white cards

AHORA:
  Timeline con accent-colored line +
  Company name en navy bold +
  Date pills con accent background +
  Better bullet formatting +
  Reveal animation (stagger)
```

### 5. EDUCATION — Cards mejoradas
```
ANTES:
  White cards con accent-colored school names

AHORA:
  Cards con left navy border +
  School name en Libre Baskerville serif +
  Achievement badges con border +
  "Study Abroad" highlight pill +
  Stagger reveal on scroll
```

### 6. HEADER — Improved nav
```
ANTES:
  White/80 blur on scroll

AHORA:
  White/90 with stronger blur +
  Active section indicator (navy underline) +
  Smooth scroll to sections +
  Nav items: About/Publications/Experience/Education
```

### 7. FOOTER — Cleaner
```
ANTES:
  Gray-50 bg, wave SVG pattern

AHORA:
  Cleaner design without wave +
  Navy bg with white text (OR keep light) +
  Social links centered +
  "Built with ♥ by Cofoundy" credit
```

---

## Motion Design Plan

### Scroll Reveals
```css
.reveal {
  opacity: 0;
  transform: translateY(25px);
  transition: all 0.5s ease-out;
}
.reveal.active {
  opacity: 1;
  transform: translateY(0);
}
```
- Threshold: 0.15
- Stagger: 0.1s between siblings
- Subtle (not dramatic — matches diplomatic tone)

### Hero Entrance
- Photo: scale(0.95→1) + opacity, 0.5s
- Name: fade-in, delayed 0.2s
- Title: fade-in, delayed 0.3s
- Social: fade-up, delayed 0.5s

### Hover Effects
- Publication cards: translateY(-2px) + shadow-md, 0.2s
- Experience cards: border-left-color(transparent→navy), 0.2s
- Skill badges: scale(1.05) + bg-navy/10, 0.15s
- Nav items: underline slide

### Mobile
- Photo: centered, slightly smaller
- Cards: full-width stack
- prefers-reduced-motion: opacity only
- Touch targets: 44px min

---

## Diferencias vs. Current

| Aspecto | Antes (Arranca) | Ahora (Plus) |
|---------|-----------------|--------------|
| Font | IBM Plex Mono | Libre Baskerville + Source Sans 3 |
| Hero | No photo, "Hello! 👋" | Photo + professional intro |
| Scroll | Static | IntersectionObserver reveals |
| Cards | Flat white | Shadows + borders + hover effects |
| Section headers | Basic | Accent underline decoration |
| Skill badges | Gray pills | Navy background pills |
| Timeline | Basic dots | Accent-colored line + better pills |
| Footer | Wave SVG | Cleaner, professional |
| Color integration | Minimal accent use | Navy throughout (borders, pills, lines) |

---

## Lo que NO cambia
- Contenido en ingles (already excellent)
- Config.ts data (publications, experience, education)
- Overall section order
- Color: navy #1e40af (diplomatic, appropriate)
- Social: email + LinkedIn only

---

*Plus = Better typography + photo + scroll animations + polished cards. Same great content, elevated visual.*
