# Avlynor — corporate site

Single-page marketing site for **Avlynor**, the parent company of **Tether**.

## Preview locally

No build step. Just open the file:

```bash
open avlynor/index.html
```

Or serve it for nicer dev experience (matches how a real host will serve it):

```bash
cd avlynor && python3 -m http.server 8080
# then visit http://localhost:8080
```

## What's in it

- **Hero** — TETHER headline, "One check-in. One guardian. Zero friction." tagline,
  three big numbers (48h / 30× / 15s), animated SVG waveform that draws on load,
  CTAs to `biomarker.arhan.dev` and to the email capture.
- **Marquee ticker** — slowly scrolling band of technical credentials.
- **The 72-hour black hole** — problem statement + four stat cards.
- **The human voice is a biological sensor** — five-step Tether cycle.
- **The arithmetic is almost embarrassing** — ROI section, red cost bar over gold
  Tether-per-patient bar, with the SEK 2.4M savings explanation.
- **Three audience cards** — patients / nurses / hospitals.
- **Every competitor was built for the wrong continent** — 8-row comparison table.
- **Team Avlynor** — three founders with contact info.
- **Roadmap** — Q3 2026 → Q2 2027 (placeholder content; replace with real milestones).
- **Final CTA** — email capture targeted at Nordic hospitals + insurers. Currently
  opens a `mailto:` draft to Nitya. Wire to a real backend before launch.
- **Footer** — minimal, links to the technical surfaces (`biomarker.arhan.dev`,
  `tether-docs.pages.dev`).

## Interactions baked in

- Custom cursor: small gold dot + larger ring that expands over interactive elements.
- Compressing nav: shrinks to a thin strip once you scroll past 80 px.
- Reveal-on-scroll fade-up animations via `IntersectionObserver`.
- Marquee that pauses on hover.
- Animated waveform that draws on page load.
- Decorative gold/tan circles in the hero (matches deck slide 1).

## Brand tokens (CSS custom properties)

```
--bg-0:        #070D1B   deep navy
--gold:        #D4B572   primary (matches AVLYNOR wordmark)
--gold-bright: #E8CC85   highlight
--cream:       #F5EFE0   body text
--muted:       #8A95B0   secondary text
```

Typography: **Cinzel** for the AVLYNOR wordmark and small caps, **Cormorant Garamond**
for serif headlines, **Inter** for body. All via Google Fonts.

## What still needs doing before launch

- [ ] Email capture form: wire to a real backend (currently opens mailto). Options:
      Cloudflare Worker route, Formspree, ConvertKit, or a small Pages Function.
- [ ] Replace placeholder roadmap milestones with the real ones from Nitya.
- [ ] Photos for the team cards (currently text-only; pitch deck has the photos).
- [ ] Final copy review by Nitya — the deck-derived copy is intentionally close to
      the deck so the website matches what investors and hospital partners already saw.
- [ ] Decide on production domain (avlynor.com? avlynor.health? avlynor.se?) and
      DNS + TLS for Cloudflare Pages.
- [ ] Open Graph + Twitter Card meta tags for social sharing.

## Why no framework

This is a single-page marketing site. Adding React + bundler + framework would
make the file larger, slower to load, and harder for a non-engineer cofounder to
edit. A handwritten `index.html` + embedded CSS/JS is the right call here.
