# Blog writing learnings: Kiro power post (partner-integration announcement)

Distilled from the editorial and final-check sessions on "Dynatrace observability, now a Kiro power". Written to be merged with learnings from other blogs. Each item is tagged **[general]** (applies to any PNB post) or **[type: partner-integration]** (applies mainly to partner/product-integration announcements).

## 1. Workflow that worked

1. Revise the original draft with Claude in editorial rounds (audience, structure, phrasing).
2. Save the decisions in a context file, so later sessions start with the "why", not only the text.
3. Final check in a fresh session against three inputs: original draft, revised draft, context file. Ask Claude to review and raise questions before editing.
4. Resolve open points as numbered items (Ad 1, Ad 2, ...), then write a new version file (V2, V3, V4). Never overwrite earlier versions.
5. Run the anti-AI checklist, then the answer-engine-optimization (AEO) check, then a last AI-slop pass.
6. Render to Word last, from the final markdown.

**[general]** Keep every version as its own file. It made it easy to compare and to offer "(1) / (2)" options side by side.

## 2. Editorial principles

- **[general]** Lead with the news or the reader benefit, not the timing. No "Today, we're excited to announce".
- **[general]** Address each audience explicitly in the intro with a short pivot ("For customers... For developers new to X...").
- **[general]** Pitch at the actual reader. For developers: tight loop between code and production, not MTTR or ops-marketing language.
- **[general]** Concrete capabilities beat abstract bullets. "Investigate live incidents and get root cause analysis in the Kiro chat" works; "smart suggestions for configuration" does not.
- **[general]** Merge "challenge" and "solution" sections when the challenge is well known. One paragraph of problem framing, not three.
- **[general]** Move customer quotes to where they validate a claim just made, not to the end.
- **[general]** The conclusion must not restate the intro. Show the new reality for the reader, then a clean call to action.
- **[general]** Differentiate the product, but proportionally. One paragraph on the differentiator (here: grounding in causal AI and real data). More derails the post.
- **[general]** Avoid listing internal component names (Grail, Smartscape, etc.) in the main argument. Link to a deeper page instead.
- **[general]** Do not mirror a source article's structure when paraphrasing. Rewrite in our own voice.
- **[type: partner-integration]** Name the host product and the mechanism in the title (here "Kiro power"). Searchers and partners both look for it.
- **[type: partner-integration]** Intro arc: host product, then integration mechanism, then our integration, then both audiences, then walkthrough signpost.
- **[type: partner-integration]** Borrowing a partner's credibility phrase ("curated, partner-validated bundles") is fine when rephrased.
- **[type: partner-integration]** Keep a small nod to the co-author's company where it is natural (we kept an AWS prerequisite line deliberately).

## 3. Walkthrough and UX honesty

- **[general]** Show realistic UX including expected error states. Example: after install, the product shows an error because config ships with placeholders. Say "this is expected" and give the next click.
- **[general]** Keep placeholder conventions exactly as the UI ships them (here `YOUR_DT_URL`, `YOUR_BEARER_TOKEN`). Check against the product before publishing.
- **[general]** Prose examples and demo video should reinforce each other (same example query in both).
- **[general]** Keep wording identical between prose and captions (we caught "verifying" vs "confirming").
- **[general]** Heading style for steps: active verb, no gerund ("Install ...", not "Installing ...").

## 4. Anti-AI-artefact check (from the pnb-draft anti-ai-checklist)

Source of truth: `~/.claude/skills/pnb-draft/references/anti-ai-checklist.md`.

- No em dashes. Replace with comma, colon, period or parentheses. In this post that was 13 replacements, the single most common finding.
- Banned intensifiers: seamless, robust, streamline, game-changer, revolutionary, cutting-edge, unprecedented, pivotal, generic "comprehensive" and "powerful".
- Banned words: delve, harness, leverage (verb), metaphorical navigate/landscape/realm/tapestry, myriad, plethora, vague empower.
- Banned openers and phrases: Furthermore, Moreover, Additionally, In conclusion, "Not only... but also", "In order to", "Let's dive in".
- Structural tells: three or more same-pattern sentences, same-length paragraphs, perfectly parallel bullets.
- **Exception:** do not edit real customer quotes. Our quote contained "game changer" and "unprecedented"; we kept it verbatim and flagged it.
- Practical method: grep for the em dash and the banned-word regex, then read for structural tells.

## 5. Answer engine optimization (AEO) guidelines and how we judged them

Source: https://styleguide.dynatrace.com/docs/best-practices/write-for-answer-engine-optimization/

**Applied (cheap for agents, neutral or positive for humans):**
- Active-verb H2/H3 headings, no gerunds.
- A one-sentence, extractable definition right under the first heading (the "lede"). Combine with an FAQ-style H2 ("What is X?") so heading and first sentence form a question-answer pair.
- One idea per paragraph; short bridge sentences are fine.
- Parallel structure in lists; numbered lists for procedures, bullets for non-sequential items.
- Bold only for UI elements and key terms.
- Tables for grid-like reference data (placeholder to replacement mappings). Trade-off: long copy-paste values like URLs are slightly fussier inside table cells.

**Consciously not applied:**
- Rewriting an announcement title into a how-to. Launch posts serve readers who want the news and the install path.
- Removing italics from quotes and figure captions. The rule targets italics for emphasis, not conventional roles.
- Dismantling a deliberate intro arc. Satisfy front-loading with a lede sentence instead.
- Adding "Key takeaways" or FAQ blocks to a ~600-word post. It would read as padding.
- Renaming "Conclusion" purely for AEO. The call to action link already carries the action.

**Side effect to watch:** a new lede creates redundancy with the old second intro paragraph. Fix by trimming that paragraph to one bridge sentence ("The X power brings observability into that model.") and keep the audience pivot after it.

## 6. Reusable post structure (partner integration / power announcement)

1. **Title:** news plus both product names, no "we're excited".
2. **What is it?** (FAQ-style H2): lede definition, host product, mechanism, one-line bridge, audience pivot, walkthrough signpost.
3. **Why this matters:** short problem framing, differentiator paragraph, diagram with caption, concrete capability bullets, customer quote.
4. **Install / walkthrough:** prerequisites, preparation, install steps including expected error state, configuration (table or bullets), first prompts, demo video.
5. **Conclusion:** new reality for the reader, forward-looking, CTA link.

## 7. Tooling notes

- Word rendering: the pnb-compose skill has a converter (`pnb_to_docx.py`) and the Word template, but it expects YAML front matter (title, slug, authors, meta_description, categories, tags). For our quick version we used a one-off python-docx script, which does not use the official template. For publication, add front matter and use pnb-compose.
- The one-off script handles headings, lists, hyperlinks, images, quotes, and (after extension) markdown tables.
- Embed diagrams as markdown image references in the md; keep video as a captioned placeholder until the file or link exists.
- When a session worktree is recycled, uncommitted files are lost. Save deliverables into the real project folders, not only the worktree.

## 8. Decision checklist before declaring a post final

- [ ] Title leads with the news and names the mechanism
- [ ] Both audiences addressed in the intro
- [ ] Lede sentence answers the heading question
- [ ] No redundancy between lede and following intro paragraph
- [ ] Every capability is concrete and tied to a developer task
- [ ] Customer quote placed right after the claims it supports
- [ ] Expected error states documented in the walkthrough
- [ ] Placeholders match the product UI
- [ ] Prose, captions and video describe the same demo
- [ ] Zero em dashes, no banned words (customer quotes excepted)
- [ ] Headings use active verbs
- [ ] Figures embedded; video placeholder resolved
- [ ] Word export done with the PNB template and front matter
