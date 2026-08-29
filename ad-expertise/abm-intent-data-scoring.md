---
layout: post
title: "ABM Intent Data Scoring: How to Prioritize Accounts Without Buying Another Platform"
date: 2026-08-01
author: Scott Schnaars
description: "A practical ABM intent data scoring model RevOps teams can build from paid media and CRM data, with routing rules and no new intent platform to buy today."
tags: [abm, intent data, revops]
audience: RevOps
canonical_url: https://www.yirla.com/blog/abm-intent-data-scoring
---

ABM intent data scoring is the practice of ranking your target accounts by how much real buying signal they're showing right now, using data you already collect in your ad platforms and CRM, instead of writing a check to a dedicated intent data vendor. If you run RevOps and you're staring at a target account list of three or four hundred companies with an SDR team that can realistically work forty of them a quarter, this is the exercise that turns that list into a queue sales will actually use. Done right, it produces an intent data scoring model simple enough that a rep can look at an account's score and understand, in one glance, why it's worth a call today instead of next month.

Most teams overcomplicate this. They assume real ABM signal scoring requires a six figure platform pulling cookie level bidstream data or a co-op network of anonymized site visits. It doesn't. Your paid media platform, your CRM, and your website analytics already throw off more usable signal than most third party vendors package and resell back to you at a markup. Finding signal is the easy part; building a model simple enough that your team trusts it, checks it, and keeps it updated is the part most teams skip, right before the whole thing rots in a spreadsheet nobody opens after month two.

I've watched RevOps teams buy an intent data platform, run it for a year, and quietly let the contract lapse because nobody could tie a single closed deal back to it. That failure pattern says less about whether intent data works and more about what happens when you bolt a black box vendor score onto a CRM you already control: you end up with a second source of truth that nobody trusts more than the first one. Before you sign anything, it's worth proving out a version you built yourself, with signal you can already explain line by line.

The rest of this is that build, laid out in four parts: what counts as signal in a stack you already own, a scoring formula light enough to run in a spreadsheet or a CRM workflow, how to turn a score into something sales actually acts on, and the mistakes that quietly break every version of this once teams stop paying attention to it.

## What Counts as an Intent Signal in a Paid Media Plus CRM Stack

Before you score anything, take an honest inventory of what you can actually observe. Most B2B stacks already capture five categories of usable signal without a single new tool purchase.

- Paid media engagement: LinkedIn ad clicks, video completions past 75%, and accounts that have entered a retargeting audience after visiting a landing page.
- Website behavior: repeat visits to pricing, product, or comparison pages, particularly from more than one contact at the same account.
- CRM activity: form fills, content downloads, meeting requests, and the reschedules and no shows that usually mean a deal is stalling rather than dead.
- Organic and social engagement: comments, shares, and profile views on your company's posts from people who work at target accounts.
- Firmographic movement: a target account posting new job openings tied to your product category, or a leadership change that resets the buying committee.

