---
name: NeverMiss
description: The FIFA World Cup 2026 companion that tells fans exactly when it's safe to step away.
colors:
  match-dark: "#080808"
  dugout-grey: "#111111"
  goal-green: "#00e05a"
  goal-green-dim: "#00e05a1f"
  ink-white: "#ffffff"
  border-subtle: "#ffffff12"
typography:
  display:
    fontFamily: "Bebas Neue, sans-serif"
    fontSize: "clamp(64px, 12vw, 140px)"
    fontWeight: 400
    lineHeight: 0.92
    letterSpacing: "0.02em"
  headline:
    fontFamily: "Bebas Neue, sans-serif"
    fontSize: "clamp(32px, 5vw, 52px)"
    fontWeight: 400
    lineHeight: 1.1
    letterSpacing: "0.04em"
  title:
    fontFamily: "Bebas Neue, sans-serif"
    fontSize: "20px"
    fontWeight: 400
    letterSpacing: "0.06em"
  body:
    fontFamily: "Inter, sans-serif"
    fontSize: "clamp(17px, 2.5vw, 21px)"
    fontWeight: 300
    lineHeight: 1.65
  label:
    fontFamily: "Inter, sans-serif"
    fontSize: "10px"
    fontWeight: 500
    letterSpacing: "0.22em"
rounded:
  sm: "4px"
  md: "6px"
  pill: "100px"
components:
  cta-button:
    backgroundColor: "{colors.goal-green}"
    textColor: "#000000"
    rounded: "{rounded.sm}"
    padding: "16px 40px"
  cta-button-hover:
    backgroundColor: "{colors.goal-green}"
    textColor: "#000000"
    rounded: "{rounded.sm}"
    padding: "16px 40px"
  countdown-block:
    backgroundColor: "{colors.dugout-grey}"
    rounded: "{rounded.md}"
    padding: "14px 18px"
  live-badge:
    backgroundColor: "{colors.goal-green-dim}"
    textColor: "{colors.goal-green}"
    rounded: "{rounded.pill}"
    padding: "8px 20px"
---

# Design System: NeverMiss

## 1. Overview

**Creative North Star: "The Fan's Trusted Mate"**

NeverMiss is built for the fan who's half-watching from the couch and half-managing real life. The visual system behaves like a mate who's already thought of everything: no fuss, no fanfare, just a quick heads-up and you're sorted. Every design decision reflects that relationship — direct, confident, self-aware enough to have a sense of humor about bathroom breaks.

The palette is stadium-night dark, not because dark is aesthetically interesting, but because fans watch in dim rooms with phones at 40% brightness. The single accent — a vivid, alert-signal green — earns its impact by appearing sparingly. Typography commits fully to the display-body split: Bebas Neue carries event energy; Inter handles the human part. The page knows what it is and gets out of the way.

This system explicitly rejects three aesthetic families the user named: the over-produced, sponsor-heavy corporate sports brand (clean surface, zero soul); the SaaS landing-page pattern (hero metrics, gradient text, "10× your match experience" copy); and hypebeast streetwear maximalism (all-caps stacking, aggressive decoration, nothing left to breathe). NeverMiss is none of those. It's the app your mate built because he was tired of missing goals.

**Key Characteristics:**
- Near-black body, one sharp green accent, white ink — three ingredients, no filler
- Bebas Neue at display scale: event-energy type that reads at arm's length
- Inter Light for body: readable, low fatigue, no-fuss
- Sparse decoration: radial green glow on the hero, 1px borders on blocks, nothing else
- Direct copy: irreverent, specific, clearly fan-authored

## 2. Colors: The Three-Ingredient Palette

One dark field, one alert signal, one clean ink. Rarity is the point — Goal Green means something because it appears on almost nothing.

### Primary
- **Goal Green** (`#00e05a`): The single accent. CTA button, brand type prefix ("Never"), pillar titles, live badge, pulsing live dot. Appears on ≤15% of any surface. Never decorative.
- **Goal Green Dim** (`#00e05a1f`): Background tint only — hero radial glow, live badge fill, countdown block ambient shadow. Never used for text.

### Neutral
- **Match Dark** (`#080808`): Body background. The entire page sits on this. Not pure black; fractionally lifted so Dugout Grey reads as a distinct layer.
- **Dugout Grey** (`#111111`): Surface color for countdown blocks and inset containers. The only tonal layer in the system.
- **Ink White** (`#ffffff`): Primary text. All body copy, headings, UI labels. 21:1 contrast on Match Dark.
- **Border Subtle** (`#ffffff12` / `rgba(255,255,255,0.07)`): Pillar grid dividers, countdown block borders. Near-invisible in direct light; intentional — it defines without asserting.

