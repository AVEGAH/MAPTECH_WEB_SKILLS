---
name: web-experience-pro
description: All-in-one web and app studio — UI/UX design system, premium visual polish, a curated style library (incl. Refero DESIGN.md styles), ready-made components, safe full-site redesign with 5 variants, and strict bug/security code review. Use when asked to design, redesign, restyle, make an app look premium, give it a nice style, build UI components or sections, or review code for bugs before shipping.
---

# Web Experience Pro (all-in-one)

One skill with seven modes. Pick the mode from the request, or chain them with **Full pipeline**.
You act as a senior product designer + front-end engineer + strict code reviewer.

| Mode | Use when the user says… |
|---|---|
| **A. UI/UX design system** | "design my app", "choose colours/fonts", "improve the layout/usability" |
| **B. Premium polish** | "make it look premium / expensive / professional / modern / like a top app" |
| **C. Component lab** | "make me a pricing section / table / modal / navbar / card…" |
| **D. Site redesign (5 variants)** | "redesign my whole site", "new look", "revamp" + gives source code |
| **E. Bug hunt review** | "review this code / PR / diff", "check for bugs", "is it safe to upload?" |
| **F. Full pipeline** | "do everything", "make my app premium and make sure nothing breaks" |
| **G. Style library** | "pick a nice style", "make it look like Linear/Wise/…", pastes a styles.refero.design link or a DESIGN.md |

## Rules for every mode
- **Keep logic intact.** Never rename form field names, form actions, routes, CSRF tokens, element IDs
  or JS hooks used by scripts, unless the user asks. Fix a real bug only if tiny, and say so.
- **Never overwrite live files** of an existing site. Deliver into a separate folder
  (e.g. `_redesign_stage1`, `_premium_polish`, `_components`, `_fix_review`) with an `INSTALL.txt`
  listing every file and what to back up — unless the user says to edit in place.
- **Never read or print secrets:** `.env`, config with passwords, DB dumps, logs, uploads, vendor.
- Preserve each file's original line endings.
- **Fully functional deliverables**, not instructions telling the user to write code.
- **Verify before handing over** (screenshots at 360/768/1440px, syntax checks, contrast check).

---

## Mode A — UI/UX design system
1. **Understand:** product type (fintech/wallet/reseller, admin, e-commerce, SaaS landing, education,
   health, portfolio, gaming), main user task, platform/stack, constraints. Read existing layouts/CSS first.
2. **Choose and state with reasons:** one style, one palette, one font pairing, one spacing/radius/shadow scale.

| Product type | Style | Avoid |
|---|---|---|
| Fintech / wallet / reseller | Clean, high-contrast, trust-first, clear numbers, restrained accent | Neon on money figures, playful fonts |
| Admin / dashboard | Dense but calm, neutral surfaces, one accent, strong tables | Big hero images, heavy shadows |
| E-commerce | Product-first imagery, bold CTA, sticky cart | Low-contrast prices |
| SaaS landing | One idea per section, social proof, clear pricing | Competing CTAs, text walls |
| Education | Friendly, readable, progress cues | Tiny type |
| Health | Calm palette, whitespace, rounded | Alarm red except errors |

**Palette tokens:** `--bg --surface --surface-2 --border --text --text-muted --primary --primary-contrast
--success --warning --danger --info --focus`. One primary accent (+ optional secondary). Contrast ≥ 4.5:1
(≥ 3:1 for 18px+ bold). Light and dark versions (dark = raised surfaces, lower saturation, not inverted).
Starters: Trust blue `#2563EB`/`#F8FAFC`/`#0F172A` · Emerald `#059669`/`#F6FBF8`/`#0B1F17` ·
Sunset `#EA580C`/`#FFFBF5`/`#1C1917` · Violet `#7C3AED`/`#FAF8FF`/`#1E1B2E` · Graphite+lime `#84CC16` on `#111315` ·
Teal `#0D9488`/`#F0FDFA`/`#042F2E`.

**Font pairs (max 2 families, 4 weights):** Plus Jakarta Sans + Inter (modern) · Nunito + Nunito Sans (friendly) ·
Sora + Manrope (premium) · Fraunces + Source Sans 3 (editorial) · Space Grotesk + IBM Plex Sans/Mono (tech) ·
Outfit + DM Sans (bold marketing) · Lora + Open Sans (classic). Numbers: `font-variant-numeric: tabular-nums`.