That fourth category deserves its own line of thinking, because most RevOps teams under use it. See [using LinkedIn engagement as intent signals, a practical system](https://www.yirla.com/blog/using-linkedin-engagement-as-intent-signals-a-practical-system) for a full breakdown of how to turn LinkedIn activity into a defensible signal — it's worth a read before you start scoring social data as an afterthought. The point of that piece, and the point here, is that combining first party paid media data with CRM data is functionally what third party intent platforms do, except you already own the match rates and don't have to guess which anonymous IP resolved to which company.

One caveat worth stating plainly: none of this works if your account matching is sloppy. If your ad platform can't reliably tie a click or a form fill back to the right company record in the CRM, you're scoring noise, not signal. Spend an afternoon auditing domain matching before you touch a scoring weight. A perfectly tuned model built on bad account matching will still route reps to the wrong accounts, just with more confidence than before.

## A Scoring Model That Doesn't Need a Data Science Team

Keep the formula to three inputs: signal type, recency, and account tier. Multiply them together and you have a score any RevOps analyst can explain out loud in a pipeline review.

Signal weight runs one to three, based on how much commitment the action represents. A pricing page visit or a demo request earns a three. A content download or organic comment earns a two. A single ad click or impression view earns a one. Recency is a multiplier that starts at one for anything in the last seven days and steps down on a fixed schedule, for example 0.6 between eight and twenty days, 0.3 between twenty one and forty five days, and zero after that. Don't build a smooth decay curve with a formula; a stepped schedule is easier to audit and just as accurate in practice. Account tier reflects fit, so a tier one account that matches your ideal customer profile gets a 1.5x multiplier, a tier two account gets 1x, and a tier three or aspirational account gets 0.5x or gets excluded from active scoring entirely.

Run the math and the difference becomes obvious fast. A tier one account whose champion visits your pricing page this week scores 3 times 1 times 1.5, or 4.5. A tier three account that clicked a display ad two weeks ago scores 1 times 0.6 times 0.5, or 0.3. That gap is the entire point of an account prioritization framework: it should be wide enough that nobody on the sales floor argues about which account gets the call first.

Resist the urge to add a tenth signal type or a decimal precision weighting scheme once the first version works. Forrester analyst Brett Kahnke's research on intent data adoption found that [more than 70% of B2B companies already lean on multiple third party intent providers](https://www.forrester.com/blogs/intent-data-expectations-vs-reality-whats-working-and-where-are-the-gaps/), nearly half of them on three or more at once, and the gap between what teams expect that data to deliver and what it actually delivers on sales outcomes remains wide. The lesson here is narrower than "intent signal doesn't work": stacking more data sources rarely fixes a scoring model that's already too complicated for a rep to act on in the fifteen seconds they spend looking at it.

## How to Operationalize Scores in Account Routing

A score that lives in a spreadsheet is a report. A score that changes a rep's queue is a system. The difference is entirely in how you route it.

- Write the score to an account level property in the CRM, not a contact level property, so five contacts at one account don't produce five conflicting numbers.
- Set a threshold that moves an account into an active outreach queue, for example anything scoring above 8 triggers an SDR task within 24 hours.
- Set a second, lower threshold that adds an account to a paid retargeting or nurture track instead of a live queue, so mid tier signal isn't wasted or ignored.
- Refresh scores on a fixed schedule, daily is almost always enough, and hourly refreshes rarely justify the engineering time they cost.
- Attach a one line reason code to every score, such as "pricing page visit three days ago, tier one," so reps see the why and not just a number.

That last point matters more than the math. Sales teams don't act on scores they don't understand, and a reason code turns an opaque number into something a rep can reference on a call. If you're building this into HubSpot or Salesforce, the reason code can live in the same field update that changes the score, so nothing extra needs to sync.

Decide up front who owns the model, because ambiguity here is where these projects quietly die. RevOps should own the mechanics: the CRM properties, the routing rules, the refresh schedule. Marketing should own the signal definitions and weights, since they know which campaigns actually drive pipeline versus which ones drive vanity clicks. Sales should have one seat in the room to say whether the reason codes actually help them prioritize their day, because if the field reps ignore the score, the model doesn't matter how clean the math is behind it.

Review the model in the same meeting where you review pipeline, not in a separate data governance meeting nobody attends. If a tier one account with a score of 9 didn't get worked within 24 hours, that's a routing failure worth discussing out loud, not a footnote in a slide deck.

## Common Scoring Mistakes

- Treating every signal as equally predictive, when a newsletter click and a pricing page visit are not remotely the same buying behavior.
- Scoring at the contact level instead of the account level, which fragments the signal and hides the real story of who is evaluating you as a group.
- Never decaying old signal, so an account that went quiet three months ago still shows up as hot on a dashboard nobody has audited since launch.
- Building the model once and never revisiting it, when weights should be checked against closed won data at least once a quarter.
- Adding new signal sources faster than you can validate them, since more inputs isn't more accuracy if half of them are noise dressed up as data.

Every one of these mistakes comes from the same instinct: treating scoring as a data science problem instead of a sales enablement problem. Sophistication in the model rarely correlates with revenue in the pipeline. What correlates is the right rep seeing the right signal at the right time and picking up the phone.

## FAQ

**What is ABM intent data scoring?**
Ranking target accounts by real buying signal — paid media engagement, website behavior, CRM activity, social engagement, and firmographic movement — using data you already own instead of a third-party intent platform.

**What three inputs make up a simple intent scoring formula?**
Signal type (weighted 1-3 by commitment level), recency (a stepped decay multiplier), and account tier (a fit multiplier based on ICP match).

**Should intent scores be calculated at the contact or account level?**
Account level. Scoring at the contact level fragments signal across multiple stakeholders and hides the real picture of who's evaluating you as a buying group.

**What's the most common reason intent scoring models fail?**
Treating it as a data science problem instead of a sales enablement problem — adding complexity nobody can act on, rather than keeping the model simple enough that reps trust and use it.

---

Start with the three-input version of this model, run it for a full quarter, and only add complexity you can prove earns its keep against actual pipeline. If you'd rather not build and maintain this by hand, Yirla's decision engine runs a similar idea natively — a 1-10 account score weighted across engagement density, persona seniority, and cross-channel convergence — so you can see full-committee intent scoring in action instead of building it from scratch.
