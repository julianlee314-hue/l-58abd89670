# Acre & Water: brand notes

The LIFE editorial family: ink, ivory, brass and sea-slate. Grown-up and quiet. Never Mathera. Matches the PDF, which is set in EB Garamond and Lato.

## Palette
| Token | Hex | Use | Contrast |
|---|---|---|---|
| Ivory (paper) | `#F4EFE4` | page background | — |
| Ink (pine-black) | `#1C2B26` | body text, headings, dark bands | 12.9:1 on ivory (AAA) |
| Sea-slate | `#5E7B86` | rules, map lines, large labels | 3.9:1 on ivory (large text and UI only) |
| Sea-slate deep | `#46616B` | small slate text and links on ivory | 5.8:1 (AA) |
| Brass | `#A8813E` | ampersand, hairlines, icons | 3.1:1 on ivory (decor and large text only) |
| Brass deep | `#7A5C26` | small brass text on ivory | 5.4:1 (AA) |
| Brass light | `#C9A55F` | brass on ink | 6.3:1 on ink (AA) |
| Slate light | `#9DB4BB` | slate on ink | 6.8:1 on ink (AA) |

Ivory on ink is 12.9:1. Keep small body text in ink and use brass and slate as accents.

## Type
- **Display and body serif:** EB Garamond (Georg Duffner; SIL OFL). Get it from https://fonts.google.com/specimen/EB+Garamond or https://github.com/octaviopardo/EBGaramond12 and self-host the woff2 files. Use weights 400, 500 and 600 plus 400 italic. Set caps headings at 500 with `letter-spacing: .06em`. The italic `&` is the signature: set it in brass.
- **Labels, kickers and meta:** Lato (Łukasz Dziedzic; SIL OFL) from https://fonts.google.com/specimen/Lato. Use 400 and 700, uppercase, `letter-spacing: .18em`, 11–12 px.
- System fallbacks: `Georgia, 'Times New Roman', serif` and `system-ui, -apple-system, 'Segoe UI', sans-serif`.

## Wordmark and mark
- The `wordmark*.svg` files are converted to outlines, so they need no fonts. The caps are EB Garamond 500, tracked +60 units, with a manual T/E optical kern. The ampersand is EB Garamond italic at 82%, in brass.
- The mark: three ink field furrows that narrow toward the horizon, meeting two brass wave lines.
- Use `wordmark-on-ivory` on light backgrounds and `wordmark-on-ink` on dark ones. Keep clear space of at least the height of one cap "A" on every side. The smallest size is 160 px wide. Below that, use the mark alone.
- Favicon: `favicon-32.png` and `apple-touch-icon-180.png` (`mark.svg` is the rounded version for an SVG favicon).

## Hero
- `hero.jpg` is the 1280×720 original. `hero-1600.jpg` is the 1600 px web size; it is upscaled, so serve 1280 where you can and use 1600 only for full-bleed hero layouts. Use `object-fit: cover`, focus on the centre, and keep 16:9 or crop wider, not taller.
- Caption it every time, small and in italics under the image: *"Illustration, not a property."* A longer version: *"Original conceptual artwork, not a photograph of a listed property."*
- Don't put text over busy parts of the image. If you need a title over it, use an ivory panel, as the PDF cover does.

## CSS
```css
@font-face{font-family:"EB Garamond";src:url(/fonts/EBGaramond-VariableFont_wght.woff2) format("woff2");font-weight:400 800;font-display:swap}
@font-face{font-family:"EB Garamond";src:url(/fonts/EBGaramond-Italic-VariableFont_wght.woff2) format("woff2");font-style:italic;font-weight:400 800;font-display:swap}
:root{
  --aw-ivory:#F4EFE4; --aw-ink:#1C2B26;
  --aw-slate:#5E7B86; --aw-slate-deep:#46616B; --aw-slate-light:#9DB4BB;
  --aw-brass:#A8813E; --aw-brass-deep:#7A5C26; --aw-brass-light:#C9A55F;
  --aw-rule:color-mix(in srgb,var(--aw-ink) 18%,transparent);
  --aw-serif:"EB Garamond",Georgia,"Times New Roman",serif;
  --aw-sans:"Lato",system-ui,-apple-system,"Segoe UI",sans-serif;
  --aw-measure:66ch;
}
body{background:var(--aw-ivory);color:var(--aw-ink);font:400 1.125rem/1.6 var(--aw-serif)}
h1,h2{font-weight:500;letter-spacing:.06em;text-transform:uppercase}
.kicker{font:700 .72rem/1.2 var(--aw-sans);letter-spacing:.18em;text-transform:uppercase;color:var(--aw-slate-deep)}
.amp{font-style:italic;color:var(--aw-brass)}
a{color:var(--aw-slate-deep)} a:hover{color:var(--aw-brass-deep)}
figcaption{font-style:italic;font-size:.85rem;color:var(--aw-slate-deep)}
```
