---
name: short-form-video-scripts
description: Script system for 15-60 second vertical video on TikTok, Instagram Reels, YouTube Shorts and Facebook Reels for consumer subscription apps. Covers hook taxonomy, retention beats, proven formats, per-platform deltas, weekly batch production, a per-script output schema and a claims quality gate. Use when writing, batching or reviewing short-form video scripts that drive app installs or signups.
metadata:
  origin: ECC
---

# Short-Form Video Scripts

Write vertical video scripts that earn the first three seconds, hold attention, and convert without inventing a single claim.

## When to Activate

- writing scripts for TikTok, Instagram Reels, YouTube Shorts or Facebook Reels
- planning a weekly batch (for example 30 scripts from 5 content pillars)
- adapting one idea to four platforms without copy-pasting it
- reviewing scripts before they go to video production
- building a hook library for A/B testing

## Non-Negotiables

1. The hook is written first and tested alone. A weak hook cannot be saved by the body.
2. One video carries one idea and one call to action.
3. Every statistic has a named source and a date. No source, no stat.
4. Claims come from the product-provided allow list. Anything on the deny list is cut.
5. Prices, trial lengths and plan limits are copied from the live product, never from memory.
6. Scripts are written for the ear and the screen, not the page.

## Inputs Required

Collect before writing. If missing, ask once, then proceed with explicit assumptions.

- audience and the problem they already feel (in their words)
- 3-6 content pillars (for example: problem education, product demo, myth-busting, tips, stories, comparisons)
- allow list and deny list of claims supplied by the product owner
- real pricing, trial terms and store links
- brand voice profile (use `brand-voice`)
- disclosure rules for AI-generated media (see `ai-video-production`)

## Hook Taxonomy (first 1-3 seconds)

| Hook type | Pattern | Use when |
|---|---|---|
| Pain callout | "If you [specific situation], watch this." | audience problem is concrete |
| Curiosity gap | "The setting nobody checks on [thing]." | there is a real, non-obvious fact |
| Contrarian | "Stop doing [common habit]." | the claim is sourced and defensible |
| Stat | "[Number] percent of [group] [fact] (source: X)." | a verifiable stat exists |
| Demo first | show the result on screen, then explain | the product visibly solves it |
| POV | "POV: you just [moment]." | story or relatable scene |
| Question | "Do you know how to [outcome]?" | simple, answerable in the body |
| Proof of process | "I tested [thing] so you do not have to." | only if the test really happened |

Rules: spoken words and on-screen text land in the same second; no greetings, no logo intro, no "hey guys"; start mid-action.

## Retention Beats

Structure every 15-60 second script as beats with timestamps.

| Beat | Time (30s example) | Job |
|---|---|---|
| Hook | 0-3s | stop the scroll, name the payoff |
| Context | 3-8s | one line of why this matters |
| Payoff steps | 8-24s | 2-4 visual changes, new frame every 2-4s |
| Pattern interrupt | mid-video | zoom, cut, text pop, or reveal to reset attention |
| CTA | last 3-5s | one specific action |

Loop trick: end on a line that flows back into the hook so replays count.

## Proven Formats

1. **POV**: a relatable moment in first person. Best for emotion and shareability.
2. **Myth-bust**: state the myth, give the sourced correction, show the fix.
3. **Stat-with-source**: one stat, the source on screen, what to do about it.
4. **Demo screen-record**: real app flow on test data, 3 taps to a result, caption the taps.
5. **Green-screen reaction**: presenter reacts over a screenshot or article; cite it on screen.
6. **List**: "3 things" with a visual change per item; items must be independently useful.
7. **Story**: a short scenario with a turn; clearly labeled as illustrative if fictional.
8. **Comparison**: option A vs option B on stated criteria; name only facts you can source and never disparage competitors without evidence.

## Per-Platform Deltas

Verify current limits in each platform's creator documentation before a campaign; limits change.

| Item | TikTok | IG Reels | YT Shorts | FB Reels |
|---|---|---|---|---|
| Sweet-spot length | 20-45s | 15-30s | 20-45s (loop friendly) | 15-30s |
| Caption | short, keyword in first line | short, hook echo | title is the hook, keep brief | short, plain language |
| On-screen text | large, centered, inside safe zone | same | same, plus title text | same, readable muted |
| Hashtags | 3-5 specific | 3-5 specific | 1-3, include #Shorts if useful | 1-3 |
| CTA wording | "link in bio" or search prompt | "link in bio" | "link in description" or pinned comment | "tap the link" where allowed |
| Destination | web landing page (PWA) or store link per policy | same | same | same |

Link-in-bio vs app store: send traffic to a web landing page that detects device and routes to the PWA, App Store or Google Play. Use one tracked URL per platform (UTM) so attribution works (see `subscription-app-growth-model`). Keep text inside the platform UI safe zones so buttons never cover it.

## Batch Production

Weekly engine: 5 pillars x 6 scripts = 30 scripts.

1. Pick the week's pillars and the top 3 hook types from last week's results.
2. For each pillar write 6 ideas, then 3 hook variants per idea (see `ai-video-production` for hook A/B).
3. Assign each script a format and a platform; adapt, do not duplicate.
4. Run the quality gate in one pass; mark each script PASS, FIX or CUT.
5. Hand PASS scripts to production as a numbered queue.

## Output Contract

Deliver one block per script, plus an index table.

```text
ID:            SF-YYYYWW-###
Pillar:        [pillar]
Format:        [POV | myth-bust | stat | demo | green-screen | list | story | comparison]
Platform:      [TikTok | IG Reels | YT Shorts | FB Reels]
Length:        [seconds]
Hook (variant A/B/C): [spoken line] / [on-screen text]
Beats:
  0:00-0:03  Hook      VO: ...  Text: ...  Shot: ...
  0:03-0:08  Context   VO: ...  Text: ...  Shot: ...
  ...
  0:27-0:30  CTA       VO: ...  Text: ...  Shot: ...
B-roll / shot list: [numbered shots]
CTA: [exact wording and destination]
Caption: [text]
Hashtags: [list]
Sources: [name, URL or document, date for every stat]
Compliance notes: [AI disclosure, ad disclosure, claims checked, test data used]
Status: [PASS | FIX | CUT]
```

## Quality Gate

A script passes only if all are true:

- every statistic has a source and date in the Sources field
- no invented testimonials, reviews, usage numbers, user counts or "founding member" claims
- prices and trial terms match the live product
- every claim appears on the allow list and none on the deny list
- paid or sponsored content carries the required ad disclosure
- AI-generated or synthetic media is labeled as the platform requires
- the hook works with sound off (text carries it)
- one idea, one CTA

## Hard Bans

Delete and rewrite any of these:

- fear-bait that exaggerates danger to drive installs
- fake reviews, fake customers, or AI personas presented as real users
- undisclosed AI presenters or synthetic voices
- unverifiable superlatives ("the best", "number one", "guaranteed")
- medical, legal, financial or safety promises the product cannot prove
- fake scarcity or countdowns not backed by a real deadline
- engagement bait ("comment YES") unless the owner explicitly wants it
- copy that would work unchanged for any other product

## Related Skills

- `ai-video-production` - turn approved scripts into finished video
- `content-engine` - platform-native text content and repurposing
- `marketing-campaign` - positioning and campaign angle
- `brand-voice` - durable voice profile
- `crosspost` and `social-publisher` - distribution after approval
- `video-editing` - manual edit and assembly
- `seo` - landing page and caption keywords