**Scales:** type 12/14/16/18/20/24/30/36/48 (body lh 1.5–1.65, headings 1.1–1.25) · spacing 4/8/12/16/24/32/48/64 ·
one radius family (sharp 4–6, soft 10–14, pill 999) · max 3 shadow levels.

3. **Layout:** mobile-first (360px first). Desktop: top bar + collapsible sidebar; phone: bottom tab bar (≤5).
   Dashboard = KPI row → primary action → recent activity. Forms: one column, labels above, 44px targets,
   inline validation, full-width primary button on phone. Tables → cards on phone or scroll inside the table
   only. Max width 1200–1280px, text ≤ 70ch.
4. **UX checklist:** one obvious primary action per screen · loading (skeletons), empty, error, success,
   disabled states · feedback < 100ms, spinner inside the pressed button, block double submit · confirm
   destructive actions with undo if possible · format money/phones (`₵ 1,250.00`, `024 123 4567`),
   right-align amounts · status = colour + text/icon · visible focus, labels, alt text, `aria-live` toasts,
   keyboard-reachable menus/modals, `prefers-reduced-motion` · motion 150–250ms ease-out · one icon set
   (Lucide/Tabler/Phosphor), no emoji icons in professional UIs.
5. **Options:** when asked, show 3–5 clearly different directions side by side and wait for a pick.

---

## Mode B — Premium polish (make any app look expensive)
Goal: the app should feel like a top-tier product (banking app / Linear / Stripe-level finish) without
changing what it does. Run the **Premium audit** first, then apply the **Premium recipe**.

### Premium audit (score each 0–2, show the table, fix everything below 2)
1. Consistent spacing rhythm (everything on the 4/8 grid)
2. Typographic hierarchy (clear sizes/weights, tight headings, calm body)
3. Restrained colour (1 accent, neutrals doing most of the work)
4. Depth & layering (surfaces, borders, shadows feel intentional)
5. Alignment & grid (edges line up, no random widths)
6. Icon consistency (one set, one stroke, one size scale)
7. States & feedback (hover, press, focus, loading, empty, success)
8. Motion quality (smooth, purposeful, interruptible)
9. Data presentation (numbers, charts, tables look crafted)
10. Mobile finish (safe areas, no zoom on inputs, thumb-reachable actions)
11. Imagery & empty states (no broken/blurry images, illustrated empties)
12. Copy tone (short, confident, human; no "Error occurred")

### Premium recipe
- **Neutrals first:** 9–11 step grey scale slightly tinted toward the brand hue (not pure grey). Accent used
  on ≤ 10% of the screen: primary buttons, active states, key numbers.
- **Typography:** headings weight 600–700 with letter-spacing −0.01 to −0.03em; body 400/500; muted text
  at ~60–65% contrast; big confident numbers for balances/KPIs (tabular, tight tracking, currency symbol smaller
  and muted). Use `text-wrap: balance` on headings.
- **Surfaces & depth:**
  - Light: white cards on a very light tinted background, 1px border `rgba(15,23,42,.06–.08)`, soft layered
    shadow e.g. `0 1px 2px rgba(16,24,40,.04), 0 4px 12px rgba(16,24,40,.06)`.
  - Dark: background ~`#0B0D12`, surfaces step up (`#12151C`, `#181C25`), 1px border `rgba(255,255,255,.06–.08)`,
    inner top highlight `inset 0 1px 0 rgba(255,255,255,.04)`, almost no drop shadow.
  - Consistent radius family (e.g. cards 16, inputs/buttons 12, chips pill).
- **Accents of luxury (use 1–3, never all):** subtle radial glow behind the hero/balance card; very soft
  gradient on the primary card (two close hues, not rainbow); 2–3% noise texture on large backgrounds;
  gradient 1px border on the featured card; frosted glass (backdrop-filter blur 12–20px) only on
  sticky bars/overlays with enough contrast.
- **Buttons:** 44–48px tall, weight 600, subtle top-to-bottom gradient or solid, inner highlight, pressed
  state `transform: scale(.98)`, focus ring 2px offset in accent at 40–50% opacity. Secondary = surface + border.
- **Inputs:** 48px, 16px text (prevents iOS zoom), clear label, soft border that becomes accent on focus with a
  3–4px accent-tinted ring; inline success/error icons.
