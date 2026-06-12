---
layout: post
title: "Demand Gen Metrics That Actually Predict Pipeline: A B2B Framework"
date: 2026-06-12
author: Scott Schnaars
description: "The 5 demand gen metrics that predict pipeline in B2B SaaS: pipeline velocity, cost per pipeline dollar, win rate by source. Plus a board-ready template."
tags: [demand-gen, pipeline, metrics, b2b-saas, marketing-analytics, hubspot, salesforce]
audience: CMO
canonical_url: https://www.yirla.com/blog/demand-gen-metrics-predict-pipeline
---

Here's the uncomfortable truth about most B2B marketing dashboards: they were built to survive budget reviews, not to drive revenue decisions. Thirty metrics, all moving in the right direction, none of them connected to whether the quarter closes.

This isn't a technology problem. Every data point you need exists in HubSpot or Salesforce today. It's a prioritization problem. The wrong metrics got promoted to the top of the dashboard, and the ones that actually matter got buried in an appendix nobody reads.

What follows is a framework for fixing that, built around the five metrics that reliably predict pipeline in B2B SaaS.

---

## The Vanity Metric Trap

Vanity metrics persist for a simple reason: they move. MQLs go up. Impressions go up. Click-through rates can be optimized. When leadership asks how marketing is doing, there's always a chart that looks good.

The problem is that none of these metrics answer the question leadership is actually asking, which is: are we going to hit pipeline? MQL volume doesn't answer that. Neither does CPL, reach, or engagement rate. These metrics measure activity, and activity is not pipeline.

Most marketing teams inherited this reporting structure from a different era, when attribution was nearly impossible and the funnel was assumed to be linear. The model rewarded volume because volume was the only thing measurable. Dashboards were designed around what was easy to collect, not what was useful to decide.

