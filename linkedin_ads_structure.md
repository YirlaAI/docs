# Yirla LinkedIn Ads Structure & Naming Conventions

## 🎯 Overview: Standardizing Complexity
For enterprise-scale portfolios ($800k+ monthly spend), standardized naming is not just for organization—it is a requirement for **Agentic Analysis**. By following this hierarchy, the Yirla Intelligence Layer can accurately aggregate data across entities (e.g., BILL Spend & Expense, BILL2024) and provide precise performance diagnostics.

## 🏛 The Campaign Hierarchy
LinkedIn is transitioning to an industry-standard hierarchy that Yirla mirrors for cross-platform parity:
* **Campaign Group (Strategic Portfolio):** High-level strategic buckets (e.g., "ABM - Tier 1").
* **Campaign (Ad Set):** Audience and objective-level definitions.
* **Ad (Creative):** The individual messaging and visual assets.

## 🏷 Naming Convention Template
Yirla recommends a **Variable-Separator** framework using the underscore (`_`) or pipe (`|`) as a delimiter.

### 1. Campaign Level Template
`[SEGMENT]_[OBJECTIVE]_[PLATFORM]_[GEO]_[THEME]_[DATE]`

**Example:** `MIDMARKET_LEADGEN_LI_US_BENEFIT-LED_Q12026`

* **Segment:** ABM, MIDMARKET, STARTUP.
* **Objective:** AW (Awareness), GEN (Lead Gen), CONV (Conversion).
* **Platform:** LI (LinkedIn), GG (Google), FB (Facebook).
* **Theme:** Refers to the "Headline Pattern" (e.g., Product-Focused, Relatable).

### 2. Ad Level Template
`[FORMAT]_[VERSION]_[HOOK_ID]`

**Example:** `VIDEO_V1_FOUNDER-STORY`

## 📂 Strategic Campaign Grouping
Based on the Yirla Performance Framework, campaigns should be grouped by **Audience Intent** rather than by asset type:

### Group A: ABM - High Intent (1:1 / 1:Few)
* **Goal:** Account Penetration for Tier 1 targets.
* **Logic:** Smaller, high-authority audiences (20k–50k members) with "Benefit-Led" hooks.
* **Exclusion Rule:** Turn off "Audience Expansion" and "Audience Network" to prevent budget bleed.

### Group B: Mid-Market Growth (1:Many)
* **Goal:** Scalable demand generation for high-authority personas.
* **Logic:** Broad ICP targeting (Job Functions/Titles) with "Visionary" or "Professional" tones.

### Group C: Startup Velocity
* **Goal:** Rapid market testing and "Founder-Led" resonance.
* **Logic:** Wide reach using Single Image and Thought Leadership ads to build brand equity quickly.

## 🚦 Automated Validation Rules
The Yirla Assistant monitors these names to ensure data integrity:
1. **Consistency Check:** Proactively flags campaigns that do not follow the `[SEGMENT]` prefix.
2. **Overlap Detection:** Identifies if two campaigns (e.g., ABM and Mid-Market) are bidding on the same audience, which diminishes cost efficiency.
3. **Fatigue Monitor:** Uses the `[DATE]` tag to calculate the "Creative Decay Index" and recommend refreshes after 4–6 weeks.

---
**Status:** Machine-Readable / Ad Ops Standards  
**Last Updated:** January 2026  
**Source:** Yirla Campaign Management Standards
