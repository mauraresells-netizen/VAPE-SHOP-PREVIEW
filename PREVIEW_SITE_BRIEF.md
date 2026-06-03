# Preview Website Build Brief — Glasgow Cold-Lead Campaign

**Attach this file to the start of every preview-site session.** It defines what we're building, the quality bar, and the exact structure every site must follow. Read it fully before writing a single line of code.

---

## 1. The Mission

I run a cold-email campaign targeting Glasgow-area businesses that have **no website** (or only a Facebook page). For each niche I build **one stunning single-page preview website** — a finished, sellable mockup branded to that niche. I then cold-email dozens of leads in that niche with the preview, showing them exactly what their own site could look like. The preview *is* the pitch.

**One site must convince a stranger, in 5 seconds, that it was custom-built by a premium agency for their specific trade.** If it looks templated, generic, or "AI-made", the email gets deleted. This is the entire game.

### Niches still to build (priority order — by count of no-website leads)
1. **Bakery** — 26 leads
2. **Butcher** — 21 leads
3. **Florist** — 16 leads
4. **Takeaway** — 10 leads
5. **Bike Shop** — 9 leads
6. **Ice Cream Shop** — 7 leads
7. **Gift Shop** — 7 leads
8. **Vape Shop** — 6 leads

(Already done: Restaurant, Cafe, Pet Shop, Barber, Hairdresser, Car.)

**One niche per session.** Do not attempt multiple niches in a single session — quality degrades and sites start bleeding into each other.

---

## 2. Non-Negotiable Quality Bar

> **Production-grade. Editorial. Bespoke. Zero AI slop.**

- **No generic AI aesthetic.** No purple-blue gradients, no default Inter/Roboto/Arial, no centered-everything hero with a lonely button, no emoji-as-icons, no Lorem Ipsum. Every site must feel like it came from a real boutique studio.
- **Use the installed skills, and use them hard.** This is mandatory, not optional:
  - **`frontend-design`** / **`impeccable`** — drive the overall design quality, visual hierarchy, polish, and anti-slop direction.
  - **`ui-ux-pro-max`** — pull niche-appropriate palettes, font pairings, layout systems, and the 99 UX guidelines.
  - **`ui-styling`** / **`design-system`** — token architecture (CSS variables for every colour/font/space/timing), spacing & type scales.
  - **`design`** / **`banner-design`** — only if a generated visual asset genuinely elevates the result.
  - Invoke them deliberately. Don't just freestyle — lean on the skill intelligence for colour theory, font pairing, and UX correctness.
- **Every detail considered.** Real local pricing, real Glasgow geography (streets, subway stops, landmarks), authentic Glaswegian testimonial voice, plausible opening hours, a believable founding year and backstory.
- **Code quality:** single self-contained HTML file, all CSS/JS embedded, vanilla JS only (zero frameworks/libraries), clean and fully commented, every section labelled in both HTML and CSS, fully mobile-responsive.
- **Accessibility & performance** still matter: semantic HTML, keyboard-navigable, `prefers-reduced-motion` respected, GPU-accelerated transforms, no jank.

If a section feels flat, push it further. "Good enough" is a deleted email.

---

## 3. The Splash-Image Rule (applies to EVERY site)

Each site **must open on a single full-screen image that I will supply** in the project folder. This is the first page — nothing else is visible.

- The splash is a full-screen layer: `position: fixed; z-index: 9999; overflow: hidden`, sitting above everything.
- The image is set via a single `background-image` property with a **clearly commented swap point** for the photo I'll drop in. Use a niche-appropriate gradient as the placeholder until then.
- The **main site is fully rendered in the DOM beneath the splash but hidden and inert** — `visibility: hidden; pointer-events: none` — plus a scroll lock, until the transition completes.
- Centred on the image: the business name in large airy heading type, a short descriptor beneath, and **a single refined CTA button with niche-relevant text** (e.g. "Enter", "Step Inside", "View the Collection", "See the Menu") that the user clicks to reach the main page.
- On click: a cinematic exit (curtain wipe / iris bloom / fade) reveals the already-rendered site seamlessly.
- After the exit animation completes, **the splash element is removed from the DOM entirely** — it cannot be scrolled back to, tabbed to, or re-accessed.
- Main site `visibility`, `pointer-events`, and scroll lock are restored only **after** the splash transition fully completes.

> Always check the project folder for the supplied splash image first. If it's there, wire it into the commented swap point. If not, use the placeholder gradient and leave the swap point obvious.

---

## 4. The Template Structure

The nail-salon prompt below is the **gold-standard reference for structure, depth, and the animation system**. Every site reuses this skeleton. **Only the niche-specific layer changes** — keep the architecture, keep the richness.