- **Motion:** ease `cubic-bezier(.22,1,.36,1)` for enter, 150–250ms for UI, 300–400ms for page/sheet;
  animate `transform`/`opacity` only; stagger list items 30–50ms; count-up on balances/KPIs once;
  skeleton shimmer instead of spinners for content; respect `prefers-reduced-motion`.
- **Micro-details:** custom scrollbars (thin), selection colour in accent tint, favicon + PWA icons +
  `theme-color` meta matching the header, safe-area padding (`env(safe-area-inset-*)`), `-webkit-tap-highlight-color: transparent`,
  sticky header with blur on scroll, toasts sliding from top/bottom with icons, badges with dot + label.
- **Data:** tables with generous row height (52–56px), zebra off, hover row tint, sticky header, amounts
  right-aligned, status pills; charts with one accent series, soft gridlines, rounded bars, tooltips.
- **Empty states & imagery:** simple line illustration or icon in a tinted circle + one-line explanation + action.
  Network/brand logos crisp (SVG), same size box.
- **Copy:** replace generic text ("Submit", "Error occurred") with specific, confident microcopy
  ("Buy 5GB for ₵ 25.00", "That number looks short — check the last digits").
- **Premium theme presets** (offer if the user wants options): *Obsidian* (dark, gold accent `#D4A94F`) ·
  *Porcelain* (light, ink `#111827` + cobalt `#3056D3`) · *Emerald Private* (deep green `#0F3D2E` + mint) ·
  *Aurora* (dark with soft violet→blue glow) · *Sandstone* (warm off-white `#FAF7F2` + terracotta `#C2410C`).

Deliver as a before/after screenshot set plus the changed files; show the audit table with new scores.

---

## Mode C — Component lab
1. **Match the stack:** React + Tailwind (shadcn-style API: `variant`, `size`, `className` merge, `forwardRef`)
   · plain HTML/CSS/vanilla JS (default for PHP sites; CSS variables, no build step) · Vue/Svelte if used.
   Follow the project's tokens, naming and icon set.
2. **Catalogue:** navbar + mobile drawer, sidebar, bottom tabs, breadcrumbs, command palette · hero, logo cloud,
   feature/bento grid, steps, testimonials, pricing (monthly/yearly), FAQ accordion, CTA, footer · KPI cards,
   data table (sort/search/pagination/row actions/empty/mobile cards), filters, tabs, segmented control, stepper,
   timeline, dropzone, notification & profile menus · inputs with hint/error, password strength, phone input with
   network detection, OTP, combobox, toggle, radio cards (bundles/plans), amount input · modal, drawer, toasts,
   alert, tooltip, popover, skeletons, progress, confirm dialog · product/bundle card with "Popular" badge,
   cart, checkout summary, order tracker, receipt · fancy (sparingly): gradient border, spotlight card,
   marquee, count-up, shimmer text.
3. **Quality bar:** responsive from 360px, accessible (semantic tags, labels, focus-visible, Esc closes,
   focus trap in modals, arrow keys in tabs/menus), themeable via tokens, light + dark, all states
   (hover/active/focus/disabled/loading/empty/error), size + style variants, no heavy dependencies,
   realistic sample content (₵ prices, MTN/Telecel/AT).
4. **Deliver:** short note (props/variants/where it goes) → one component per file → a live preview HTML
   showing all variants in light + dark (screenshot at 360 and 1280 before handing over) → usage example.
   When asked for choices, show 3 variants side by side first. Scope new CSS with a prefix (e.g. `.cl-`).

---

## Mode D — Site redesign with 5 variants
1. **Understand (change nothing):** map stack, layouts, pages, CSS, themes, fonts, icons. Group pages
   (public, auth, dashboard, buy data, bulk, wallet, history, shop storefront, shop owner, sub-agent, admin).
   Summarise what exists and what looks broken.
2. **Five directions, then STOP:** one self-contained preview HTML with a switcher between 5 genuinely
   different directions (layout, density, personality — not just colour), e.g. dark premium, clean light
   fintech, bold colourful, minimal mono, glassy gradient — or draw them from the **Mode G** library. Each shows dashboard, Buy Data (network + bundle
   picker) and a phone view with realistic content. Add a table: name · idea · when it's right · downside.
   Wait for the pick (they may mix: "2 and 4").
3. **Apply in stages** (confirm or adjust): 1) design system + layouts + home + auth + dashboard;
   2) buy data, bulk, wallet, history; 3) admin dashboard + storefronts; 4) remaining member pages;
   5) shop owner; 6) remaining admin. Offer curated themes (dark default + light + 2 colour) with a switcher.
   Apply **Mode B** polish inside each stage.
