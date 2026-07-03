# Gimmie Build Plan — one phase per Claude Code session

Work one phase at a time. Start each session by telling Claude Code which phase you're on. Commit at the end of every phase. If a phase drifts, stop and re-anchor: "Re-read CLAUDE.md and the Phase N spec before continuing."

---

## Phase 0 — Scaffold (30 min)
Prompt: "Read CLAUDE.md. Scaffold the Next.js + TypeScript + Tailwind project. Set up the design tokens as CSS variables, import Unbounded and Hanken Grotesk, and build components/PhoneFrame.tsx: a centered 390px frame with soft shadow that wraps every page. Create empty stubs for lib/api.ts, lib/scoring.ts, types/profile.ts, data/questions.ts, data/products.json. Render the splash screen from the previous prototype inside the frame as the home page."

Done when: splash screen renders in the phone frame with correct fonts, colors, and sparkles.

## Phase 1 — Component library (1 session)
Prompt: "Read CLAUDE.md. Build the shared component library: Button (yellow/pink/purple variants, disabled state, press animation), SelectTile (single and multi modes with purple border + yellow ✦ badge selection state), WordChip, ProgressBar (animated, n of 13), TextArea, SparkleBurst (radiating ✦ animation), and BrandPicker (type-ahead against a hardcoded brand list, removable pill tags, max 5). Build a /kitchen-sink page that shows every component in every state so I can review them all at once."

Done when: /kitchen-sink looks right and every state works.

## Phase 2 — Quiz engine (1 to 2 sessions)
Prompt: "Read CLAUDE.md. Implement the full onboarding quiz as config-driven screens. Populate data/questions.ts with all 13 questions from the spec (copy below). Build the generic QuizScreen renderer, wire answers into UserProfile context, and implement the weighted scoring engine in lib/scoring.ts with a points map on every answer option. Structure the flow as 8 required questions, then an interstitial screen ('Nice. Want to level up your profile?') with a 'Finish my profile' primary CTA and a 'Skip to my style' secondary option, then the remaining 5. Include the 3-tap color season screen last."

Bring your existing question copy from the prototype prompt into this session. Assign points maps yourself or ask Claude Code to propose them and review its table before it writes code. Review the points table carefully: this IS the product.

Done when: you can complete the quiz three different ways and get three different, sensible archetypes.

## Phase 3 — Result screen + the AI moment (1 session)
Prompt: "Read CLAUDE.md. Build the results screen: sparkle burst on load, archetype name + tagline, three style notes derived from actual answers, color season card framed as a starting palette with a 'Not quite right? Adjust anytime' link. Then add the AI touch: send the Q3 free-text answer plus the computed profile to the Anthropic API and ask for one warm personalized sentence to display under the archetype (e.g. referencing their wedding, new job, closet fatigue). Handle the empty case gracefully."

Done when: typing "I have a wedding in September and nothing fits" in Q3 produces a result screen that mentions it.

## Phase 4 — Discovery feed with mock data (1 session)
Prompt: "Read CLAUDE.md. Generate data/products.json: 40 realistic products (dresses, tops, bags, shoes, jewelry) with brand, name, price, colors, vibe tags matching the 8 archetypes, and CSS-gradient placeholder images. Build the feed: masonry grid, filter chips (Vibe / Size / Price / Brand), Trending Now horizontal strip, ✦ save buttons with a save animation, bottom tab bar (Home, Search, Saved, Profile). Feed sorts by match to the user's archetype and color season."

Done when: two different quiz outcomes produce visibly different feed orderings.

## Phase 5 — Collections (1 session)
Boards grid (My Closet, Wedding Stuff, Someday Maybe, Currently Obsessed), create board flow, save-to-board sheet from any product card, board detail view.

## Phase 6 — Backend (later, separate decision)
Supabase auth + profile persistence + saved items. Only touch lib/api.ts. Do not start this until Phases 0 to 5 feel solid.

---

## Session hygiene tips
- One phase per session. Fresh session per phase keeps Claude Code sharp.
- If output drifts off-brand, the fix is "re-read CLAUDE.md," not re-explaining.
- Screenshot everything as you go. This doubles as your build-in-public content.