### What changes per niche
- **Palette** — derive a bespoke, niche-appropriate scheme (warm artisan tones for a bakery, fresh botanical greens for a florist, bold appetite-driving colour for a takeaway, etc.). Never reuse the salon's blush/rose unless it genuinely fits.
- **Typography** — a fitting Google Fonts pairing for the niche (always one display/character face + one clean body face; never Arial/Roboto/Inter/system defaults).
- **Voice & copy** — headlines, taglines, About backstory, Glasgow rooting, all rewritten for the trade.
- **Sections** — adapt to what the niche needs: a bakery has a *product/menu* section not "Services"; a florist has *bouquet collections* + occasions; a takeaway has a *menu* + order/delivery CTA; a bike shop has *services + product ranges*; etc.
- **Pricing / products** — realistic UK prices and real-sounding product names for that trade.
- **Imagery** — placeholder gradients + commented swap points themed to the niche.

### What stays the same (the essentials — carry ALL of these across)
- The **splash-image entry page** behaviour (Section 3 above) — every time.
- **CSS custom properties** for every colour, font, spacing value, and timing.
- A **fixed minimal top nav** that's invisible/inert during splash and fades in after reveal; scroll-triggered backdrop blur + hairline border; centre-out underline hover; mobile hamburger with a full-height slide-in panel and staggered links.
- A **hero** with split/staggered headline reveals, a rooted Glasgow tagline, two CTAs, a subtle textured/gradient background, and 2–3 slow-drifting decorative background shapes.
- A **core offering section** (services/menu/products) as an animated card grid with hover lift + shadow bloom.
- An **About / Our Story** two-column section with an image reveal and **count-up stats** on scroll.
- A **full-width spotlight / feature** section with parallax and an inset frame.
- A **gallery** — asymmetric editorial masonry, staggered reveals, hover overlay with a "View" label.
- A **testimonials** section — a deliberate dark/rich palette moment, authentically Glaswegian voices, auto-advancing carousel with dot nav, oversized decorative quote mark.
- A **booking / contact / enquiry** section with **floating-label** form fields, animated focus borders, and a ripple-effect submit button, plus real Glasgow address, 0141 phone, and opening hours.
- A **Find Us** section with a styled map placeholder, CSS-drawn location pin, and a Glasgow transport/landmark note.
- A **footer** — rich palette, centred wordmark, tagline, social links with letter-spacing hover, three columns (hours / address / quick links), top border rule, spaced-caps copyright.

### The full site-wide animation system (apply to EVERY site)
- **Scroll reveals** via Intersection Observer: `opacity 0→1` + `translateY 30px→0` over ~0.8s with `cubic-bezier(0.22, 1, 0.36, 1)`; children staggered ~0.12s.
- **Headline reveals**: word-by-word `clip-path` rises from `translateY(100%)`, ~0.7s/word, staggered ~0.09s.
- **Hover states**: colour 0.3s ease, transforms 0.45s `cubic-bezier(0.25, 0.46, 0.45, 0.94)` — consistently soft.
- **Sliding underlines**: nav `::after` `scaleX` from centre.
- **Floating background shapes**: slow `20s ease-in-out infinite alternate` drift.
- **Parallax** on the spotlight section via passive scroll listener, `will-change: transform`.
- **Custom cursor**: a small filled dot following the mouse with lerp inside a `requestAnimationFrame` loop; scales/morphs to an outline ring over links/buttons. (Disable on touch devices.)
- **Smooth scroll** on `html` + eased JS anchor handler.
- **Grain overlay**: fixed SVG-noise pseudo-element at 3–4% opacity over the whole page for tactile warmth.
- **Loading sequence**: after splash exits, the hero plays a coordinated ~2s entrance (background bloom → staggered headline → tagline → buttons).
- **Ripple effect**: soft radial ripple from the click point on button mousedown (pure CSS/JS).
- **Card hover**: `translateY(-6px)` lift + soft shadow bloom + accent border transition.

> Tune every animation's *feel* to the niche (a butcher should feel crafted and solid; a florist soft and botanical; a takeaway energetic and appetising) — but the *system* and its polish level stay constant.

---

## 5. Technical Requirements (every build)
- Single HTML file, all CSS and JS embedded.
- Fully mobile responsive — hamburger nav, grids collapse to one column, touch-friendly tap targets.
- Google Fonts via `<link>` (niche-appropriate pairing).
- Intersection Observer for all scroll-triggered animation.
- **Vanilla JS only — zero frameworks, zero libraries.**
- `requestAnimationFrame` loop for the custom cursor.
- Splash: `position: fixed; z-index: 9999`, removed from DOM after exit.
- Main site: `visibility: hidden; pointer-events: none` until splash transition completes.
- All image placeholders via `background-image` with clearly commented swap points.
- CSS custom properties for every colour, font, spacing, and timing value.
- Clean, well-structured, commented code — every section labelled in HTML and CSS.

