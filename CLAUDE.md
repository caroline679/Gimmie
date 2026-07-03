# CLAUDE.md — Gimmie

## What this project is
Gimmie is a visual-first, scroll-and-discover shopping app for women building their personal style. "Pinterest, but everything is actually for sale and current." This repo is a high-fidelity working prototype: real frontend architecture, mock data layer, backend-ready state, no live backend yet.

## Tech stack
- Next.js 14+ (App Router) + TypeScript
- Tailwind CSS with brand tokens defined as CSS variables (see Design Tokens)
- No external UI libraries. No shadcn, no MUI. Every component is custom.
- State: React context for the user profile. Structure it so a future Supabase swap only touches `lib/api.ts`.
- Deployment target: Vercel

## Design tokens (never change these hex values)
- Electric Purple `#7A2FF2` (hero / primary actions / selection states)
- Hot Pink `#FF3DA5` (secondary CTAs, the wordmark exclamation point)
- Coral `#FF6A4D` (tertiary accents, "vs." badges)
- Zap Yellow `#FFE23D` (high-emphasis CTAs, sparkle accents)
- Ink Plum `#170A2E` (dark backgrounds, dark tiles)
- Cloud `#FBF7FF` (light backgrounds)

Fonts (Google Fonts):
- Display: Unbounded (headlines, wordmark, big numbers). Use with restraint.
- UI/body: Hanken Grotesk (everything else)

Wordmark: "gimmie!" lowercase in Unbounded Black, exclamation point in Hot Pink.
Signature motif: four-pointed sparkle ✦ used for save actions, selection badges, and micro-moments. Subtle global pulse animation. Squish blobs as decorative card backgrounds, retro checkerboard as texture only (max 5% opacity).

## Layout rules
- Mobile-first inside a centered 390px phone frame on desktop (`components/PhoneFrame.tsx`)
- Pill-shaped buttons, 16 to 24px corner radius on cards
- Screen transitions: slide left on advance, slide right on back
- Respect prefers-reduced-motion

## Copy voice
Warm, confident, a little funny. Talks to the user like a sharp friend, never like a system. Examples of the register: "Be honest, we're not here to judge." / "Type anything, we actually read this." Never corporate. Sentence case everywhere. Buttons say exactly what they do.

## Architecture conventions
- Quiz questions live in `data/questions.ts` as config objects, NOT hardcoded screens. One generic QuizScreen component renders any question type (tile-multi, tile-single, chips, text, brand-picker, color-triple).
- All quiz answers write to a single `UserProfile` object (see `types/profile.ts`).
- Archetype assignment uses the weighted scoring engine in `lib/scoring.ts`. Never use if/else chains for archetype logic.
- `lib/api.ts` contains stubbed async functions: `saveUserProfile()`, `getFeed()`, `getCollections()`. They read/write local mock data now and console.log their payloads. Do not scatter data access anywhere else.
- Mock products live in `data/products.json`.

## The scoring engine (important)
Every answer option carries a points map toward the 8 archetypes, e.g. `{ curator: 2, gardenParty: 1 }`. On completion: sum all points, highest total wins, ties broken by the aesthetic picker (Q4) result. Archetypes: The Curator, The Clean Slate, The Protagonist, The Garden Party, The Sunday Roman, The Gilt-Edge Girl, The Archivist, The Off-Duty. The Off-Duty is a real archetype with its own points, not a fallback.

## Things to never do
- Never add a UI library or icon pack
- Never change brand hexes or fonts
- Never hardcode quiz content inside components
- Never call real payment, auth, or scraping services
- Never present the color season result as definitive; copy always frames it as a starting palette the user can correct
