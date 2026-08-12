# Iconography — the standard pack

> Chapter XII of **The Oneness Circle — Design System**
> Volume I · Edition II · MMXXVI

This folder is the whole icon layer of the system: one library, one weight, one
addressing scheme, and a manifest that lets a coding agent resolve a *meaning*
into a glyph without guessing at names.

**Download the pack:** [`oneness-icon-pack.zip`](oneness-icon-pack.zip) · 4.1 MB ·
1,512 glyphs × 6 weights (9,072 SVG files) + both sprites + the manifest + the licence.

---

## Two layers, one vocabulary

| Layer | Count | ID scheme | Lives in | Purpose |
|---|---|---|---|---|
| **House glyphs** | 39 | `#icon-{name}` | inline sprite in `index.html` | The bespoke marks that carry brand meaning. |
| **Standard pack** | 1,512 | `#i-{name}` | `oneness-icons.svg` | Utility, navigation, wayfinding — the long tail. |

Where a house glyph exists, it **outranks** the pack. Where it does not, the pack
answers — and no new icon gets drawn. Per the client brief, only **four custom
icons** are sanctioned for core pages beyond the existing house set.

---

## Files

| File | What it is |
|---|---|
| `oneness-icons.json` | **The token manifest.** Start here if you are an agent. Contract, semantic tokens, and all 1,512 glyphs with categories + tags for search. |
| `oneness-icons.svg` | Full sprite — all 1,512 glyphs, `regular` weight, as `<symbol id="i-{name}">`. |
| `oneness-core.svg` | Brand-core sprite — the 53 glyphs behind the semantic tokens. Prefer this for site builds; it is 29 KB against 734 KB. |
| `svg/{name}.svg` | Every glyph as a standalone file, for the mask pattern and for `<img>`. |
| `oneness-icon-pack.zip` | The complete pack, all six weights, for download. |
| `LICENSE-phosphor.txt` | MIT licence for the underlying pack. |

---

## How to reference a glyph

There are exactly two working patterns, and one that looks right and isn't.

### A · Inject the sprite, then use the hash — *preferred*

This is how the 39 house glyphs already work. Do the injection **once** per document:

```js
fetch('/icons/oneness-core.svg')          // or oneness-icons.svg for the full library
  .then(r => r.text())
  .then(t => {
    const d = document.createElement('div');
    d.hidden = true; d.innerHTML = t;
    document.body.prepend(d);
  });
```

Then anywhere in the document:

```html
<svg class="ico ico-md"><use href="#i-leaf"/></svg>
```

### B · Mask a loose file

For a single glyph, or where CSS must own it (pseudo-elements, backgrounds).
`background: currentColor` does the tinting, so the ink tokens still apply:

```html
<span class="ico-mask ico-md" style="--g:url('/icons/svg/leaf.svg')"></span>
```

### ✗ Never — cross-document `<use>`

```html
<svg class="ico"><use href="/icons/oneness-icons.svg#i-leaf"/></svg>
```

External `<use>` references are SVG 2 and were **never shipped in Blink or WebKit**.
This renders nothing in Chrome, Edge, and Safari. Firefox alone resolves it — which is
exactly what makes the mistake easy to ship. Inject the sprite (A) or mask a file (B).

---

## The rules

Five rules govern every glyph:

1. **Resolve meaning first.** Look up `semantic["pillar.vitality"]` before you go
   looking for an icon called `leaf`. Sixty brand meanings are mapped; they encode
   decisions the naming does not.
2. **One weight — `regular`.** Sitewide, without exception. The other five weights
   ship in the archive for completeness. Mixing them dissolves the vocabulary.
3. **Size through a token.** `--toc-icon-xs` … `--toc-icon-2xl`
   (14 · 16 · **20 default** · 24 · 32 · 48px), wearable as `.ico-xs` … `.ico-2xl`.
   A raw pixel size on a glyph is a defect.
4. **Never set a fill.** Every symbol carries `fill="currentColor"` and takes the ink
   of whatever it sits in. To override, set the *element's* colour with an ink token —
   `--toc-icon-ink-quiet`, `--toc-icon-ink-thread`, `--toc-icon-ink-onDark`.
5. **Gold ink needs the safe gold.** Sacred Gold `#B8965A` measures 2.6:1 on ivory and
   fails WCAG AA. For a gold glyph on a light ground use `--toc-icon-ink-thread`
   (gold-700 `#7B6435`, 5.36:1).

### Ink tokens

| Token | Resolves to | Use on |
|---|---|---|
| `--toc-icon-ink` | `currentColor` | the default — inherit the surface |
| `--toc-icon-ink-quiet` | `--toc-ink-500` | meta and secondary glyphs |
| `--toc-icon-ink-thread` | `--toc-gold-700` | gold glyphs on a light ground |
| `--toc-icon-ink-onDark` | `--toc-ivory` | violet · sage · blue grounds |

---

## For coding agents

Read [`oneness-icons.json`](oneness-icons.json). It is the single source of truth and
needs no other context.

```js
const m = await fetch('/icons/oneness-icons.json').then(r => r.json());

// 1 — meaning → glyph (preferred)
m.semantic['action.virtual-tea'].token        // "i-tea-bag"
m.semantic['pillar.gene-keys'].token          // "i-dna"

// 2 — search by tag or category, when no semantic token fits
m.icons.filter(i => i.tags.includes('meditation'))
m.icons.filter(i => i.categories.includes('nature'))

// 3 — the rules and the working reference patterns, in machine form
m.contract.rules
m.contract.patterns        // .sprite (preferred) and .mask
m.contract.antipattern     // the cross-document <use> trap, and why
```

Semantic groups: `pillar` · `offering` · `action` · `botanical` · `science` ·
`practice` · `sound` · `editorial` · `social` · `status`.

The `offering` group encodes the colour-by-offer mapping from the client brief —
Young Living → green, ARCEA → blue, core brand → gold + violet — so an agent picking
an icon for a page also picks up which colourway that page belongs to.

---

## Attribution

The standard pack is [**Phosphor Icons**](https://phosphoricons.com) v2.1.1, MIT
licensed. Glyphs are redistributed unmodified on their native 256-unit grid; the
Oneness Circle layer adds the sprite, the token scheme, and the semantic map.