---

## 6. Reference Prompt — The Nail Salon (gold standard)

> The prompt below is the proven reference. Mirror its **depth, structure, and animation system** for each new niche, swapping the niche-specific layer (palette, fonts, copy, sections, pricing, imagery) as described in Section 4.

```
Build a single-page luxury nail salon website called "Nail Salon" using HTML, CSS, and JavaScript in one file. The salon is Glasgow-based, feminine, romantic, and quietly luxurious — think a boutique Parisian nail bar that has found its home in the heart of Glasgow. Every detail should feel delicate, considered, and indulgent without ever feeling overdone. The design language is soft, editorial, and warm — like flipping through a high-end beauty magazine.

COLOUR SCHEME & TYPOGRAPHY
Palette: Soft blush rose #f2d4d7, deep rose #8b3a4a, champagne gold #d4af6a, warm white #fdf8f5, and a near-black #1a0a0d for text and dark sections. Use CSS variables throughout for every colour, font, spacing, and timing reference. Typography: Pair an elegant romantic serif (e.g. Cormorant Garamond or Playfair Display) for headings with a light delicate sans-serif (e.g. Jost or Raleway Light) for body text. Never use Arial, Roboto, Inter, or default system fonts. Letter-spacing on headings should be generous — airy and editorial.

PAGE STRUCTURE
1. Splash / Entry Page — CRITICAL: On load, only a single full-screen image, nothing else. Splash layer z-index: 9999, position: fixed, overflow: hidden. Main site rendered beneath but visibility: hidden + pointer-events: none until transition completes. Image via background-image with a commented swap point (blush-to-rose gradient placeholder). Dark vignette overlay. Centred: salon name in large airy serif (warm white, 1.5s fade), descriptor in champagne gold (fades at 2s), and a refined ghost CTA button with a breathing gold glow. On click: cinematic exit (curtain wipe / iris bloom / fade). Splash removed from DOM after exit; main site visibility/pointer-events/scroll restored only after transition completes.
2. Navigation — Fixed minimal top nav, inert during splash, fades in after reveal. Logo left, links right (Services, About, Gallery, Testimonials, Book Now). Scroll: semi-transparent warm white + backdrop-filter blur(12px) + hairline blush border. Hover: centre-out champagne gold underline. Mobile: deep rose hamburger, full-height blush slide-in panel with staggered links.
3. Hero — Split romantic headline, Glasgow-rooted tagline, two CTAs (deep rose filled + champagne ghost). Warm white background with subtle blush gradient bloom + fine grain. Staggered clip-path word reveals. 2–3 drifting blush background shapes.
4. Services — "— Our Services —" with thin gold rules. Card grid (3col/1col). Each: serif deep rose name, near-black description, champagne gold price, blush bg, deep rose top border. Staggered fade-up; hover lift -6px + blush shadow + gold border. Realistic UK nail pricing (Classic Manicure £28, Gel £38, Luxury £48, Pedicures £32/£42/£55, Extensions £55/£38, Gel Removal £15, Nail Art from £3/£25, Paraffin £18, Hand & Arm Massage £12, Bridal £95, Bridal Trial £65, Repair £8).
5. About — Two columns: framed blush image left, editorial text right. "Crafted in Glasgow. Inspired by Art." Backstory (Glasgow roots, artist trained in London/Paris, premium products, self-care ethos). Stat row (Est. 2016 / Premium Products Only / Glasgow's Favourite Studio) with count-up + clip-path image reveal.
6. Signature Look Spotlight — Full-width, large centred image, slow parallax, blush bg. Overlaid featured style name in deep rose serif ("The Glasgow Rose") + poetic gold italic description. Inset gold frame. "Book This Look" ghost CTA.
7. Gallery — Asymmetric editorial masonry, 6–8 blush-to-rose gradient cells with gold accents. Staggered fade-up; hover scale 1.04 + rose overlay 35% + "View" label. Blush section bg.
8. Testimonials — Deep rose dark section, warm white text. 4–5 authentically Glaswegian quotes (warm white italic serif, champagne gold name + stars). Crossfade carousel with horizontal drift, oversized faded gold quote mark, auto-advance 5s, pause on hover, gold dot nav.
9. Booking / Contact — Warm white. "Book Your Appointment" + italic "Treat yourself. You deserve it." Fields: Name, Email, Phone, Service dropdown, Date, Time, Requests — floating labels, gold expanding focus border. Deep rose submit with blush ripple. Glasgow address, 0141 phone, hours (Tues–Sat 10–7, Sun 11–5, closed Mon). Bridal/group note.
10. Find Us — Blush section, styled map placeholder with CSS gold location pin. Glasgow address ("14 Princes Square, Glasgow, G1"), transport note ("2 minutes from Buchanan Street subway. Steps from the Style Mile.").
11. Footer — Deep rose, centred warm white serif wordmark, gold italic tagline, social links (Instagram/Pinterest/TikTok) with letter-spacing hover, three columns (Hours/Address/Quick Links), gold top border, spaced warm white caps copyright.

ANIMATION SYSTEM — apply throughout: Intersection Observer scroll reveals (opacity + translateY 30px, 0.8s cubic-bezier(0.22,1,0.36,1), 0.12s stagger). Word-by-word clip-path headline reveals (0.7s/word, 0.09s stagger). Hover: colour 0.3s ease / transforms 0.45s cubic-bezier(0.25,0.46,0.45,0.94). scaleX nav underlines. Drifting blush shapes (20s ease-in-out infinite alternate). Parallax spotlight (60% rate, will-change). Custom cursor (deep rose dot, lerp in rAF, morphs to gold ring on hover). Smooth scroll. Permanent SVG grain overlay 3–4%. Coordinated ~2s hero entrance after splash. Button ripple from click point. Service card hover lift.

TECHNICAL: Single HTML file, all CSS/JS embedded. Fully mobile responsive. Google Fonts (Cormorant Garamond + Raleway). Intersection Observer. Vanilla JS only — zero libraries. rAF cursor loop. Splash position:fixed z-index:9999, removed after exit. Main site visibility:hidden + pointer-events:none until done. Image placeholders via background-image with commented swap points. CSS custom properties for every colour/font/spacing/timing. Clean commented code, every section labelled.
```