As covered in our post on [why the MQL is a comfortable lie](https://www.yirla.com/blog/the-mql-is-a-comfortable-lie), the metric feels like accountability. It isn't. Here are the five that are.

---

## Five Metrics That Actually Predict Pipeline

### Pipeline Velocity

Pipeline velocity answers the question: how fast is qualified revenue moving through your funnel? The formula is straightforward: multiply the number of qualified opportunities by average deal size and win rate, then divide by average sales cycle length. The result is a dollar-per-day (or dollar-per-week) figure that tells you whether your pipeline machine is accelerating or stalling.

What makes this metric predictive rather than descriptive is its sensitivity. A drop in pipeline velocity shows up weeks before it shows up in a missed quarter. It also tells you *where* the breakdown is. Stalling deals point to a sales problem. Shrinking deal size points to a targeting problem. A longer cycle points to a qualification problem. Aggregate MQL numbers can't do that.

Track it weekly. Three consecutive weeks of decline is an action signal, not a data point to note for the quarterly review.

### Cost Per Pipeline Dollar

Most demand gen teams optimize for cost per lead. The right metric is cost per pipeline dollar: how much did you spend to generate one dollar of qualified pipeline? Divide total marketing spend by total pipeline generated in the same period.

This forces a connection between spend and business outcome, not spend and activity. It also immediately surfaces channel efficiency in a way CPL cannot. If LinkedIn has a lower CPL than paid search but LinkedIn-sourced deals convert to pipeline at half the rate, your cost per pipeline dollar from LinkedIn is twice as high. CPL was telling you to spend more on the wrong channel.

### Win Rate by Source

Reporting win rate in aggregate is essentially useless. A 22% overall close rate tells you nothing about where to put the budget. Win rate broken down by lead source tells you everything.

According to [LinkedIn's B2B Institute](https://business.linkedin.com/marketing-solutions/b2b-institute), at any given moment only roughly 5% of your total addressable market is actively in-market. That makes close rate by source one of the clearest signals available for distinguishing which channels are reaching buyers with actual intent versus channels generating form fills from people who will never talk to sales.

If your content-sourced deals close at 31% and paid social closes at 14%, that's a reallocation signal. If one ABM cohort is closing at 40% and everything else is at 18%, that cohort is a proof of concept for a bigger bet.

### Marketing-Sourced Pipeline Percentage

What share of your total pipeline originated from a marketing touch? This is the most important number for justifying the marketing budget, and most teams either don't track it or track it inconsistently.

The attribution model debate (first-touch versus last-touch versus multi-touch) is real but secondary. What matters more is consistency. Pick a model and use it quarter over quarter so comparisons are meaningful. A 38% marketing-sourced pipeline number is only useful if last quarter's comparison uses the same attribution logic.

This metric also gives you a defensible answer to the CFO question. "What did marketing contribute this quarter?" should be answered with a dollar amount and an attribution model, not impressions and MQLs.

### Time-to-Close by Campaign Cohort

This is the one that gets missed most consistently. Average sales cycle length is a useful baseline, but the predictive signal is in the deviation. Deals sourced from a branded search campaign close faster than the company average. Deals from top-of-funnel display campaigns close slower. Deals from a specific event cohort might take 90 days when the baseline is 70.

Each deviation is a signal about the quality of intent behind the source. And if you're treating all pipeline equally in your forecast regardless of source, that's why your forecasts are consistently wrong.

---

## Instrumentation in HubSpot and Salesforce

None of these metrics require a custom data warehouse. They all exist within the platforms most B2B SaaS teams already use.

**Pipeline velocity** is a calculated metric. In HubSpot, use a deal-based report combining Deal Amount, Days to Close, and close rate (Closed Won vs. total). In Salesforce, Opportunity reports with cycle length calculations work the same way. The goal is a time-series view so week-over-week trend is visible.

**Cost per pipeline dollar** requires connecting spend data to pipeline data. In HubSpot, import campaign spend into the Campaigns tool and tie it to deals via contact source attribution. In Salesforce, Campaign Influence handles this natively when campaigns are set up correctly. UTM parameter consistency across all channels is the prerequisite that makes this work in either platform.

**Win rate by source** is built in HubSpot using the Original Source or Latest Source contact property joined to deal records, filtered by Closed Won versus Closed Lost. In Salesforce, the Lead Source field on the Opportunity object does the same thing natively. The data hygiene caveat: if 40% of your deals show "Other" or blank in the source field, fix that before you run the report.

**Marketing-sourced pipeline percentage** in HubSpot is a pipeline report filtered to deals where the contact's original source is a marketing channel. In Salesforce, Campaign Influence is the right model. In both cases, you're dividing marketing-sourced pipeline by total pipeline to get the percentage.

**Time-to-close by cohort** requires consistent campaign tagging at the source level. In HubSpot, use Original Source Drill-Down properties to get to campaign granularity. In Salesforce, Campaign Member records tied to Opportunities accomplish the same thing. The upstream requirement is UTM discipline: every paid, content, and event program needs consistent tagging for the downstream report to be meaningful.

---

## A Four-Question Board Report

The quarterly marketing slide to leadership should answer exactly four questions. If it answers more than four, it answers none.

- **What did marketing contribute to pipeline this quarter, in dollars?** State marketing-sourced pipeline total and its percentage of total company pipeline;
- **Are we generating pipeline more or less efficiently than last quarter?** Cost per pipeline dollar, three quarters in view, so the trend is visible;
- **Which channels are producing pipeline worth closing?** Win rate by top three to four sources. Not aggregate. The ones that matter;
- **What are we doing differently next quarter based on this data?** One or two bullets: reallocation decisions, tests being shut down, bets being increased.

One page. No appendix unless leadership asks. If a question comes up that these four data points can't answer, the response is to add that measurement to the system, not to add more slides.

The goal isn't a better presentation. It's a shared understanding of what moving the business actually looks like. As we've covered before, [closed-won is the only vanity metric worth chasing](https://www.yirla.com/blog/closed-won-is-the-only-vanity-metric-worth-chasing). This framework gets you there.

---

## The Bottom Line

You don't have a metrics problem. You have a prioritization problem. The five metrics in this framework exist in your CRM today. The reason most teams aren't using them is that nobody stopped to ask which numbers actually predict whether the quarter closes, versus which numbers are easy to collect and safe to put in front of leadership.

Start with pipeline velocity and win rate by source. Add cost per pipeline dollar once your spend attribution is clean. Build the four-question board report and drop three existing dashboard metrics for every one you add.

[Yirla](https://www.yirla.com) surfaces these metrics across your paid channels automatically, with cross-platform pipeline attribution by campaign. If you're spending on LinkedIn, Google, and programmatic and still building attribution in a spreadsheet, that's the problem it was built to solve.
