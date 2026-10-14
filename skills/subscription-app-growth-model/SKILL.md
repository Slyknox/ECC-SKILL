---
name: subscription-app-growth-model
description: Funnel and unit-economics model for a consumer subscription app sold on the web (PWA with a card processor) and in the app stores (a subscription management service). Covers the metrics tree, steady-state subscriber math, LTV and CAC caps, store fees, back-solved volume targets, weekly KPI review, experiment backlog, attribution and exit-readiness metrics. Use when sizing growth targets, setting channel CAC caps, running a weekly KPI review, or preparing acquirer-ready metrics.
metadata:
  origin: ECC
---

# Subscription App Growth Model

Turn "we want 50k paid subscribers" into monthly volume targets, spend caps and a weekly decision routine.

## When to Activate

- setting subscriber targets and working backwards to traffic
- deciding how much to pay per install, trial or paid subscriber by channel
- running the weekly KPI review
- choosing the next growth experiment
- preparing metrics for an investor or acquirer conversation

## Non-Negotiables

1. Use measured numbers. Where a number is an assumption, label it ASSUMPTION and replace it within 30 days.
2. Never invent usage numbers, conversion rates or testimonials for external use.
3. Report net revenue after store fees and refunds, not gross.
4. Compare channels on cost per paid subscriber and payback, not on views or installs.
5. Keep web and store cohorts separate until you can prove they behave the same.

## Metrics Tree

```text
impressions -> views -> profile or link clicks -> landing visits
  -> trial or signup -> activation -> paid -> retained (M1, M3, M6, M12)
```

| Stage | Metric | Typical owner |
|---|---|---|
| Reach | impressions, unique reach | content |
| Attention | 3-second hold, average watch time, completion | scripts |
| Intent | click-through to link or store page | CTA and bio |
| Landing | visit to signup or install rate | landing page, ASO |
| Activation | % reaching the first success moment in 24h | product |
| Monetization | trial-to-paid, direct-to-paid | paywall |
| Retention | monthly logo churn, revenue churn, cohort curves | product, lifecycle |

Define "activation" once, as a single measurable event, and never change it silently.

## Steady-State Subscriber Math

```text
steady_state_base = new_paid_per_month / monthly_churn
months_to_90pct   = ln(10) / -ln(1 - monthly_churn)   # approximate
```

Example: 800 new paid per month at 8 percent monthly churn gives a base of 10,000. Churn is the lever with the highest long-run effect: halving churn doubles the steady-state base at the same acquisition.

## Unit Economics

```text
net_ARPU   = price x (1 - store_fee) - refunds     # per paying subscriber per month
LTV        = net_ARPU x gross_margin / monthly_churn
CAC_cap    = LTV / 3                               # LTV:CAC of 3:1
payback_mo = CAC / (net_ARPU x gross_margin)
```

- Store fee: a reduced rate (15 percent) is available under the Apple Small Business Program and for Google Play subscriptions on the reduced tier; confirm eligibility and the current rates in each store's program terms. Standard rates are higher.
- Web payments avoid the store fee but carry processor fees and tax handling. Where store rules permit an external purchase link, model it as a separate channel.
- Use the lower of measured and target payback when setting caps; prefer payback under 6 months for cash-constrained teams.
- Create one model per plan (monthly, annual where allowed, family) and weight by mix.

Illustrative example (ASSUMPTION): price 4.99, store fee 15 percent, margin 85 percent, churn 8 percent gives net_ARPU 4.24, LTV about 45, CAC cap about 15.

## Back-Solving Volume Targets

Required new paid subscribers per month (new_paid = target x churn):

| Target base | Churn 5% | Churn 8% | Churn 10% |
|---|---|---|---|
| 10,000 | 500 | 800 | 1,000 |
| 50,000 | 2,500 | 4,000 | 5,000 |
| 100,000 | 5,000 | 8,000 | 10,000 |