---

## 7. Session Kick-off Checklist
When starting a niche session, do this:
1. Confirm the niche and check the project folder for the supplied **splash image**.
2. Invoke the design skills (`frontend-design` / `impeccable` / `ui-ux-pro-max`) to lock a **bespoke palette + font pairing + layout direction** for the niche — not a recolour of the salon.
3. Adapt section names/content to what the niche actually needs (menu vs services vs collections).
4. Write real Glasgow detail: address, 0141 number, hours, landmarks, backstory, authentic testimonials, realistic UK pricing/products.
5. Build the full splash → main architecture and the complete animation system.
6. Self-review against the Quality Bar (Section 2) before declaring done — if any section feels flat or templated, push it further.

---

## 8. Deploy — Push to GitHub & Go Live

Once the site is built and reviewed, publish it as a live GitHub Pages repo, matching the existing previews (e.g. `https://mauraresells-netizen.github.io/RESTAURANT-PREVIEW/`).

### Conventions
- **GitHub account:** `mauraresells-netizen`
- **Repo name:** the niche in caps with `-PREVIEW`, e.g. `BAKERY-PREVIEW`, `FLORIST-PREVIEW`, `VAPE-SHOP-PREVIEW`.
- **The site file MUST be named `index.html`** (GitHub Pages serves `index.html` at the repo root). If the build produced a differently-named file, rename it to `index.html` before pushing.
- **Splash image:** make sure the supplied image is in the repo (e.g. `splash.jpg`) and the `background-image` swap point points to it with a *relative* path (`url('splash.jpg')`) so it loads on the live site.
- **Live URL after deploy:** `https://mauraresells-netizen.github.io/<REPO-NAME>/`

### Steps (run from inside the niche folder)
```bash
# 1. Confirm gh is authenticated (one-time): gh auth status  → if not: gh auth login
# 2. Initialise and commit
git init
git add .
git commit -m "Add <niche> preview site"
git branch -M main

# 3. Create the repo on GitHub and push (public so Pages works on free tier)
gh repo create <REPO-NAME> --public --source=. --remote=origin --push

# 4. Enable GitHub Pages on the main branch root
gh api -X POST repos/mauraresells-netizen/<REPO-NAME>/pages \
  -f "source[branch]=main" -f "source[path]=/" 2>/dev/null \
  || gh api -X PUT repos/mauraresells-netizen/<REPO-NAME>/pages \
       -f "source[branch]=main" -f "source[path]=/"
```

### Verify
- Pages can take 30–60s to build on first deploy. Then open `https://mauraresells-netizen.github.io/<REPO-NAME>/` and confirm:
  - The splash image loads (not a broken image / placeholder gradient).
  - The Enter button reveals the main site cleanly.
  - Fonts, animations, and the custom cursor all work on the live URL.
- If the image 404s, it's almost always a path/case mismatch — GitHub Pages is case-sensitive, so `Splash.JPG` ≠ `splash.jpg`.

> Don't push until the splash image is actually in the folder and wired in — a live preview with a broken hero image is worse than no preview. Confirm the image is present first.
