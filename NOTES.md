# Notes from building this talk page

A retrospective from the 6pm-deadline scramble. Written so future-Matt (and future-Claude) can move faster next time.

## Outcome

- Shipped a single-page, scroll-snap deck at https://agents-making-money.vercel.app
- Repo: https://github.com/mmurrs/agents-making-money
- 7 sections: Title · Premise · State (Read/Write/Own?) · Tour · Edges · Experiments · Your move
- EigenCloud design system (indigo #1a0c6d, ABC Repro headings, Geist body)
- Keyboard nav (arrows / space / home / end)
- Real avatar, real X link, real QR to docs.eigencloud.xyz
- Vercel auto-deploys on every `git push`

## What worked

### Start with structure, not slides
Opening the laptop and writing `index.html` with 6 empty `<section>` headlines surfaced weak spines faster than outlining ever did. The act of seeing the headline on-screen was the thinking.

### Brain-dump in 7 fixed prompts
When I circled, the anti-circle protocol — 90s per question, banned words (*maybe, or, I'm not sure*), no re-reading — converged me. The answer to "working title" is almost never the final title, but writing *anything* in the box unblocks everything downstream.

### "Saturday morning question"
*"If all 20 developers leave convinced, what are they doing Saturday morning?"* That one question decided the whole talk spine. Use it earlier next time.

### Mirror → confirm → edit
Before touching the file, Claude repeated back the change set in bullet form and asked 2–4 clarifying questions. This caught several misfires (Dark Bloom ≠ "agents run companies"; image #14 was transit402 not AgentKit). Keep doing this.

### Build-first cycles
Anti-thinking-loops device: *"The angle is whatever you wrote in the last prompt. Stop thinking, start building. If after 15 min it feels wrong, re-think — not before."* This broke me out of two separate circles.

### Scaffolding before content
First pass was literally placeholder headlines + dashed diagram boxes. Filling in real content against an existing visual structure is 10× easier than writing text and then making layout.

### Vercel + GitHub linkup
`vercel link --yes --project X --scope Y` + `vercel deploy --prod` gave auto-deploy on every push. Total setup: 90 seconds. Should be the default for any throwaway deck or prototype.

### AgentCash for LinkedIn/X lookup
Worked for the X avatar (Firecrawl scrape → pbs.twimg.com URL). Didn't work for LinkedIn (403 auth wall; Minerva returned wrong person). **Lesson:** default to X/GitHub for public avatars, skip LinkedIn enrichment unless you already have a verified LinkedIn URL.

## What went wrong / cost time

### Image misattribution cascades
Same screenshot got mapped to 3 different cards over 5 messages. Every "swap screenshot X to card Y" compounded confusion.

**Fix next time:** Save each image with a **semantic filename at the moment of paste** (`openfront-tournament-diagram.png`, not `13.png`). And before swapping, *explicitly state what each file currently contains* so we catch misfires early.

### Title churn
Title went through at least 5 iterations: *Agents Making Money* → *...and what they're buying* → *...a check-in on where things are* → *Read → Write → ?*. Each change was fine in isolation; the cumulative context-switch cost was real.

**Fix:** Lock the title last. Build the talk against a placeholder like `[TITLE TBD]` and only finalize when the content is stable.

### Scope creep in the bounty section
Bounty framing flip-flopped: *"$100 for first to ship"* → *"$100 for what problem to solve"* → *"$100 to build with us"* → eventually removed bullet-question list entirely. Every reshape was an edit, then a re-edit.

**Fix:** When you catch yourself oscillating on one component, stop editing and spend 60s on *"what is this slide's job?"* The job clarifies the copy.

### Screenshot quality
Half the real screenshots were either wrong, misaligned, or didn't tell the story on their own. Ended up swapping to icon-based cards in the final hour.

**Fix:** For a 10-min talk with a scrolling page, icons + captions > screenshots most of the time. Screenshots only when the image is *itself* the point (a diagram with unique information, a Sreeram tweet that's the story).

### Sovereign agents rabbithole
First 40 min of conversation included sovereign-agents framing that got explicitly scrapped later. Spent tokens on an angle that was wrong for the room.

**Fix:** Identify the audience *first*, and filter your own saved memories against "does this belong in front of THIS audience?" before introducing them.

## Patterns worth reusing

### The "angles email" prompt
When genuinely stuck on talk direction, email yourself 4 distinct spines — not variants of the same idea, but actually different takes. The gut-check question *"which, if nailed, would I be proudest of?"* picks the right one. Agentcash StableEmail cost: $0.02.

### One-page-deck pattern
Single scrolling HTML with sections as "slides." Benefits:
- Shareable as a URL, not a PPTX
- Embeds live links, real screenshots, live examples
- Auto-updates on git push (via Vercel)
- Works on phone, projector, laptop
- Builders can revisit and click through later

Keyboard nav (arrow keys) makes it feel deck-like on the projector.

### EigenCloud design system port
The design skill handoff bundle (`eigencloud-design-system/`) dropped into any project gives you indigo/neutral palette, typography, and grid motif in 5 min. Default to it for any Eigen-adjacent artifact.

### "Mirror before edit" for ambiguous requests
When a message is long or contains multiple asks, bullet-mirror the ask back before touching the file. Prevented at least 3 wrong-direction edits.

## What to carry forward

1. **Lock the audience first. Lock the "Saturday morning" outcome second. Everything else falls out.**
2. **Scaffold before content.** Placeholder headlines in real layout > outline in a doc.
3. **Vercel + git push + arrow-key nav** is the fastest path from "no deck" to "shippable deck."
4. **Icons over screenshots** unless the screenshot is the story.
5. **Save asset files with semantic names immediately.**
6. **When oscillating, ask "what is this component's job?" — don't keep editing.**
7. **Mirror → confirm → edit** for any multi-part ask.

## Was the outcome as desired?

Partial self-check — for you to validate:

- [ ] The talk has a clear spine and doesn't require you to improvise the arc
- [ ] The page is usable on-stage (big enough text, keyboard nav works, links resolve)
- [ ] The $100 bounty + QR give a concrete next-action for the room
- [ ] The edges cards surface real questions you'd want to hear answers on
- [ ] You can walk through all 7 sections in 8–9 min, leaving 1–2 for discussion
- [ ] Nothing on-screen feels like it needs an apology ("sorry, this is rough")

If any of those aren't `[x]` after tonight, the fix is worth noting back here for future reference.
