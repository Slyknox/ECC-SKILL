---
name: ai-video-production
description: Turn an approved short-form script into a finished 9:16 vertical video with an AI video generator (Higgsfield as the worked example, tool-agnostic otherwise). Covers shot lists, reference images and characters, image-to-video and text-to-video, consented voice, captions, assembly, credit budgeting, hook A/B variants, series consistency and AI-content compliance. Use when producing, batching or auditing AI-generated vertical video for a consumer app.
metadata:
  origin: ECC
---

# AI Video Production

Convert an approved script into a publish-ready vertical video, with a cost estimate up front and a compliance record at the end.

## When to Activate

- an approved script from `short-form-video-scripts` needs to become video
- generating several hook variants for one body
- keeping one AI presenter or character consistent across a series
- estimating credits or cost for a weekly batch
- auditing a finished video for AI disclosure and endorsement rules

## Non-Negotiables

1. Production starts only from a script marked PASS. No script, no generation.
2. Budget first: estimate credits per video before the first generation.
3. Nothing is published by this workflow. Output is a package for human approval.
4. AI-generated media is labeled as each platform requires.
5. No AI "customer" gives a testimonial. No real person's likeness or voice without written consent.
6. Demo screens use test data only, never real user data.

## Pipeline

1. **Shot list**: split the script beats into shots of 2-5 seconds. One action per shot.
2. **References**: create or collect reference images for the presenter, location and product UI. Store them with a stable name per series.
3. **Per-shot generation**: image-to-video when you need control (start from an approved still); text-to-video for simple b-roll. Keep prompts to subject, action, camera, light, style.
4. **Voice**: record a human voiceover, use a stock TTS voice, or clone a voice only with the speaker's documented consent.
5. **Captions**: burn-in word-level captions inside the safe zone; check legibility with sound off.
6. **Assemble**: cut to the beat timestamps, add the real app screen-record clip for demos, add music licensed for commercial use.
7. **Export**: 9:16, 1080x1920, H.264, 30 fps, within each platform's size and length limits.
8. **Production card**: fill the card below and attach compliance results.

## Worked Example: Higgsfield

Treat the tool as replaceable. Typical loop with a Higgsfield-style generator:

1. Generate a presenter still or character sheet once; reuse its reference for every shot in the series.
2. For each shot, run image-to-video from the approved still with a short motion prompt.
3. Use the tool's batch mode for independent shots, and wait for all jobs before reviewing.
4. Reject shots with warped hands, text, logos or faces; regenerate only the failed shot.
5. Never ask the generator to render the app UI. Screen-record the real app on test data and composite it.
6. Check the account balance and price quote before large batches.

Other generators follow the same pipeline; only prompt syntax and pricing differ.

## Cost and Credit Budgeting

Estimate before generating:

```text
credits_per_video = shots x (credits_per_clip x attempts_per_shot)
                  + voice_credits + upscale_credits
cost_per_video    = credits_per_video x price_per_credit
```

- plan 1.5-2.5 attempts per shot until your own reject rate is measured
- a 30 second video at 3 second shots is about 10 shots
- set a weekly credit cap; pause generation at 80 percent used
- log actual credits per video and use measured numbers next week
- compare cost per approved video to the CAC cap in `subscription-app-growth-model`

## Batch Workflow

- Generate all shared assets first (presenter, locations, product screen-records).
- Group shots by reference asset so the generator stays consistent.
- Run independent shots in parallel; review in one pass.
- Keep a numbered queue: script ID, status, credits spent, reviewer.

## Hook A/B Variants

Generate 3 hooks per body:

- keep the body identical; vary only the first 1-3 seconds (spoken line, on-screen text, opening shot)
- name files `ID_hookA`, `ID_hookB`, `ID_hookC`
- publish variants on separate days or accounts so tests are not diluted
- judge on 3-second hold and average watch time, not likes
- retire the loser; feed the winner's pattern into next week's scripts

## Consistency Across a Series

- one presenter reference, one wardrobe, one location set per series
- lock seed or reference image where the tool supports it
- keep a style sheet: palette, caption font, lower-third, end card
- re-use the exact same voice and pacing
- if the character drifts, regenerate from the reference rather than prompting around it

## Compliance

| Area | Requirement |
|---|---|
| Platform labels | Apply the platform's AI-generated content disclosure where required: TikTok AIGC label, Meta "AI info" label on Instagram and Facebook, YouTube altered or synthetic content disclosure. Check each platform's current policy before each campaign. |
| Endorsements (FTC) | Paid or incentivized promotion needs a clear disclosure. The FTC rule on fake reviews and testimonials bars fabricated reviews, including AI-generated "customers" describing experiences that did not happen. |
| Presenter honesty | An AI presenter must not claim personal use, results or feelings about the product. Frame it as a demonstration or explainer. |
| Likeness and voice | No real person's face or voice without written consent and scope of use. No sound-alike of a public figure. |
| Demo data | Screen-records use seeded test accounts; blur any real names, emails or payment data. |
| Music and assets | Commercial-use license recorded per track and per stock asset. |
| Claims | Re-check on-screen text against the product's allow and deny list. |

## Output Contract: Production Card

```text
Production card
Video ID:            [matches script ID]
Script status:       PASS (reviewer, date)
Platform(s):         [list]
Length / format:     [seconds], 9:16, 1080x1920
Tool and model:      [generator, model name]
Shot list:           [n shots, credits per shot, attempts]
References used:     [presenter, location, product asset names]
Voice:               [human | stock TTS | cloned with consent doc ref]
Music / assets:      [license refs]
Hook variants:       [A, B, C files]
Credits spent:       [actual] vs budget [estimate]
Disclosure applied:  [platform labels set, ad disclosure text]
Compliance check:    [PASS | FIX] by [reviewer]
Files:               [final mp4, captions srt, thumbnail]
Publish status:      NOT PUBLISHED (human approval required)
```

## Related Skills

- `short-form-video-scripts` - script source and quality gate
- `video-editing` - manual editing and finishing
- `fal-ai-media` - alternative generation backends
- `social-publisher` and `crosspost` - publishing after approval
- `subscription-app-growth-model` - CAC caps for creative spend
- `brand-voice` - voice and tone
