# QA Report: Karem Lizbeth Parraga Espinoza

**Date:** 2026-02-07
**URL:** https://cofoundy.github.io/portfolio-karem-parraga/
**Status:** PASS

## Data Validation
- [x] Name matches source -- "Karem Lizbeth Parraga Espinoza" matches Sheet and config.ts exactly
- [x] Email matches source -- "karemparraga@gmail.com" matches Sheet exactly
- [x] Job title matches source -- "International Lawyer & Policy Analyst" from config.ts, consistent with CV/research
- [x] Companies listed exist in source -- UNODC (Consultant + Intern), EMMSA, Constructora MMAC S.A. all from CV
- [x] Education institutions exist in source -- Diplomatic Academy of Vienna, National University of San Marcos, University of Cologne all from CV
- [x] Dates are from source -- All date ranges match config.ts which was derived from CV
- [x] No hallucinated data detected
- [x] Publications section correctly labeled (not "Projects") -- nav and section heading both say "Publications"
- [x] Publication links are real and return HTTP 200 (bindinghook.com, polemics-magazine.com)

## Language Validation
- [x] html lang="en" correctly set
- [x] All section headers in English (About Me, Publications, Experience, Education)
- [x] All descriptions and bullet points in English
- [x] Spanish proper nouns acceptable: "Sociedad Hispanohablante", "Empresa Municipal de Mercados (EMMSA)", "Constructora MMAC S.A."
- [x] No stray Spanish UI text found

## Clean Deploy
- [x] No "Powered by" / "Made with" / "Built with" visible text
- [x] No "View source" / "View on GitHub" / "Fork this" template links
- [x] No "Lorem ipsum" / "Your name here" / "[placeholder]" text
- [x] No template watermarks visible to users (meta generator tag is in head only, not visible)
- [x] No broken links showing "#" or "javascript:void(0)" as visible text
- [x] No "undefined" or "null" visible in content
- [x] No Vercel badge, Astro logo, or other branding visible

## Technical
- [x] Page loads (HTTP 200)
- [x] CSS loads -- /_astro/index.z47Fn8Iq.css (HTTP 200)
- [x] Favicon loads -- /favicon.svg (HTTP 200)
- [x] Profile image -- not used in this template (minimal-mono text-only hero), profile.jpg exists at /profile.jpg (HTTP 200) but not referenced in HTML -- acceptable for this design
- [x] Publication link 1 loads -- bindinghook.com (HTTP 200)
- [x] Publication link 2 loads -- polemics-magazine.com (HTTP 200)
- [x] No critical console errors (only browser extension noise)
- [x] Grid pattern used instead of programming symbols (as required)

## Design Verification
- [x] Accent color #1e40af (navy blue) applied via CSS custom properties
- [x] Minimal-mono template correctly applied
- [x] All sections present: Hero, About Me, Publications, Experience, Education, Footer
- [x] Navigation links: About, Publications, Experience, Education
- [x] Social links: Email (mailto) and LinkedIn only (no Twitter/GitHub as expected)
- [x] Footer copyright: "2026 Karem Lizbeth Parraga Espinoza. All rights reserved."

## Minor Observations (Non-blocking)
- About section mentions 4 languages (Spanish, English, French, German) but client also speaks Italian and Portuguese. This appears to be intentional ("I work professionally in...") rather than hallucinated, but could be expanded if client requests.
- No profile photo displayed in hero section -- this is by template design (minimal-mono), not a bug.

## Issues Found
None

## Evidence
- qa-desktop.png
