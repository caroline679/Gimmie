# Gimmie Archetype Scoring — reviewed points maps for lib/scoring.ts

Abbreviations: CUR = The Curator, CLN = The Clean Slate, PRO = The Protagonist,
GAR = The Garden Party, SUN = The Sunday Roman, GLT = The Gilt-Edge Girl,
ARC = The Archivist, OFF = The Off-Duty

## Weighting philosophy
- Q4 (aesthetic spaces) = 3 pts primary, 1 pt secondary. Strongest identity signal.
- Q5 (style words) = 2 pts primary, 1 pt secondary. Direct self-description.
- Q1, Q2, Q6, Q7 = 1 pt. Context signals.
- Brands (Q11 + Q12) = 1 pt per matched brand. Cap total brand points at 3 per archetype so a long brand list can't swamp the aesthetic answers.
- Q3 (text), Q8, Q9, color season screen: no archetype points. They personalize copy and feed, not identity.

## Q4 — Which spaces feel like you? (3 / 1)
- Historic & Layered: CUR 3, ARC 1
- Clean & Minimal: CLN 3, GLT 1
- Colorful & Maximalist: PRO 3, CUR 1
- Warm & Earthy: SUN 3, OFF 1
- Sleek & Modern: GLT 3, CLN 1
- Romantic & Ornate: GAR 3, CUR 1

## Q5 — How do you want to dress? (2 / 1)
- Polished: GLT 2, CUR 1
- Relaxed: SUN 2, OFF 1
- Feminine: GAR 2
- Androgynous: ARC 2, CLN 1
- Bold: PRO 2
- Understated: CLN 2, SUN 1
- Playful: PRO 2, OFF 1
- Timeless: CUR 2, GLT 1
- Edgy: ARC 2, PRO 1
- Romantic: GAR 2, CUR 1
- Effortless: SUN 2, OFF 1
- Structured: GLT 2, CLN 1
- Colorful: PRO 2, GAR 1
- Minimalist: CLN 2
- Classic: GLT 2, CUR 1

## Q1 — Day-to-day (1)
- Office life: GLT 1
- Work from home: OFF 1
- On my feet all day: OFF 1
- Mix of everything: SUN 1
- Student life: ARC 1
- I make my own schedule: PRO 1

## Q2 — What do you need right now? (1)
- Everyday casual: OFF 1
- Work outfits: GLT 1
- Going out looks: PRO 1
- Special occasions: GAR 1
- All of the above: no points
- Just browsing honestly: CUR 1

## Q6 — Inspiration sources (1)
- Pinterest: GAR 1
- Instagram: PRO 1
- Movies & TV: ARC 1
- Street style: ARC 1
- Museums & art: CUR 1
- Architecture: CLN 1
- Friends & people I see: OFF 1
- Magazines: GLT 1

## Q7 — Fit preference (1)
- Fitted and structured: GLT 1
- Relaxed and flowy: SUN 1
- Mix depending on the piece: CUR 1
- I'm still figuring it out: no points (drives the "discovery mode" style note instead)

## Brands — Q11 and Q12 combined (1 each, cap 3 per archetype)
- CUR: Sézane, & Other Stories
- CLN: Everlane, Uniqlo, COS, Totême, Mejuri, The Row, Khaite
- PRO: Zara, ASOS, Revolve, Ganni, Staud, Valentino, Jacquemus
- GAR: Anthropologie, Reformation, Free People, Sleeper, Réalisation Par, LoveShackFancy, Zimmermann
- SUN: Madewell, Dôen, Chloé
- GLT: Nordstrom, J.Crew, Banana Republic, Shopbop, Net-a-Porter, Loro Piana, Bottega Veneta
- ARC: House of Sunny
- OFF: H&M, Lululemon, Target, Aritzia

## Tie-breaking
1. Highest total wins.
2. If tied: the tied archetype that received points from Q4 wins.
3. If still tied (multi-select Q4): the tied archetype with more Q5 points wins.
4. Final fallback priority order: CUR, GLT, GAR, CLN, SUN, PRO, ARC, OFF.

## Sanity-check personas (run these before shipping Phase 2)
1. Historic & Layered + Timeless, Classic, Polished + Museums & art + Sézane, J.Crew
   → expect The Curator (CUR ~8 vs GLT ~7)
2. Warm & Earthy + Relaxed, Effortless + WFH + Everyday casual + Madewell, Aritzia
   → expect The Sunday Roman, with Off-Duty a close second
3. Colorful & Maximalist + Bold, Playful, Colorful + Instagram + Going out + Ganni, Staud
   → expect The Protagonist, decisively

## Known gaps to fix in question copy
- The Archivist is under-served by the brand list. Add "Vintage & thrift" as a selectable option in Q11 worth ARC 2, or she'll only ever emerge from word choices.
- If a user picks 6+ words in Q5, consider capping Q5 contribution at the top 8 points per archetype so word-collectors don't skew results.
