---
name: anti-ai-checklist
description: Single source of truth for anti-AI-detection rules — banned words, phrases, intensifiers, and structural tells. Used by pnb-draft (writing + review) and pnb-compose (pre-convert check).
last_reviewed: 2026-04-20
---

# Anti-AI Detection Checklist

This file is the one place banned words/phrases/intensifiers live. Every skill that scans prose (pnb-draft, pnb-compose) reads **this file** rather than carrying its own copy. Update here; changes flow to every skill.

For the "why" behind these rules and Dynatrace brand voice context, see `style-guide.md`.

---

## Em dashes

- **Rule:** No em dashes (—). Replace every one with a comma, colon, semicolon, or parenthetical.
- **Why:** Em dashes are a strong AI-detection signal in 2025+ detectors.

---

## Banned intensifiers (generic without specifics)

- `seamless` / `seamlessly`
- `robust` (when used generically)
- `streamline` / `streamlined`
- `game-changer` / `game-changing`
- `revolutionize` / `revolutionary`
- `cutting-edge`
- `unprecedented`
- `pivotal`
- `comprehensive` (when used without what exactly is covered)
- `powerful` (when used without what exactly it can do)

Replace with concrete, specific descriptions.

---

## Banned AI words

- `delve`
- `harness`
- `leverage` (as a verb)
- `navigate` (metaphorical, e.g., "navigate complexity")
- `landscape` (metaphorical)
- `realm` (metaphorical)
- `tapestry` (metaphorical)
- `myriad`
- `plethora`
- `empower` / `empowers` (when vague)

---

## Banned phrases

- `It's important to note`
- `In today's X landscape`
- `In the ever-evolving world of`
- `Not only... but also`
- `Let's dive in` / `Let's explore`
- `First and foremost`
- `Last but not least`
- `With that said`
- `At the end of the day`
- `When it comes to X` (as an opener)
- `In order to`
- `A holistic approach`

---

## Banned sentence starters (transitions)

- `Furthermore`
- `Moreover`
- `Additionally`
- `In conclusion`
- `To summarize`

---

## Structural tells

- **Symmetry:** if three or more sentences or bullets follow the same opening pattern, vary at least one.
- **Paragraph rhythm:** if three consecutive paragraphs are the same length, vary one.
- **Perfect bullet lists:** mix bullet lengths; avoid all-same-length parallel bullets.

---

## Positive signals (want to see)

- Contractions used naturally (`it's`, `you'll`, `don't`, `can't`)
- Sentence length mix: short declaratives interleaved with longer compound sentences
- Concrete examples, persona-specific scenarios, named products/paths
- First or second person (as voice profile dictates), not third-person-about-Dynatrace

---

## How skills use this file

- **pnb-draft** reads this while drafting (fix silently per section) and again during the final review (flag-to-author).
- **pnb-compose** reads this during the pre-convert quality check (flag-to-author, never block).