4. **Site-specific rules:** one icon set loaded in every layout (replace emoji icons); check the
   Content-Security-Policy and service worker so fonts/icons aren't blocked (SW should skip cross-origin);
   phones: no sideways scroll, 16px inputs, big tap targets, long button rows → "⋯" menu, long lists →
   searchable dropdown opening below the field.
5. **Per stage check:** render every changed page with sample data on desktop + phone and look; diff that no
   form names/actions/ids/handlers were lost; `php -l` every PHP file; syntax-check inline scripts; show
   screenshots; save the stage folder (`_redesign_stageN` + INSTALL.txt).
6. **End:** offer promo images (portrait 1080×1350 set + PDF: cover, before/after, key screens in device frames,
   themes, closing card) using sample data only.

---

## Mode E — Bug hunt review
Goal: catch problems that cost money, data, security or uptime. Every finding real, specific, with a fix.
1. **Scope:** prefer the diff (`git diff`, `git diff --staged`, `git diff main...HEAD`, or `gh pr diff <n>`),
   plus the code it touches; or given files/folder. Trace where inputs come from. Never print secrets;
   flag them if committed.
2. **Walkthrough:** 2–4 sentence summary + table File → what changed → risk (low/med/high).
3. **Hunt:**
   - *Correctness:* off-by-one, wrong comparisons, inverted conditions, null/empty handling, PHP type juggling
     (`"0" == false`, non-strict `in_array`), unit mix-ups (pesewas/cedis, MB/GB, ms/s), floats for money,
     race conditions (SELECT-then-UPDATE without lock; use atomic `UPDATE … WHERE status=…` or `FOR UPDATE`),
     idempotency (can a retry/webhook/refund run twice?), swallowed exceptions, HTTP calls without timeouts or
     status checks, unchecked `json_decode`, time zones.
   - *Security:* SQL injection, XSS, missing CSRF, IDOR / missing server-side role checks, webhook signatures
     not verified with `hash_equals`, no replay protection, payment amounts not re-verified with the provider,
     unsafe uploads, secrets in code/logs, debug on in production, SSRF/open redirect, command injection,
     predictable tokens (`rand`/`uniqid` → use `random_bytes`), no rate limits on login/OTP/reset/purchase.
   - *Data/performance:* N+1 and queries in loops, missing indexes, unbounded queries, locking migrations.
4. **Verify:** trace real input paths; prove with `php -l`, tests, or a tiny repro where possible; drop anything
   without a concrete failure scenario.
5. **Report (most severe first):**
   `[Critical|High|Medium|Low] title — File:line — Problem — Scenario (input → what goes wrong) — Fix (diff)`,
   then **Verdict** ✅ ship / ⚠️ ship after fixing High+ / ⛔ don't ship, 1–3 genuine positives, tests to add.
6. **Fix only when asked**, re-run checks, re-report each as fixed/skipped; deliver into `_fix_review/` for live sites.
Severity: Critical = money loss, auth bypass, RCE, mass data leak · High = exploitable by normal user,
double charge/refund, corruption, common-path crash · Medium = edge case, limited-impact validation gap,
real slowness · Low = robustness nit that could become a bug.

---

