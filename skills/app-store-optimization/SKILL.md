---
name: app-store-optimization
description: App store optimization for the iOS App Store and Google Play. Covers keyword research, title and subtitle, the 100-character iOS keyword field, Play short and full descriptions, screenshots and preview video storyboards, custom product pages and store listing experiments, review prompts, localization, Apple Search Ads basics and review-guideline pitfalls. Use when planning or auditing a store listing, or mapping store pages to creator and ad campaigns.
metadata:
  origin: ECC
---

# App Store Optimization

Make the store page convert the traffic that short-form video and ads already sent, and rank for the searches that never see a video.

## When to Activate

- launching or relaunching an iOS or Android listing
- auditing metadata, screenshots or ratings
- connecting a creator or ad campaign to a dedicated store page
- localizing a listing
- preparing for store review of a subscription app

## Non-Negotiables

1. Metadata describes what the app does today. No unverifiable claims, no invented usage numbers, no "number one" without proof.
2. Subscription terms are disclosed accurately: price, billing period, trial length, renewal and how to cancel.
3. Review prompts are never incentivized and never gated on sentiment.
4. Keep the live store policy open. Character limits and rules change; verify them before submitting.
5. Do not use competitor names or trademarks in metadata.

## Keyword Research Method

1. List seed terms from the problem, the job-to-be-done and the user's own words.
2. Expand with store autocomplete, competitor listings, review text and search ads data.
3. Score each term: relevance (0-3), estimated volume, competition, and your ability to rank.
4. Keep terms where relevance is 2+ and you can plausibly rank in the top 10.
5. Place each keyword once. Do not repeat words across title, subtitle and keyword field on iOS; the store already combines them.
6. Re-check rankings every two weeks and rotate the weakest terms.

## Metadata Fields

| Field | iOS App Store | Google Play |
|---|---|---|
| Title / name | 30 chars; brand plus one strong keyword | 30 chars; brand plus one strong keyword |
| Subtitle / short description | Subtitle 30 chars; benefit plus keyword | Short description 80 chars; benefit-led hook |
| Keyword field | 100 chars, comma separated, no spaces, no repeats from title or subtitle | none |
| Description | not indexed for search; write for conversion | Full description up to 4000 chars is indexed; use the main keyword naturally a few times |
| What's new | per release; plain language | per release |

Rules of thumb: singular forms cover plurals on iOS; no filler like "best" or "free" unless true; no pricing text in the title.

## Screenshots and Preview Video

- First two screenshots carry the whole pitch; most users do not scroll.
- One benefit per screenshot: a short headline plus the real UI on test data.
- Storyboard the preview video (15-30s): problem frame, the one core action, the result, then a clear end card. Reuse the best-performing short-form video demo.
- Show only features that exist in the shipping build.
- Provide required device sizes for each platform; localize text per locale.

## Custom Product Pages and Experiments

- **iOS custom product pages**: build one per campaign or audience (for example one per creator angle), each with its own screenshots and promo text. Use a campaign-specific URL so traffic lands on the matching page.
- **Google Play custom store listings** and **store listing experiments**: test icon, screenshots, short description and feature graphic. Run tests for at least 7 days and until the result is significant.
- Map every video pillar or ad angle to one page. The page headline repeats the video's promise.
- Record each mapping in the ASO brief so conversion can be compared by campaign.

## Ratings and Reviews

- Use the platform in-app review API (StoreKit review request on iOS, in-app review API on Android).
- Ask after a success moment (a completed task), never at launch or during an error, and not more often than the platform allows.
- Never offer rewards, discounts or features for a rating. Never filter who gets asked by predicted sentiment.
- Route unhappy users to support through a separate link, not instead of the review option.
- Reply to reviews with specific, honest answers.

## Localization

- Start with the markets that already send installs; then add by volume and revenue potential.
- Localize keywords, not just translate: research terms per locale.
- Localize screenshots and the preview video text.
- Check legal subscription wording per country.

## Apple Search Ads Basics

- Campaign types: brand, category, competitor and discovery. Keep exact-match and broad discovery separate.
- Start small, harvest converting search terms into exact match, and add the rest as negatives.
- Judge on cost per install and cost per paid subscriber, not taps.
- Point ads at the custom product page that matches the keyword intent.

## Review-Guideline Pitfalls

- claims you cannot prove in metadata: usage counts, ratings, awards, rankings
- screenshots that show features not in the build, or devices the app does not support
- subscription screens missing price, period, trial terms, renewal and restore purchase
- mentioning other platforms, prices or external payment in a way the store forbids; read current rules for external purchase links by region
- mismatch between description and actual behavior, or hidden functionality
- privacy labels and data-safety forms that do not match what the app collects

## Output: ASO Brief Template

```text
ASO brief - [app, platform, locale, date]
Goal:               [installs, trial starts, paid]
Audience / intent:  [who and which searches]
Keyword set:        [term, relevance, volume est., difficulty, placement]
Title:              [30 chars]
Subtitle / short:   [30 or 80 chars]
iOS keyword field:  [<=100 chars]
Description:        [outline or final]
Screenshots:        [1..n: headline, UI state, benefit]
Preview video:      [storyboard beats]
Custom pages:       [campaign -> page -> URL]
Experiments:        [hypothesis, variant, metric, duration]
Review prompt plan: [trigger event, frequency]
Localization:       [locale list and priority]
Ads:                [Search Ads structure and budget]
Policy check:       [claims, subscription disclosure, privacy labels]
Baselines:          [impressions, page views, conversion rate, rating]
Next review date:   [date]
```

## Related Skills

- `subscription-app-growth-model` - funnel math and attribution
- `short-form-video-scripts` - video angles that map to store pages
- `ai-video-production` - preview video production
- `seo` - web landing page search
- `market-research` - competitor and audience research
- `brand-voice` - listing copy voice
