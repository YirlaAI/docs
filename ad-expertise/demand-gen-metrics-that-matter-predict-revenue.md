---
layout: post
title: "Demand Gen Metrics That Matter: The 6 KPIs That Actually Predict Pipeline and Revenue"
date: 2026-08-08
author: Scott Schnaars
description: "Most demand gen teams track a dozen metrics but only a handful predict revenue. Here are the 6 KPIs that matter, with formulas, setup steps, and a board-ready template."
tags: [demand gen, metrics, pipeline reporting, b2b paid media]
audience: Head of Demand Gen
canonical_url: https://www.yirla.com/blog/demand-gen-metrics-that-matter-predict-revenue
---

The demand gen metrics that actually predict revenue are pipeline velocity, cost per pipeline dollar, win rate by source, sales-accepted rate, engagement depth in target accounts, and time-to-close by campaign cohort — not the dozen activity metrics most teams report out of habit. If your team tracks fifteen numbers a month and leadership still asks "so is this working," the problem isn't effort. It's metric selection.

## Why Don't Most Demand Gen Dashboards Predict Revenue?

Most B2B dashboards are built to make marketing look busy, not to help the business make decisions. Leads generated, cost per lead, impressions, click-through rate, email open rate — all of it moves, and none of it reliably predicts whether you're going to hit pipeline. These numbers are easy to collect and easy to report: MQLs feel like progress because the number goes up, clicks feel like traction, impressions feel like reach. Nobody gets fired for a slide where every bar trends upward, even when nothing downstream is moving.

Activity metrics count things happening. Engagement metrics measure response. Both feel like progress. Neither reliably predicts revenue on its own. True leading indicators are the metrics that, historically, moved before pipeline did — and moved in the same direction consistently enough to trust.

## What KPIs Actually Predict Pipeline and Revenue?

| Metric | What it measures | Why it predicts revenue |
|---|---|---|
| **Pipeline velocity** | (Qualified opportunities × avg. deal size × win rate) ÷ avg. sales cycle length | A drop shows up 2–3 months before it hits the topline number |
| **Cost per pipeline dollar** | Marketing spend ÷ pipeline generated | Connects spend to pipeline instead of activity; surfaces real channel efficiency |
| **Win rate by source** | Closed-won rate segmented by lead source | Aggregate win rate hides which channels reach in-market buyers |
| **Sales-accepted rate** | % of marketing-sourced pipeline sales actually works | A low or declining rate predicts a revenue miss regardless of lead volume |
| **Engagement depth in target accounts** | Stakeholders and distinct interactions per account, not just whether an account engaged once | Depth correlates with close rate far more than breadth does |
| **Time-to-close by campaign cohort** | Average days to close, segmented by originating campaign | A cohort closing faster than baseline is pulling better-qualified buyers |

Win rate by source matters more than it looks: per LinkedIn's B2B Institute, only about 5% of your total addressable market is actively in-market at any given moment, which makes close rate by source one of the sharpest signals for identifying which channels reach in-market buyers versus people who fill out a form and disappear.

## How Do You Instrument These Metrics in HubSpot and Salesforce?

Both platforms can surface all six metrics without a custom data warehouse — it just requires intentional setup that most teams skip.

| Metric | HubSpot | Salesforce |
|---|---|---|
| Pipeline velocity | Deal-based report using Deal Amount, Close Date, Create Date, and the "Days to Close" property; filter Deal Stage for win rate | Native Opportunity pipeline report with the same fields; track as a time series to spot trend changes weekly |
| Cost per pipeline dollar | Pull spend from the Campaigns tool (or import), divide against pipeline tied to that campaign | Campaign Influence model handles this natively if campaigns are set up correctly |
| Win rate by source | "Original Source" or "Latest Source" on the contact, joined to deal records, filtered Closed Won vs. Closed Lost | "Lead Source" field on the Opportunity object, natively |
| Marketing-sourced pipeline % | Pipeline report filtered to deals whose contact source matches marketing channels, divided by total pipeline | Campaign Influence, with first-touch vs. multi-touch decided up front |
| Time-to-close by cohort | "Original Source Drill-Down" properties to reach the campaign level | Campaign Member records tied to Opportunities |

The common failure mode across every row: data hygiene. If 40% of your deals have "Other" or a blank lead source, a win-rate-by-source report is meaningless — fix the tagging upstream before you trust any of these numbers.

## How Do You Build a Board-Ready Scorecard Leadership Will Actually Read?

One page. Trend lines, not single-point snapshots — a number without direction tells you almost nothing. Structure it around four questions and nothing else:

1. **What did marketing contribute to pipeline this quarter, in dollars?** State marketing-sourced pipeline and what share of total company pipeline it represents.
2. **Are we generating pipeline more or less efficiently than last quarter?** Cost per pipeline dollar, current quarter vs. the previous two, so the trend is visible.
3. **Which channels are producing pipeline worth closing?** Win rate by the top three or four sources — not all channels, not an aggregate.
4. **What are we doing differently next quarter based on this data?** One or two bullets: reallocations, tests being cut, bets being increased.

One framework worth naming here: the **3-Metric Rule**. If a KPI can't be explained in one sentence and doesn't move before revenue does, it doesn't belong on the leadership scorecard.

## How Do You Retire Vanity Metrics Without Losing Team Buy-In?

Don't cut them cold. Move them to an appendix for one full quarter while the new scorecard runs in parallel, so the team can see the new metrics hold up before the familiar ones disappear. Frame the change around what the team gains — less time building reports nobody reads, more credibility in budget conversations — rather than what they're losing.

As we've written before, [the MQL is a comfortable lie](https://www.yirla.com/blog/the-mql-is-a-comfortable-lie): it feels like accountability, but it isn't. And as we've covered in depth, [closed-won is the only vanity metric worth chasing](https://www.yirla.com/blog/closed-won-is-the-only-vanity-metric-worth-chasing). The six metrics above get you there faster.

## FAQ

**What demand gen metrics actually predict revenue?**
Pipeline velocity, cost per pipeline dollar, win rate by source, sales-accepted rate, engagement depth in target accounts, and time-to-close by campaign cohort.

**What's the difference between activity metrics and leading indicators?**
Activity metrics count things happening, like emails sent or ads served. Leading indicators are metrics that historically move before pipeline and revenue do.

**How do you calculate pipeline velocity?**
(Number of qualified opportunities × average deal size × win rate) ÷ average sales cycle length.

**How do you get a team to stop tracking vanity metrics?**
Run the new and old metrics in parallel for a quarter before retiring the old ones, so the team sees the new scorecard hold up first.

**What's the 3-Metric Rule?**
If a KPI can't be explained in one sentence and doesn't move before revenue does, it doesn't belong on a leadership scorecard.

---

See the metrics that actually move pipeline surfaced automatically, including cross-platform pipeline attribution by campaign. [Start a Yirla trial](https://www.yirla.com/pricing).
