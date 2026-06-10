# CLAUDE.md

Behavioral guidelines to reduce common LLM coding mistakes. Merge with project-specific instructions as needed.

**Tradeoff:** These guidelines bias toward caution over speed. For trivial tasks, use judgment.

## 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.

---

## Project: NeverMiss — Landing Page

### What this repo is
A single-file GitHub Pages landing page for **NeverMiss**, a FIFA World Cup 2026 companion app. The app tells users when it's safe to step away from a match (bathroom break, snack, etc.) based on live match intensity.

### Files
| File | Purpose |
|------|---------|
| `index.html` | The entire site — HTML, CSS, JS, and base64 assets in one file |
| `.gitignore` | Excludes `peetactics_handoff/` (design handoff, not for production) |

### Key details
- **App URL**: `https://app.nevermiss.click` (the CTA "Open App" button links here)
- **Support email**: `support@nevermiss.click`
- **World Cup kickoff target**: `2026-06-11T23:00:00Z` — countdown auto-switches to live state at this UTC time
- **Brand split**: "Never" (green, `data-brand-prefix`) + "Miss" (white, `data-brand-suffix`)
- **Accent color**: `#00e05a` (CSS var `--green`)
- **Fonts**: Bebas Neue (display/headings), Inter (body) — loaded from Google Fonts CDN

### Google Analytics
GA is **commented out** in `<head>`. To activate: uncomment the two script tags and replace both `G-XXXXXXXXXX` placeholders with the real Measurement ID.

### Design source
`peetactics_handoff/` contains the original multi-file React/Babel prototype with the tweaks panel and full app screens. It is gitignored and should not be modified. The production `index.html` was derived from `peetactics_handoff/index.html` with React/Babel removed, assets inlined, and the CSS bug fixed.

### Hosting
GitHub Pages — root of `main` branch. No build step. Push `index.html` and it's live.

### Pending
- Add `og-image.png` (1200×630px) to the repo root. Until then, social share cards will show no image but nothing breaks.
- Custom domain `nevermiss.click` is active. Canonical link, OG tags, JSON-LD, and `sitemap.xml` all point to `https://nevermiss.click/`.
