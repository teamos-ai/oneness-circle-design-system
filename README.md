# The Oneness Circle — Design System

> Volume I · Edition II · MMXXVI
>
> An apothecary of tokens. Five anchors. Three pillars. One ivory canvas.

A self-contained editorial design system for **The Oneness Circle** — a brand at the intersection of botanical ritual, cellular science, and sovereign leadership. Edition II reframes the system in the editorial-apothecary register: a single centered column, numbered chapters, hairline rules, and plate-figure-caption rhythm. Every token, colour, font, and principle is preserved verbatim from the source brief.

## Live site

After deploying to Vercel, the production URL appears here.

## What's inside

Twenty chapters, top to bottom:

| # | Section | Notes |
|---|---|---|
| I | Principles | Five rules of geometry & restraint |
| II–VII | Foundations | Colour · Typography · Spacing · Radius · Elevation · Motion |
| VIII–IX | System | Taxonomy & the three pillars · Token reference |
| X–XIV | Components | Buttons · Chips · **Iconography** · Cards · Forms · Swatch |
| XV–XVII | Patterns | Bento · In application · Do & Don't |
| XVIII | React UX profiles | Live preview + copyable JSX |
| XIX | Image gallery | Tagged & filterable |
| XX | More in application | Landing · Blog · Social posts |

## Design DNA — locked

These choices are intentional and must not drift:

- **Sharp geometry** — `border-radius: 0` is the default; `4px` is the only permitted softening.
- **Five anchors** — Ivory, Sacred Gold, Sage Dark, Dark Blue, Violet Noir. Each carries a full 9-step scale.
- **Two typefaces** — Cormorant Garamond (soul) + Jost (mind). No third family.
- **Coral appears exactly once** per surface, as the action accent.
- **No gradient text**, no side-stripe borders on callouts, no rounded chrome.
- **One icon weight** — `regular`, sitewide. House glyphs (`#icon-*`) outrank the pack (`#i-*`).

## Tech

Single static `index.html` with inline CSS and JS. No build step. No dependencies beyond Google Fonts (Cormorant Garamond + Jost) loaded at runtime.

### Local preview

```bash
# any static server works
npx serve .
# or
python -m http.server 8000
```

Open `http://localhost:8000`.

### Deploy

This repo is deploy-ready for Vercel as a zero-config static site. Push to GitHub, click **Import** in the Vercel dashboard, and the site is live in under a minute.

## Repository layout

```
.
├── index.html        # the complete design system, self-contained
├── icons/            # Chapter XII — the icon layer
│   ├── README.md               # the contract (start here)
│   ├── oneness-icons.json      # token manifest — the AI-agent entry point
│   ├── oneness-icons.svg       # full sprite · 1,512 glyphs
│   ├── oneness-core.svg        # brand-core sprite · 53 glyphs
│   ├── svg/                    # every glyph as a standalone file
│   └── oneness-icon-pack.zip   # the complete pack · 6 weights · 4.1 MB
├── images/           # grain, library, and blurred asset folders
│   ├── grain/        # the five anchor surfaces, landscape + square
│   ├── library/      # founder, plant, interior, candid photo library
│   └── blurred/      # blurred grain mood backdrops
├── 404.html          # quiet not-found page
├── vercel.json       # caching headers + URL rewrite for the long filename
├── _source/          # original handoff bundle from Claude Design
│   ├── BUNDLE-README.md
│   └── chats/        # design conversation transcripts (intent & rationale)
└── README.md
```

## Iconography

Two layers, one vocabulary: **39 bespoke house glyphs** carry brand meaning, and a
**1,512-glyph standard pack** ([Phosphor](https://phosphoricons.com) v2.1.1, MIT) covers
the long tail. Both inherit `currentColor` and size through the `--toc-icon-*` tokens.

Everything lives in [`icons/`](icons/) — download the whole pack from Chapter XII on the
live site, or read [`icons/README.md`](icons/README.md) for the reference contract.
Coding agents should read [`icons/oneness-icons.json`](icons/oneness-icons.json): it maps
60 brand meanings (`pillar.vitality`, `offering.arcea`, `action.virtual-tea`) to glyphs,
and tags all 1,512 for search.

## Source of truth

This system originated from a brief by the client, iterated in [Claude Design](https://claude.ai/design) over two sessions. The full conversation transcripts live in [`_source/chats/`](_source/chats/) and show the rationale behind every design decision (sharp DNA, Aesop-inspired editorial layout, Cormorant + Jost pairing).

## Credits

Design direction: client brief, refined in Claude Design.
Editorial implementation: Edition II.
Polish & production: surgical pass using the [Impeccable](https://github.com/jacobwgillespie/impeccable) skill — accessibility, performance, and metadata only; brand DNA preserved.