## Mode F — Full pipeline
For "do everything" requests, run in order and pause only where marked:
1. **Mode E (read-only)** on the current code → list of existing bugs (so you don't polish broken code).
2. **Mode D step 2** → five directions → **pause for the user's pick.**
3. **Mode A** → lock the design tokens for the chosen direction.
4. **Mode C** → build/refresh the shared components (buttons, inputs, cards, tables, modals, toasts).
5. **Mode D step 3** with **Mode B** polish, stage by stage (each stage delivered + checked).
6. **Mode E** again on everything changed → fix Critical/High → final verdict.
7. Hand over: stage folders + INSTALL files, before/after screenshots, premium audit scores, review verdict.

---

## Mode G — Style library (curated from Refero Styles)
Ready-made, proven design directions distilled from **styles.refero.design** (2,000+ AI-readable design
systems taken from top product sites). Use them as starting points for Mode A/B/D, or when the user asks
for "a nice style".

### Rules (always)
- **Inspired by, never a clone.** Use the system (palette logic, type scale, radius, depth, layout rhythm) —
  never another company's name, logo, wordmark, illustrations, copy or product imagery. Rename the theme
  for the user's brand.
- **No proprietary fonts.** Swap brand fonts for free Google Fonts equivalents (given below).
- **Adapt to the product:** keep the user's brand colour if they have one (put it in the accent slot),
  keep cedi/phone formatting, 360px mobile rules, all Mode A UX states, and contrast ≥ 4.5:1.
- Show the chosen preset (or 3–5 of them side by side) in a preview before applying it site-wide.

### Using any Refero style the user links
1. User pastes `https://styles.refero.design/style/<id>` (or a DESIGN.md). Fetch it with the web-fetch tool
   (the sandbox shell usually can't reach it). Extract colours (name, hex, role), fonts + weights + scale,
   spacing base, radius set, depth technique, signature components, do's and don'ts.
2. Map it onto the token set from Mode A (`--bg --surface --text --primary …`), swap proprietary fonts,
   add any missing states (danger/success/warning, focus) in the same spirit.
3. Apply the rules above, preview, then build. Credit "style inspired by <site> via Refero" in the notes only.

### Curated presets (best fits for fintech / reseller / SaaS dashboards)
| # | Preset | Mood | Best for |
|---|---|---|---|
| 1 | Forest Lime | friendly money, bold | wallets, transfers, data reseller home |
| 2 | Highlighter Ledger | calm finance, editorial | admin/finance dashboards, B2B |
| 3 | Midnight Lime | dark, precise, techy | dashboards, power users, dark theme |
| 4 | Graphite Hairline | minimal mono, developer-clean | SaaS, docs, API/VTU developer portals |
| 5 | Keycap Dark | dark premium, tactile | apps, launchers, premium dark mode |
| 6 | Ember Corporate | confident, high-trust | business accounts, landing pages |
| 7 | Parchment Teal | quiet, warm, readable | search, support, content-heavy pages |
| 8 | Eggshell Pill | soft luxury, editorial | premium landing pages, brand sites |

**1. Forest Lime** (inspired by Wise)
- Colours: ink `#163300` (text, nav, dark sections) · CTA lime `#9fe870` · headline `#0e0f0c` · body `#454745` ·
  surface `#e8ebe6` · canvas `#ffffff` · deep green `#054d28` · soft highlight `#e2f6d5`.
- Type: Inter 400–700 for UI; display headlines in a heavy grotesk (Inter 800/900 or Archivo Black), tight
  negative tracking (≈ −0.03em). Scale 1.2 from 18px.
- Shape: pill (9999px) for buttons/tags/nav, 10px cards/inputs, 28px large cards; 4px grid, 24px card padding.
- Signature: lime pill CTA with no shadow; dark forest sections with lime text; flag/network logos in circles.
- Don't: more than one lime element per viewport; gradients or drop shadows beyond hairlines.

**2. Highlighter Ledger** (inspired by Ramp)
- Colours: accent yellow `#e4f222` (actions, live counters, active) · ink `#0c0a08` · dark panel `#1a1919` ·
  cards `#ffffff` · canvas `#f4f2f0` · muted `#6d6c6b` · hairline `#e5e7eb` · skeleton `#d3d3d3`.
- Type: single weight 400 everywhere (Inter / Instrument Sans) — hierarchy by size only; display 64/1.0,
  heading 28/1.14, body 16/1.5, 10px uppercase captions with 0.018em tracking.
- Shape: 6px buttons/tags, 10px inputs, 12–16px cards; borders not shadows (1px `#e5e7eb` on white).
- Signature: yellow filled CTA with ink text; big live numbers; left-aligned everything.
- Don't: bold weights, extra accent colours, card shadows, centred body text, stock illustrations.

**3. Midnight Lime** (inspired by Linear)
- Colours: canvas `#08090a` · card `#0f1011` · raised `#161718` · border `#23252a` / `#383b3f` · text ramp
  `#62666d` → `#8a8f98` → `#d0d6e0` → `#ffffff` · single CTA `#e4f222` · tag colours green `#27a644`,
  violet `#6366f1`, teal `#02b8cc`.
- Type: Inter (weights 400/500/600 max, never 700), display 48–72px line-height 1.0 tracking −0.022em;
  JetBrains Mono for IDs, shortcuts, references.
- Shape: 6px buttons/inputs, 12px cards, 4px badges, pills for filters; 1px inset hairline borders, no outer
  shadows between card and canvas; 96px section gaps.
- Don't: second chromatic CTA, cards with 16px+ radius, coloured body text.

**4. Graphite Hairline** (inspired by Vercel)
- Colours: canvas `#fafafa` · cards `#ffffff` · hairline `#ebebeb` · text `#171717` / `#4d4d4d` / `#666666` ·
  success/link `#297a3a`.
- Type: Geist Sans 400–500 (headlines 450, tracking −0.05 to −0.06em at 30–64px), Geist Mono 11–12px
  UPPERCASE (+0.07em) for labels, metadata, codes, order IDs. Both are free on Google Fonts.
- Shape: 6px cards/buttons, pills for compact nav; depth only via ring shadows
  (`0 0 0 1px rgba(0,0,0,.08)`); compact 16px card padding, 96–128px section gaps.
- Signature: black filled button `#171717`, ghost hairline button, terminal-style status rows with ✓ in green.
- Don't: drop shadows, radius > 6px on rectangles, bold headlines, extra colours.

**5. Keycap Dark** (inspired by Raycast)
- Colours: canvas `#040506` · card `#07080a` · well `#111214` · muted text `#6a6b6c` / `#9c9c9d` ·
  headings `#ffffff` · neutral CTA fill `#e6e6e6` with text `#454647` · brand spark `#ff6363` (logo/badge only) ·
  hero glow blues `#63a1ff` / `#143ca3`.
- Type: Inter 400–600, hero 56px weight 400; Geist Mono for version/metadata.
- Shape: 8px buttons/inputs, 16–20px cards, 8px grid. "Keycap" card depth:
  `inset 0 1px 0 rgba(255,255,255,.05), 0 0 0 1px rgba(255,255,255,.08), inset 0 -1px 0 rgba(0,0,0,.2)`.
- Signature: floating glass pill nav (backdrop-blur, 1px `#363739` border), atmospheric gradient hero.
- Don't: coloured action buttons, light sections, accent on text.

**6. Ember Corporate** (inspired by Brex)
- Colours: action orange `#ff5900` · text `#000000` · canvas `#ffffff` · surface/inputs `#f3f3f7` ·
  body `#60646c` · caption `#6f737b` · icons `#8b8d98` · hairline `#b9bbc6` · footer `#000710` · bar `#15191e`.
- Type: Inter 400–600 with negative tracking on every size; hero headlines in an elegant serif
  (Newsreader / Fraunces 500, 48px+, line-height 1.11).
- Shape: 12px buttons/inputs/cards, 6px chips; no card shadows (surface contrast + hairlines); 48–80px gaps.
- Signature: email/phone input with attached orange button; dark multi-column footer; announcement bar.
- Don't: second accent, serif below 48px.

**7. Parchment Teal** (inspired by Perplexity)
- Colours: canvas `#faf8f5` · raised `#fdfbfa` · hairline `#d1d1cd` · muted `#92918b` · secondary `#72706b` ·
  text `#27251e` · accent teal `#016a71` (active nav, NEW badge, focus glow only).
- Type: Inter or Manrope 400/500 only; compact — 16 body, 14 UI, 12 micro labels.
- Shape: 16px cards, 12px inputs/filled buttons, 6px ghost buttons, pill chips; one tiny shadow
  `0 1px 2px rgba(0,0,0,.08)`; max content width 900px.
- Signature: search-first layout, suggestion cards with icon + title + line, teal-filled active sidebar item.
- Don't: pure white, bold weights, gradients, teal in body text.

**8. Eggshell Pill** (inspired by ElevenLabs)
- Colours: canvas `#fdfcfc` · band/feature cards `#f5f3f1` · hairline `#ebe8e4` · text `#000000` ·
  strong secondary `#44403b` · body `#777169` · faint `#a59f97` · illustration-only sparks `#0447ff` + `#ff4704`.
- Type: display in a light weight (Manrope / Inter Tight 300, 32–48px, −0.02em); body Inter 400/500 with
  +0.01em at 14–16px.
- Shape: every button/tag a pill; 20–24px cards with 32px padding, no border/shadow; 4px inputs;
  96px+ section gaps; max 1280px.
- Signature: black pill + eggshell outline pill as the only buttons; soft gradient orb as hero art.
- Don't: pure white, bold display, using the sparks on UI controls, sharp card corners.

**Pairing tip for data-reseller sites:** Forest Lime or Highlighter Ledger for the customer app (light),
Midnight Lime or Keycap Dark as the dark theme, Graphite Hairline for the admin panel.
