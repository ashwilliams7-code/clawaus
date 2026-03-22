---
name: King Claw Showcase — World-Class Upgrade Research
description: Deep research on premium product showcase techniques (Apple, Stripe, Linear, Vercel, Awwwards 2025-2026) and a prioritized TOP 10 improvement list for the King Claw index.html. Researched 2026-03-22.
type: project
---

King Claw showcase is at `/Users/sky/Documents/openclaw-au/index.html` (2423 lines).

**Current state confirmed:** Dark mode (#0a0e17 bg), glassmorphism cards, particle canvas hero, CSS Mac Mini with scroll reveal, animated counters (data-count), 3D tilt cards (data-tilt), skill marketplace section, competitor table, Australia city dots with ping animation. Fonts loaded from Google CDN (Plus Jakarta Sans + Inter). No WebGL, no custom cursor, no scroll-snap, no video, no loading screen, no typewriter, no before/after slider.

**Why:** User wants to make King Claw feel world-class — Apple/Stripe/Linear quality — to convert high-value Australian SMB clients. Research done to identify the highest-ROI techniques.

**How to apply:** Reference this when implementing King Claw upgrades. Prioritize techniques by impact vs effort.

## Source Analysis

### Apple (iPhone / Vision Pro product pages)
- Core technique: **scroll-synced canvas frame sequence** — body has 500vh+ height, canvas is `position:fixed`, scroll fraction × frame count = current frame index, drawn via `context.drawImage()` in `requestAnimationFrame`
- Secondary: CSS `@scroll-timeline` / `animation-timeline: scroll()` — native browser API, no JS needed for simple parallax
- New 2025-2026: **Liquid Glass** — `backdrop-filter: blur(2px) saturate(180%)` + inset box-shadows on `::after` pseudo + SVG displacement filter for true distortion. Pure CSS gets 80% of the way there.
- Single-file feasibility: YES for canvas frame sequence (needs image assets though). YES for CSS Liquid Glass. YES for scroll-timeline.

### Stripe
- Core technique: **WebGL mesh gradient** — canvas with vertex/fragment shaders, `uniform float u_time` drives animation via `requestAnimationFrame`, simplex noise in fragment shader maps to color gradient
- Philosophy: "Simple design, a few centrepieces, and impressive details" — 20x more time on refinement
- Diagonal motif repeated throughout: slash in hero, diagonal strips between sections
- Grid lines: subtle 4-column grid lines visible across entire page (faint border-right on cols)
- Single-file feasibility: YES — raw WebGL shader is ~80 lines JS + ~30 lines GLSL, no library needed

### Linear.app
- Color system: **LCH color space** instead of HSL (perpetual uniformity — same lightness value looks equally light regardless of hue)
- 3 CSS variables instead of 98: base, accent, contrast — rest computed
- Typography: **Inter Display** for headings (expressiveness), regular Inter for body
- Spatial alignment obsession: every icon, label, button pixel-perfect aligned — "you won't see it but you'll feel it"
- Contrast: text darker in light mode, lighter in dark mode — neutral, timeless
- Single-file feasibility: YES — all CSS variable architecture

### Vercel
- **Animated gradient text**: `background: linear-gradient(...)` + `background-clip: text` + `hue-rotate` keyframe animation
- **Mesh gradient background**: WebGL with noise (same Stripe approach) OR CSS with stacked radial-gradients + `hue-rotate` animation (CPU-heavy but works)
- The CSS-only gradient text animation is 3 lines: gradient + clip + `@keyframes` with `filter: hue-rotate(360deg)`
- Single-file feasibility: YES

### Awwwards 2025-2026 Trends
- Scroll-triggered motion is the #1 JS animation trend — IntersectionObserver + requestAnimationFrame
- 3D WebGL going mainstream — responding to mouse input
- Micro-interactions on everything — hover, click, form submit feedback
- Organic shapes / anti-grid — flowing, curved dividers instead of straight lines
- Immersive product demos in hero — actual product UI running, not screenshots
- Sound design emerging but divisive — subtle clicks on interaction
- Custom cursors — trailing ring+dot, morphing on hover

### Lottie vs Rive
- **Lottie**: JSON animation files, runtime from CDN (lottie-web ~250KB), OR inline as data URI — feasible in single file but adds weight. Best for icon micro-animations.
- **Rive**: `.riv` binary files, runtime from CDN (~40KB). Can self-host runtime JS. Better for interactive state machines (hover states, click feedback). Requires external runtime — not truly inline without downloading the JS.
- **Verdict for single-file**: Skip both. Use CSS keyframe animations for icons and SVG for anything complex. Equivalent visual quality at zero weight.

### Best SaaS Landing Pages 2026
- Story-driven hero: "before → after" arc animated in the hero section
- Immersive product previews: actual running product UI in hero, not screenshots
- Split-screen before/after sliders for problem/solution
- Modular bento grid layouts (not uniform card grids)
- Bold display typography with gradient fills
- Sticky progress indicators / reading progress bars
- Testimonials with specific ROI numbers (already done in King Claw — good)

## TOP 10 Improvements — Prioritized by Impact

### Tier 1: Maximum Impact, Feasible Inline (Do These First)

**#1 — Custom Cursor with Magnetic Trail**
- What: Hide default cursor, show a 16px ring + 6px dot that follow mouse with slight lag (CSS transition on transform). Ring morphs/scales on hover over CTAs (magnetic effect).
- Why it works: Immediate "wow" moment on page load. Signals premium craftsmanship. Every Awwwards winner uses this.
- CSS/JS: `cursor:none` on body, `mousemove` listener updating two divs with `translate3d`. ~25 lines JS, ~10 lines CSS.
- Single file: YES
- Difficulty: Easy (2/5)

**#2 — Intro Loading Screen**
- What: Full-screen #0a0e17 overlay with the 👑🦞 logo scaling up (transform: scale 0.8→1.0) + "King Claw" text fading in, then the whole overlay clips away upward (`clip-path: inset(0 0 100% 0)`) revealing the page underneath. Total ~1.2s.
- Why it works: Sets the premium tone before the visitor sees anything. Apple does this, Stripe does this, every Awwwards winner does this.
- CSS/JS: CSS keyframe for logo entrance, JS `window.addEventListener('load', ...)` triggers exit animation after 800ms.
- Single file: YES
- Difficulty: Easy (2/5)

**#3 — WebGL Animated Gradient Hero Background (replace radial-gradient mesh)**
- What: Raw WebGL canvas pinned behind hero. Fragment shader uses simplex noise + `u_time` uniform to morph between coral and teal color stops. Replaces the CSS `radial-gradient` + `animation: mesh-shift`.
- Why it works: Silk-smooth, GPU-accelerated, never re-paints. The single biggest visual upgrade.
- Code: ~80 lines JS (WebGL setup + RAF loop) + ~30 lines inline GLSL. No CDN.
- Single file: YES
- Difficulty: Medium (3/5)
- Risk: Falls back to existing CSS gradient if WebGL unavailable — add `try/catch`.

**#4 — Scroll-Synced Product Demo (Apple Style)**
- What: The Mac dashboard section becomes a 300vh sticky scroll zone. As user scrolls through those 300px-worth of viewport, the terminal lines type out one by one, the LED blinks, the dashboard slides open — all driven by `scrollY` fraction, not `IntersectionObserver`. Creates the "you're in control" feeling.
- Why it works: Apple uses this for every major product. Transforms passive reading into active exploration.
- CSS/JS: `position:sticky` on Mac scene, scroll listener maps position to animation stages.
- Single file: YES
- Difficulty: Medium (3/5)

**#5 — Typewriter / Morphing Hero Text**
- What: The hero sub-headline cycles through industry use cases: "Your 24/7 AI for real estate..." → "Your 24/7 AI for aviation..." → "Your 24/7 AI for allied health..." — smooth character-by-character deletion and retyping. Or: morphing gradient text that slowly shifts hue.
- Why it works: Instantly communicates multi-vertical value. Keeps the hero alive and engaging. Used by Framer, Vercel, Linear.
- CSS/JS: ~20 lines JS, no library.
- Single file: YES
- Difficulty: Easy (2/5)

### Tier 2: High Impact, More Work

**#6 — Bento Grid Layout for Features Section**
- What: Replace the uniform 3-column `what-grid` with an asymmetric bento grid. One card spans 2 rows, one spans 2 columns — varied sizes like Apple's feature page or Linear's homepage. Each cell has a different mini-visual (icon + animated micro-demo).
- Why it works: The current 3-column uniform grid looks generic. Bento grids signal premium editorial design. Used by every top SaaS in 2025-2026.
- CSS: CSS Grid with `grid-template-areas`, named template rows/columns.
- Single file: YES
- Difficulty: Medium (3/5)

**#7 — Before/After Comparison Slider**
- What: A drag-to-reveal slider showing "Without King Claw" (messy inbox, missed tasks) vs "With King Claw" (clean dashboard, all handled). Full-width section, mouse/touch draggable divider.
- Why it works: The most visceral way to communicate transformation. Specific to King Claw's value prop. SaaSFrame identified this as a top 2026 trend.
- CSS/JS: `mousedown/mousemove/touchmove` on a clip-path divider. ~40 lines JS, no library.
- Single file: YES (uses CSS background-color blocks or SVG illustrations instead of photos)
- Difficulty: Medium (3/5)

**#8 — Smooth Page Micro-interactions Everywhere**
- What: Every interactive element gets a state machine: buttons get a ripple on click (radial-gradient expanding from click point), nav links get an underline that slides from left, stat numbers get a glow pulse when counters finish, pricing cards get a shine sweep on hover (`background: linear-gradient(105deg, transparent 40%, rgba(255,255,255,0.1) 50%, transparent 60%)` animating `background-position`).
- Why it works: Stripe's philosophy — "20x more time on refinement." These details are what separate B-tier from A-tier.
- CSS/JS: Button ripple ~15 lines JS. Shine sweep ~5 lines CSS. Link underline ~3 lines CSS.
- Single file: YES
- Difficulty: Easy (2/5)

### Tier 3: Nice-to-Have

**#9 — Sound Design (Optional / Toggle)**
- What: Subtle 200ms click sound on CTA button interactions. Pitch shifts slightly per hover vs click. Hard OFF by default, user opts in with a 🔊 toggle in the nav.
- Why it works: Emerging premium signal in 2026. Used sparingly by top Awwwards winners.
- Implementation: Web Audio API, oscillator with ADSR envelope. No files, generated in JS. ~30 lines.
- Risk: Divisive. MUST be opt-in.
- Single file: YES
- Difficulty: Medium (3/5)

**#10 — Lenis-style Smooth Scroll (Pure JS)**
- What: Replace native browser scroll with a JS-interpolated scroll (lerp with ~0.08 ease factor). Makes every section scroll feel like butter — the characteristic "weight" you feel on premium sites.
- Why it works: The single most-commented-on feel of premium sites. Users notice it within 2 scrolls.
- Implementation: ~60 lines JS to override scroll behavior with RAF loop + lerp. Must re-implement fixed position elements.
- Risk: Breaks native scroll accessibility. Add `prefers-reduced-motion` bypass.
- Single file: YES
- Difficulty: Hard (4/5) — edge cases with fixed nav, hash links, mobile

## What's Currently Missing vs World-Class

| Missing | What World-Class Does |
|---|---|
| Default browser cursor | Custom ring+dot magnetic cursor |
| Page just appears | Branded intro loading screen |
| CSS gradient hero bg | WebGL shader gradient (GPU, silky) |
| Static scroll reveals | Scroll-synced product animation |
| Static hero subtitle | Typewriter cycling industries |
| Uniform 3-col card grid | Asymmetric bento grid |
| No transformation demo | Before/after comparison slider |
| Basic hover states | Ripple + shine micro-interactions |
| Silent | Subtle sound design (opt-in) |
| Native scroll | Smooth lerp scroll (Lenis-feel) |