### Named Rules
**The One Signal Rule.** Goal Green is the go-signal. It appears only where the interface means "safe" or "action": the CTA, the live indicator, brand type. Using it decoratively — icon fills, gradient endpoints, arbitrary text highlights — is forbidden. Rarity earns meaning.

**The Two-Layer Rule.** Exactly two surface depths: Match Dark (body) and Dugout Grey (inset). No new surfaces, no tonal expansion. If a new container is needed, it uses Dugout Grey. There is no third layer.

## 3. Typography

**Display Font:** Bebas Neue (condensed gothic sans, loaded via Google Fonts CDN)
**Body Font:** Inter (humanist sans, weights 300 / 400 / 500, Google Fonts CDN)

**Character:** A deliberate contrast-axis pairing with no visual overlap. Bebas Neue reads like stadium signage and match commentary — wide-tracking condensed caps, zero ambiguity at scale. Inter reads like a text message from a friend — calm, modern, legible at small sizes with no visual fatigue. They share no DNA; the pair works because of that distance.

### Hierarchy
- **Display** (Bebas Neue 400, `clamp(64px, 12vw, 140px)`, line-height 0.92, tracking 0.02em): Hero headline only. "Never Miss a Goal." The match itself in type. One instance per page.
- **Headline** (Bebas Neue 400, `clamp(32px, 5vw, 52px)`, tracking 0.04em): Section headings. "Your match companion."
- **Title** (Bebas Neue 400, `20px`, tracking 0.06em, Goal Green): Component labels — pillar titles, live state heading variant. Small Bebas Neue always in Goal Green.
- **Body** (Inter 300, `clamp(17px, 2.5vw, 21px)`, line-height 1.65): Primary prose — hero sub, pillar body. Max line length 65–75ch enforced on containers.
- **Label** (Inter 500, `10px`, tracking 0.22em, uppercase): Countdown labels ("World Cup kicks off in"), unit text ("Days"), badge text ("Live Now"). Highest tracking in the system. Always uppercase.

### Named Rules
**The Voice-Split Rule.** Bebas Neue speaks for the event; Inter speaks for the human. Bebas Neue never runs at body scale (below 18px). Inter never runs at display scale. The two voices stay categorically distinct.

## 4. Elevation

This system is flat by default. There are no structural box-shadows. Depth is implied through two mechanisms only:

1. **Tonal layering**: Match Dark (body) beneath Dugout Grey (surfaces). One step, no blur.
2. **Goal Glow**: A faint `rgba(0,224,90,0.08)` ambient glow on countdown blocks and a `radial-gradient` green bloom on the hero background. These signal "alive" — not "lifted."

### Shadow Vocabulary
- **Goal Glow** (`box-shadow: 0 0 24px rgba(0,224,90,0.08)`): Applied via `::after` on countdown number blocks. Ambient; not reactive. Does not change on hover.
- **Hero Ambient** (`radial-gradient(ellipse 60% 50% at 50% 40%, rgba(0,224,90,0.07) 0%, transparent 70%)`): Background bloom behind hero content. Creates center focus without card structure.

### Named Rules
**The Flat-By-Default Rule.** Surfaces are flat at rest. The green glow is ambient, not a state indicator. The CTA button hovers via `opacity` and `translateY` — no shadow appears on interaction. Structural shadows are prohibited.

## 5. Components

### CTA Button
*The most important element on the page. Earns attention by contrast, not decoration.*
- **Shape:** Squared (4px radius — lowest in the system). Signals "serious action", not "playful tap."
- **Primary:** Goal Green (`#00e05a`) fill, black (`#000`) text, `padding: 16px 40px`, Inter 600, 14px, uppercase, tracking 0.06em. Minimum 44px touch target.
- **Hover:** `opacity: 0.88`, `transform: translateY(-1px)`, `transition: 0.2s`. No color change, no shadow. Opacity signals affordance.
- **Active:** `opacity: 1`, `transform: translateY(0)`. Snap-back, no elastic.

