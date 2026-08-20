# The Oneness Letter · newsletter master

One newsletter design, held long term. Documented as **Chapter XXII** of the
design system.

| File | What it is |
|---|---|
| `newsletter.html` | The master. Paste into an ESP, swap the merge fields, send. |

A newsletter earns trust by arriving the same way every time. Variation belongs
**inside** the letter — in the three body registers — never in its chrome. The
masthead, the thread, the sign-off and the footer do not change between issues.

---

## Format

| Element | Spec |
|---|---|
| Send width | 600px, single column, nested tables |
| Length | 500–800 words. Under 500 is a note; over 800 is a blog post |
| Cadence | Weekly. Fortnightly is the floor. Consistency beats frequency |
| Byline | Always Rachel Mense, never the brand. Date always visible |
| Subject | 4–8 words, sentence case, states the idea — never a curiosity gap |
| Ask | Zero or one. Delete the ask block and the design still resolves |

## Anatomy

1. Gold rule + apothecary locator — coordinate, lunar phase, place
2. Centred masthead — eyebrow, issue number, display line, byline and date
3. Gold diamond thread — closes the header, the last centred element
4. Body — three registers, left-ranged. **Prose is never centred**
5. Cormorant italic sign-off — first person, first name, every time
6. The ask — one coral button and the permission line
7. Footer — six blocks, none optional

---

## The three body registers

All permitted variation lives here. Two tints, close enough to belong to one
paper stock and far enough apart to read as different.

### 01 · Prose — the default

Ground ivory `#f9f9f7` · Jost 300 · 16 / 1.78 · ink-700 `#3D2E1A` · no border.
Carries the argument.

### 02 · Quote plate — turns and asides

Ground gold-50 `#FBF6EC` · **2px gold-500 left rule** · Cormorant italic 23 / 1.34 ·
violet-800 ink. Optional tracked gold-700 label beneath.
For the turn, a pulled line, or an editorial side note.

### 03 · Highlight box — practical notes

Ground paper `#f4f1ea` · **1px gold hairline all round** · Jost 300 · 16 / 1.75 ·
tracked gold-700 label on top.
For the small thing, a standing note, anything the reader is meant to *do*.

> The quote plate is **ruled on one edge**; the highlight box is **enclosed**.
> That structural difference, not the colour, is what tells a reader which is which.
> **Never run the two tints back to back** — separate them with prose or they
> read as one band.

Both blocks are reusable: duplicate the whole `<tr>` and change the label.
Each ships with the background set as **both** a `bgcolor` attribute and an
inline style, so Outlook and the webmail clients agree.

---

## The ask

- **Coral `#ff856b` ground, violet-800 `#1E0A2E` ink.** Never Ivory — coral with
  ivory measures 2.26:1 and fails WCAG AA. Violet on coral measures **7.75:1**.
- **Coral appears once per send and nowhere else** — not as a rule, not as a dot,
  not as a border.
- **The permission line is part of the ask**, set directly beneath the button:
  *"If it's not for you, that's completely fine — there's nothing you need to do."*
- **Approved wording only:** *Book a Virtual Tea* · *Book a free Virtual Tea* ·
  *Let's share a pot of tea*. Never *book now*, *schedule a discovery call*,
  *claim your free session*.
- **One ask, or none. Never stacked.** No button plus text link.

---

## Footer — six blocks, none optional

1. **Signature** — Cormorant italic wordmark + positioning line
2. **Sender identification** — name, business, city/country, real reply-to (never no-reply)
3. **Wellness & medical disclaimer** — bordered inset, not fine print
4. **Legal links** — Privacy · Terms · Full disclaimer · browser view
5. **Consent reminder** — *"You're receiving this because you asked to hear from me."*
6. **Exit** — Unsubscribe **and** *Write less often*

Five of the six are there because a regulator put them there.

---

## Tokens, inlined

Email has no CSS variables. Every value is a literal in the file.

| Role | Value |
|---|---|
| Ground | Ivory `#f9f9f7` |
| Quote tint | Gold-50 `#FBF6EC` |
| Highlight tint | Paper `#f4f1ea` |
| Body ink | Ink-700 `#3D2E1A` |
| Thread (decorative only) | Gold-500 `#B8965A` |
| Text gold | Gold-700 `#7B6435` — 4.6:1 |
| Action | Coral `#ff856b` with violet-800 ink |
| Radius | `0px`, everywhere |
| Display | Cormorant Garamond 300, one italic gold word per send |
| Body | Jost 300 · 16px / 1.78 |
| Label | Jost 500 · 10px / .32em uppercase |

Pure `#fff` and `#000` appear nowhere.

---

## Email-client reality

| Where | What happens | Handling |
|---|---|---|
| Gmail / Outlook | Webfonts stripped | Georgia + Helvetica/Arial fallbacks on every element. The serif/grotesque tension survives; the letterforms don't. |
| Outlook desktop | No radius, no flex | All tables; the CTA is a padded anchor inside a coloured `<td>`. |
| Tinted blocks | Outlook ignores some inline backgrounds | Set as both `bgcolor` attribute and inline style. |
| Gmail dark mode | May force-invert the ivory ground and flatten the two tints into one | **Test before the first send.** |

Merge fields to swap for your ESP's tokens: `{{unsubscribe_url}}`,
`{{preferences_url}}`, `{{webview_url}}`.

---

## Content provenance

The filled issue is the newsletter playbook's own approved worked example —
*"Your cells don't just need nutrients"*, 632 words, Pillar 2, Green gate.
No product, no claim, one contrast pair, a qualification that admits ignorance,
and a free small thing.

---

## Blockers that outrank the design

1. **The Virtual Tea cannot be booked.** `bookingEmbedUrl` is empty and
   `theonenesscircle.com` does not resolve. The CTA converts at zero until wired.
2. **No ESP and no list exist.** Consent must be evidenced per recipient —
   source, date, mechanism — before any send.

---

## Pre-send checklist

- [ ] Maps to exactly one messaging pillar
- [ ] Zero banned-language Table 1 words
- [ ] No therapeutic or structure/function claim — scanned twice
- [ ] No product testimonial from Rachel (TGA s24(4))
- [ ] No income or earnings reference without the full IDS
- [ ] No price quoted — none are confirmed
- [ ] 500–800 words
- [ ] One ask, or none. Never stacked
- [ ] The turn does not hedge
- [ ] The qualification section exists
- [ ] Bylined Rachel Mense, date visible
- [ ] Coral used exactly once, or not at all
- [ ] The two tints are not adjacent
- [ ] Consent evidenced · unsubscribe functional · sender identified
- [ ] Scanned for AI tells — rule of three, uniform rhythm
- [ ] Rendered in Gmail dark mode before send
- [ ] Still interesting with every brand name removed
