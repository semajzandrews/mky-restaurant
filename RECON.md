# RECON — MKY Restaurant

Slug: `mky-restaurant`
Stage: REVIEW (no deploy; Semaj approves LIVE)
Built: 06-18-2026

---

## Verified business facts

| Field | Value | Source |
|---|---|---|
| Name | MKY Restaurant (legal: MKY & DELY LLC) | Official site + Google listing |
| Category | Peruvian restaurant (100% Peruvian, small dine-in ~16 seats) | whereyoueat, Atly listing |
| Address | 396 Main St, City of Orange, NJ 07050 | Official site, Seamless |
| Phone | (862) 704-2887 | Official site (matches facts file) |
| PIN | 042887 (last 6 of phone) | per pinRule |
| Rating | 4.7 (45 reviews) | facts file |
| Hours | Mon to Sat 5:30 AM to 8:00 PM; Sun 5:30 AM to 7:00 PM | Official site (mkydelyllcnj.com), confirmed via search |
| Language | Spanish-first (Peruvian/Latino-serving) with vetted ES/EN toggle | facts `_language` note |

Official ordering site: mkydelyllcnj.com (confirms name, address, phone, hours).
Menu items confirmed real: ceviche / pescado al estilo peruano, beef-or-chicken saltado
(lomo/tallarin saltado), arroz chaufa (fried rice), chicharron, **leche de tigre** (explicitly
on their menu, surfaced via their own item page), homemade soda / chicha. No prices are
published publicly, so every card says "Pregunta por el precio del dia" rather than inventing one.