### Countdown Blocks
*A status display. Not a hero element — the score is the page.*
- **Background:** Dugout Grey (`#111111`). The only inset surface in the system.
- **Border:** Border Subtle (`rgba(255,255,255,0.07)`), 1px. Defines the block without asserting it.
- **Radius:** 6px (md). Slightly more than the CTA; softer read for a static display.
- **Number:** Bebas Neue, `clamp(44px, 8vw, 72px)`, Ink White, centered, `padding: 14px 18px`.
- **Unit label:** Inter 500, 9px, uppercase, tracking 0.18em, Ink White.
- **Separator:** Bebas Neue, `clamp(40px, 7vw, 64px)`, Ink White at `opacity: 0.4`. Recedes without disappearing.
- **Ambient glow:** Goal Glow on `::after` pseudo. Subtle; ambient; not interactive.

### Pillars Grid
*Three feature statements, not three cards. The gap-as-border pattern is intentional.*
- **Structure:** CSS Grid, `gap: 1px`, `background: var(--border-subtle)` on the grid creates dividers. Cells fill with Match Dark — the border IS the gap color showing through.
- **Radius:** 6px on the outer grid container, `overflow: hidden`. Cells have no individual radius.
- **Padding:** `36px 28px` per cell.
- **Title:** Bebas Neue 20px, Goal Green, tracking 0.06em.
- **Body:** Inter 300, 16px, Ink White, line-height 1.6.
- **Responsive:** 1 column → 3 columns at 860px+. No intermediate breakpoint.

### Navigation
*Fixed. Identity only. Invisible structure.*
- **Position:** Fixed top, full width, `z-index: 100`.
- **Background:** `linear-gradient(to bottom, rgba(8,8,8,0.95) 0%, transparent)`. Fades out — doesn't hard-cut the hero.
- **Logo:** Bebas Neue 28px, tracking 0.06em. "Never" in Goal Green, "Miss" in Ink White. The brand split is the logo; no separate mark.
- **No navigation links.** Nav is identity-only. Single CTA below fold is the sole action.

### Live Badge
*Replaces the countdown when the World Cup starts.*
- **Shape:** Full pill (`border-radius: 100px`), `padding: 8px 20px`.
- **Fill:** Goal Green Dim (`rgba(0,224,90,0.1)`). Border: `1px solid rgba(0,224,90,0.25)`.
- **Text:** Inter 600, 11px, uppercase, tracking 0.18em, Goal Green.
- **Dot:** 7px circle, Goal Green, `animation: pulse 1.6s ease-in-out infinite`. The sole persistent animation in the system.
- **Reduced motion:** `@media (prefers-reduced-motion: reduce)` — dot static at full opacity; no pulse.

## 6. Do's and Don'ts

### Do:
- **Do** run body text at full Ink White (`#ffffff`) on Match Dark. 21:1 contrast; no qualification needed.
- **Do** keep Goal Green on ≤15% of any surface. Its rarity is the brand — the CTA button is green *because* nothing else is.
- **Do** use Bebas Neue for event-scale headings only (≥18px, display/headline/title roles). Inter for everything else.
- **Do** apply the Two-Layer Rule: Match Dark below, Dugout Grey for insets, nothing else.
- **Do** use the gap-as-border pattern for the pillars grid. Add no card borders, individual backgrounds, or shadows to cells.
- **Do** write copy that's specific and self-aware. "Dropping a deuce" is on-brand. "Step away at a safe moment" is not.
- **Do** add `@media (prefers-reduced-motion: reduce)` for all animations. The live dot pulse and any scroll reveals need a static fallback.

### Don't:
- **Don't** reproduce FIFA official / corporate aesthetics: sponsor-blue palettes, trophy renders, "The Beautiful Game" language, dense stats tabular UI.
- **Don't** use SaaS landing-page patterns: hero metric templates (big number + stat + gradient accent), `background-clip: text` gradient text, numbered section eyebrows (01 / 02 / 03 scaffolding), cream or parchment body backgrounds.
- **Don't** use hypebeast streetwear patterns: all-caps stacking on every element, aggressive drop-shadow accumulation, `border-left` stripe accents on cards or lists.
- **Don't** add a third surface depth. No new tinted containers, no modal-grey, no semi-transparent panels that aren't already in the system.
- **Don't** use Goal Green for decoration — icon fills, arbitrary highlights, gradient endpoints. If it's not signaling "go" or "brand identity", it's not Goal Green's job.
- **Don't** use glassmorphism or backdrop-filter decoratively. The hero radial glow is ambient gradient, not a glass card.
- **Don't** pair Inter with itself at different weights to create a heading — that's the display voice's job. Two weights of Inter is a subtitle, not a headline.
