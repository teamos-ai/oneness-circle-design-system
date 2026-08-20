# Newsletter plates I–III · The Oneness Circle

Three email designs built on the Edition II design system, for the nurture sequence
and the weekly newsletter.

| File | Plate | Register | Words | Ask |
|---|---|---|---|---|
| `01-the-letter.html` | I · The Letter | Private correspondence | 120–350 | Zero, or one text link |
| `02-the-broadsheet.html` | II · The Broadsheet | Published essay | 500–800 | One, at the very end |
| `03-the-plate.html` | III · The Plate | Stated invitation | 150–250 | Exactly one |

`newsletter-plates.html` is the comparison document — all three rendered at 600px
with the spec, the footer architecture and the pre-send rules.

---

## Which plate for which send

**Plate I — the sequence workhorse.** The email playbook is explicit: *don't send a
designed template with a hero image*. Plate I is the answer to that — a centred
masthead and one gold thread, then plain left-ranged prose. Use it for welcome
emails 1–4 and for every nurture send after.

**Plate II — the weekly newsletter.** A different rhythm and a different job. This
is the only publication surface, so it is the only place a masthead plate,
a pull-quote and a CTA band are earned.

**Plate III — rationed.** Welcome email 5 (the invitation), and occasional
single-idea broadcasts. Its whole effect depends on being rare. If it goes out
monthly it stops meaning anything.

> Recommended spine for the nurture sequence: **Plate I × 4, then Plate III once.**

---

## The six movements (Plate II)

Structure is from the newsletter playbook, expressed in the design:

| # | Movement | Design treatment |
|---|---|---|
| I | The observation | Plain prose, ivory ground |
| II | The turn | Gold plate, `#FBF6EC`, 2px gold left border, Cormorant italic |
| III | The reasoning | Plain prose, closed by a three-diamond mark |
| IV | The qualification | Gold-700 label — *Where this breaks down* |
| V | The small thing | Paper inset `#f4f1ea`, hairline gold border |
| VI | The close + one ask | Sign-off, then the CTA band |

The turn is the paragraph that must not hedge, which is why it gets the only
pull-quote treatment in the system. If a draft's turn doesn't survive being set
at 24px italic, the draft doesn't have a turn.

---

## Footer architecture — identical in all three

1. **Signature block** — Cormorant italic wordmark + positioning line
2. **Sender identification** — name, business, city/country, real reply-to (never no-reply)
3. **Wellness & medical disclaimer** — bordered inset, not fine print
4. **Legal links** — Privacy · Terms · Full disclaimer (mirrors the site's `legalNav`)
5. **Consent reminder** — *"You're receiving this because you asked to hear from me."*
6. **Exit** — Unsubscribe **and** *Write less often*

Five of the six are there because of a regulator, not a designer. None is optional.

---

## CTA rules encoded in the templates

- **One ask per surface.** Never a button plus a link.
- **Coral exactly once, or not at all.** Plate III only.
- **Coral carries violet ink `#1E0A2E`, never ivory.** Coral + ivory measures
  2.26:1 and fails WCAG AA; coral + violet-800 measures 7.75:1.
  The same defect exists in the design system's `.btn-coral` and `.btn-gold` —
  worth fixing upstream.
- **The permission line is part of the ask**, set directly beneath every CTA:
  *"If it's not for you, that's completely fine — there's nothing you need to do."*
- **Approved wording only:** *Book a Virtual Tea* · *Book a free Virtual Tea* ·
  *Let's share a pot of tea*. Never *book now*, *schedule a discovery call*,
  *claim your free session*.

---

## Tokens, inlined

Email has no CSS variables. Every value below is a literal in the files.

| Role | Value |
|---|---|
| Ground | Ivory `#f9f9f7` |
| Inverse ground | Violet noir `#1E0A2E` (footer `#11051A`) |
| Body ink | Ink-700 `#3D2E1A` |
| Thread (decorative only) | Gold-500 `#B8965A` |
| Text gold on light | Gold-700 `#7B6435` — 4.6:1 |
| Gold on dark | Gold-300 `#D4AF7A` — 8.97:1 |
| Action | Coral `#ff856b` with violet ink |
| Paper inset | `#f4f1ea` |
| Radius | `0px`, everywhere |
| Display | Cormorant Garamond 300, one italic gold word per send |
| Body | Jost 300 · 16px / 1.78 |
| Label | Jost 500 · 10px / .32em uppercase |

Pure `#fff` and `#000` appear nowhere.

**Per-issue colour decision (Plate II only):** the masthead ground. Violet (default),
sage `#283b20`, or blue `#0b286d`. Swap it wholesale — pillars never mix surfaces
in one layout.

---

## Email-client reality

| Where | What happens | Handling |
|---|---|---|
| Gmail / Outlook | Webfonts stripped | Georgia + Helvetica/Arial fallbacks declared on every element. The serif/grotesque tension survives; the letterforms don't. |
| Outlook desktop | No radius, no flex | All tables; buttons are padded anchors inside a coloured `<td>`. Radius is 0 anyway. |
| Gmail dark mode | May force-invert Plates I & II | **Test before first send.** Plate III inverts least. |
| Apple Mail | Honours `color-scheme` | Declared in all three heads. |

Merge fields to swap for your ESP's tokens: `{{unsubscribe_url}}`,
`{{preferences_url}}`, `{{webview_url}}`.

---

## Content provenance

- **Plate I** — welcome email 4, verbatim from `40-content-engine/channel-playbooks/email-playbook.md`,
  with the specific income figure removed (per the Amber-gate note: safer to say
  "almost nothing" without the number, unless the full IDS is attached).
- **Plate II** — the worked example from `40-content-engine/core-content/newsletter-playbook.md`.
  632 words, Pillar 2, Green gate.
- **Plate III** — **newly written.** Assembled from the verified published description
  of the Virtual Tea plus the permission line. **Needs Rachel's sign-off before it sends.**

---

## Blockers that outrank the design

1. **The Virtual Tea cannot be booked.** `bookingEmbedUrl` is empty and
   `theonenesscircle.com` does not resolve. Every CTA converts at zero until wired.
2. **No ESP and no list exist.** Consent must be evidenced per recipient —
   source, date, mechanism — before any send.
3. **Plate III's copy is unapproved.** See above.

---

## Pre-send checklist

- [ ] Maps to exactly one messaging pillar
- [ ] Zero banned-language Table 1 words
- [ ] No therapeutic or structure/function claim — scanned twice
- [ ] No product testimonial from Rachel (TGA s24(4))
- [ ] No income or earnings reference without the full IDS
- [ ] No price quoted — none are confirmed
- [ ] Within the plate's word range
- [ ] One ask, or none. Never stacked
- [ ] The turn paragraph does not hedge (Plate II)
- [ ] The qualification section exists (Plate II)
- [ ] Bylined Rachel Mense, date visible
- [ ] Coral used exactly once, or not at all
- [ ] Consent evidenced · unsubscribe functional · sender identified
- [ ] Scanned for AI tells — rule of three, uniform rhythm
- [ ] Rendered in Gmail dark mode before send
- [ ] Still interesting with every brand name removed