### Rating handling
4.7 / 45 reviews is solid but NOT a major anchor (vs Sun Fish's 648). Per rule 11 this is
between soft and strong, so I led with the FOOD and the family-table warmth, and used reviews
only as ONE tasteful, low-key quote with no star count emphasized and no fabricated reviewer name
(attributed "Comensal local / Local diner · Google", generic and honest).

### Social
No social handle could be verified as exactly this business, so none is shown (rule 8).

### Lat/lng + map
Used the address-string keyless Google embed (Ramos pattern):
`https://www.google.com/maps?q=396+Main+St,+City+of+Orange,+NJ+07050&z=16&output=embed`.
Google resolves the address string, so no manual geocode was needed. Per ARSENAL §6, the
`output=embed` iframe can appear blank in the preview sandbox but renders fully in a real browser;
verify in real Chrome before LIVE. Tinted with a flat low-opacity brand overlay (no CSS filter on
the iframe).

---

## Art direction (assigned kit)

- Accent terracotta `#C8472B`, secondary Andean green `#1B5E4F`, warm base `#FBF4E9`, ink `#2A1B12`, gold `#E2A33C`.
- Display: **Sentient** (Fontshare). Body: **General Sans** (Fontshare). Both loaded via Fontshare CDN.
- Layout: warm editorial columns, food-forward. Mood: warm Andean, family table.
- `<html lang="es">`, Spanish-first copy, hand-written vetted EN toggle (no machine translation;
  every translatable node carries `data-es` / `data-en`, swapped by a tiny JS toggle).
- A subtle Peruvian flag motif (3 terracotta/cream stripes) accents the hero photo, and a marquee
  strip of dish names runs in Andean green.

## Signature interaction shipped (assigned)

**"Plato del dia" flip cards with a ceviche citrus / steam micro-animation on hot vs cold dishes.**
Six dish cards flip on tap/click/Enter (3D rotateY, `transform-style: preserve-3d`) to reveal
ingredients chips + a description. HOT dishes (Lomo Saltado, Arroz Chaufa) emit a gentle CSS steam
plume; COLD/citrus dishes (Ceviche, Refrescos) carry a pulsing gold citrus ring. Keyboard
accessible (role=button, tabindex, Enter/Space), `prefers-reduced-motion` disables the steam/citrus.
This is NOT a horizontal-scroll device. The 8 siblings each got a different signature.

## Other furniture / rules

- Real per-brand NAV: round MKY brand mark + "Cocina Peruana" tagline, section links, ES/EN toggle,
  persistent terracotta call CTA. On mobile (<=680px) nav links collapse, call pill becomes a 46px
  icon circle, and a separate 56px fixed tap-to-call button sits bottom-right. Verified no overflow
  at 375px (scrollWidth === clientWidth === 375).
- Footer: business name, address, phone, both hours lines, a CTA, and a bespoke "Hecho con cuidado
  por bysemaj.com" credit linking https://bysemaj.com, styled in the brand (gold link, terracotta spark).
- 12-hour time everywhere ("5:30 AM to 8:00 PM"). Live Open now / Closed pill computed in
  America/New_York via Intl.DateTimeFormat, updates each minute, also highlights today's row in the
  hours table. Verified showing "Abierto ahora · cierra 8 PM".
- NO em dashes in visible copy (validated programmatically). Time ranges use an en-dash glyph in the
  hours table only, never an em dash.

## Imagery (all Unsplash direct source URLs, all verified HTTP 200, all unique)

Every photo earns its place and the category reads instantly as a Peruvian restaurant. Each food
image was visually inspected; several first picks were rejected and swapped:

- Hero: `1604908176997-125f25cc6f3d` (saltado-style bowl)
- Lomo Saltado: `1551183053-bf91a1d81141` (beef + tomato wok saute) — replaced a wrong "flaming wraps" shot
- Ceviche: `1535399831218-d5bd36d1a6b3` (textbook Peruvian ceviche w/ camote, choclo, cancha)
- Arroz Chaufa: `1603133872878-684f208fb84b` (fried rice)
- Chicharron: `1626645738196-c2a7c87a8f58` (golden fried, crispy) — replaced a wrong "skewers/anticucho" shot
- Pescado Frito: `1580476262798-bddd9f4b7369` (fish fillet) — this card replaced the original
  "Leche de Tigre" card whose stock image was actually a green soup; reframed to a dish their menu
  lists with an accurate image. (Leche de tigre still appears as a real menu term in the marquee.)
- Refrescos de la Casa: `1556679343-c7306c1976bc` (cold citrus drink) — replaced a chicha-morada
  stock shot that (a) read as a smoothie bar and (b) collided with a sibling's used image
  (`1622597467836` is logged under pinas-locas-quetzaly). Copy reframed honestly to house drinks
  incl. chicha morada.
- Story: `1592861956120-e524fc739696` (diverse table sharing food), `1543353071-873f17a7a088`
  (Latin food spread: beans/lime/avocado/plantain), `1466637574441-749b8f19452f` (fresh prep board).
  These replaced three first-pick stock shots that read as white fine-dining / a white couple in a
  home kitchen, which fail Semaj's demographic rule for City of Orange (Black + Caribbean + Latino).

Demographic note: people-imagery was chosen to read true to the neighborhood clientele, not generic
white stock. Zero image is reused on the page; zero image collides with a same-city sibling (checked
against `.orchestrator/used_images.json`).

## Arsenal pieces fired

- Fontshare type pairing (Sentient + General Sans) — characterful display + clean body, new pairing.
- Marquee technique (Magic UI marquee, restyled to brand) for the dish-name strip.
- CSS 3D flip card (signature) + custom steam/citrus keyframe micro-animations (hand-built, not a library default).
- IntersectionObserver scroll-reveal (subtle translateY/opacity), smooth-scroll anchors.
- Keyless Google Maps embed (Ramos pattern) with brand overlay tint.
- Live timezone-aware Open/Closed status (Intl.DateTimeFormat, America/New_York).
- Vetted bilingual ES/EN toggle (hand-translated data attributes, no machine translation).

## Verification done

- 375px: no horizontal overflow, nav/call/cards/story/hours all clean; flip cards work on tap + keyboard.
- All 10 Unsplash URLs return HTTP 200; 10 unique IDs, 0 duplicates, 0 sibling collisions.
- No em dashes; no 24-hour times; lang=es; map embed present.
- Open/Closed pill verified live ("Abierto ahora · cierra 8 PM").

## Pre-LIVE to-dos (for Semaj)

- Confirm the Google map renders in real Chrome (preview sandbox can show it blank).
- Swap stock food/people photos for MKY's REAL plates and room before public launch.
- Confirm exact menu names/prices with the owner and confirm leche de tigre / chicha availability.
- Wire the PIN (042887) into the BWYW claim flow.
