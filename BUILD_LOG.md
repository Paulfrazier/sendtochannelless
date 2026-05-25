# Build Log — sendtochannelless

## 2026-05-25 — Re-skin to "Playful Arcade" design system

**Prompt:** "Looks great, push" — rolling out the new Fairpoint design system.

**Problem:** Clean but generic design; quiz engine was duplicated per-site code.

**Solution:** Converted to the `fairpoint-kit` data-driven template. Content moved to `spec.json` (40 scenarios, choices `also`/`thread`/`new`), rendered into `index.html`'s `#site-config` block via `fairpoint-kit/render.py`. New look: Space Grotesk, neobrutalist cards, scoring HUD with 🔥combo + segmented progress, +points popups, count-up summary with a grade, dependency-free confetti at ≥70%. Scenarios and correctness unchanged. This spec is also the kit's regression fixture (`fairpoint-kit/examples/send-to-channel-less.json`).

**Changed files:** `index.html` (regenerated from template), `spec.json` (new)

## 2026-05-21 — Initial scaffold

**Prompt:** "go" — Paul greenlit scaffolding the second Fairpoint site after deciding on the name `sendtochannelless`. Single decision turn after a multi-turn naming workshop in the chat.

**What landed:**
- New folder `/Users/pfrazier/Documents/claude/send-to-channel-less/`
- Structural clone of `slack-mentions-quiz` (the dontuseathere site) — same single-file static HTML, same quiz engine, identical CSS palette.
- 40 new scenarios drafted from scratch on the "Also send to #channel" overuse lesson. Distribution: 28 `thread` (most replies should stay in thread), 6 `also` (legit cases: incident resolution, decisions, scope expansion), 6 `new` (urge to also-send means you've got a new topic).
- Three-button schema: `also` / `thread` / `new`. The `also` button gets the existing yellow accent (mirrors `@here`'s "tempting but usually wrong" treatment in dontuseathere).
- Footer adds "More from Fairpoint →" cross-promo linking to fairpoint.website.
- Source/CONTRIBUTING links point to the new repo `Paulfrazier/sendtochannelless`.

**Key decisions:**
- **Identical CSS palette to dontuseathere** (Slack purple + yellow). Makes the Fairpoint family read as a coherent set.
- **`also` keyword in the schema** is a coincidence with "Also send" — kept it because it's the verb in the UI text.
- **Quiz framing is "do it less," not "never do it"** — matches the URL name "send to channel… less." The 6 `also`-correct scenarios are deliberately included to make the lesson honest.
- **No favicon yet, no analytics, no PWA.** Match the dontuseathere scope exactly.

**Files:**
- `index.html` (single-file app, ~600 lines including 40 scenarios)
- `CONTRIBUTING.md` (template + style guide for new scenarios)
- `.gitignore` (`.vercel`, `.DS_Store`)
- `BUILD_LOG.md` (this file)

**Pending:**
- GitHub repo creation + initial push
- Vercel project link + first deploy
- Custom domain `sendtochannelless.fairpoint.website` (Paul adds via Vercel dashboard + DNS at registrar)