Back-solve traffic at 8 percent churn using ASSUMPTION conversion rates (replace with measured): 1 percent view-to-click, 3 percent click-to-paid.

| Target base | New paid / month | Clicks / month | Views / month |
|---|---|---|---|
| 10,000 | 800 | about 26,700 | about 2.7M |
| 50,000 | 4,000 | about 133,000 | about 13.3M |
| 100,000 | 8,000 | about 267,000 | about 26.7M |

Add a column for paid creator or ad spend: required new paid x blended CAC. If it exceeds the cap, improve conversion, retention or price before adding spend.

## Weekly KPI Review Ritual

30 minutes, same day each week, same sheet.

1. Last week vs plan: views, clicks, signups, trials, paid, MRR, churn.
2. By channel and by content pillar: cost per paid, payback, top 3 and bottom 3 videos.
3. Funnel diagnosis: find the one stage furthest below benchmark.
4. Cohort check: M1 retention for the newest cohorts, web vs store.
5. Decide: scale, hold or cut each channel against its CAC cap.
6. Pick one experiment to start and one to stop. Write the decision and owner.

## Experiment Backlog

Rank by (expected lift x reach) divided by effort.

- paywall: placement, price anchoring, copy, trial offer vs direct purchase
- trial length: shorter vs longer, with measured trial-to-paid
- annual plan where store rules and the product allow it, with a clear savings statement
- family or multi-seat plan
- onboarding: shorten time to first success moment
- win-back and cancellation-save offers that never block cancelling
- referral loop that rewards a real, paid referral with a real benefit, disclosed plainly
- store page tests (see `app-store-optimization`)

Each experiment records hypothesis, metric, minimum sample, duration and decision rule before launch.

## Attribution

- UTM on every link, one set per platform, creator and campaign; first-touch stored at signup.
- Web: store UTM and referrer in the account record; reconcile with processor events.
- iOS: SKAdNetwork or AdAttributionKit postbacks for paid campaigns, with conversion values mapped to trial and paid; campaign-specific custom product page URLs.
- Android: install referrer parameter.
- Creator codes: unique code per creator, redeemed at signup or checkout, tied to a disclosed arrangement.
- Subscription events from the store flow through the subscription management service into one warehouse table keyed by user and platform.
- Expect undercounting on iOS; triangulate with promo-code and "how did you hear" signals.

## Exit Readiness

Metrics acquirers ask for, kept current monthly:

- MRR, ARR, net new MRR bridge (new, expansion, contraction, churn)
- net revenue retention and gross revenue retention
- cohort retention curves by month and by channel
- CAC by channel, blended CAC, CAC payback
- channel concentration: share of new paid from the largest channel (aim to avoid dependence on one source)
- refund and chargeback rates, store vs web split
- gross margin including AI generation, hosting and support costs
- clean data: documented definitions, reproducible queries, no unverified claims

## Output Contract: Model Sheet Layout

```text
Tab 1 Assumptions:  price per plan, store fee, processor fee, margin, churn, conversion rates (each marked MEASURED or ASSUMPTION)
Tab 2 Funnel:       weekly rows; columns follow the metrics tree
Tab 3 Cohorts:      signup month x months since signup, logo and revenue retention
Tab 4 Unit econ:    net ARPU, LTV, CAC cap, payback per plan and channel
Tab 5 Targets:      back-solve table for 10k / 50k / 100k with required traffic and spend
Tab 6 Channels:     spend, new paid, CAC vs cap, decision (scale | hold | cut)
Tab 7 Experiments:  backlog, status, results, decision
Tab 8 Exit metrics: MRR bridge, NRR, concentration, refund rates
Tab 9 Log:          weekly decisions with date and owner
```

## Related Skills

- `app-store-optimization` - store conversion and custom product pages
- `short-form-video-scripts` - top-of-funnel content
- `ai-video-production` - creative cost per video
- `investor-materials` - presenting these metrics
- `market-research` - benchmarks and competitors
- `seo` - organic landing traffic
