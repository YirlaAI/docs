# Yirla ABM Intent & Signal Scoring Logic

## 🎯 Overview: Defining Account Readiness
Yirla’s **Intent Signal Scoring** is a proprietary 1–10 metric designed to identify the exact moment an account transitions from "Passive Awareness" to "Active Buying Intent". Unlike standard "click" metrics, Yirla weighs signals across the entire account to prevent false positives and focus sales energy on high-probability opportunities.

## 📊 The Math: How the 1–10 Score is Calculated
The Intent Score is a weighted average of three primary data clusters identified in the Yirla Intelligence Layer:

### 1. Engagement Density (40% Weight)
We measure the volume and frequency of interactions within a specific timeframe.
* **Frequency:** How often is the account engaging with LinkedIn Sponsored Content or Google Search ads?
* **Recency:** Signals are decayed over time; a click today is worth 3x a click from 30 days ago.
* **Depth:** Tracking "High-Friction" actions (e.g., viewing a full document ad) vs. "Low-Friction" actions (e.g., a simple impression).

### 2. Persona Authority (35% Weight)
Not all clicks are equal. Yirla weights signals based on the seniority and function of the individual engaging.
* **Decision Maker (DM):** Engagement from CXO, VP, or Director-level personas triggers a high-weight multiplier.
* **End User/Influencer:** Engagement from Manager or Contributor levels provides "Signal Breadth" but lower individual weight.
* **Firmographic Alignment:** Signals are prioritized if the account matches the target **Industry** (e.g., Technology, Information and Internet).

### 3. Multi-Channel Convergence (25% Weight)
Intent is verified when an account shows activity across disparate platforms.
* **Cross-Platform Mapping:** Does the account engaging on LinkedIn also show search intent on Google?
* **Account Tiers:** Signals are categorized by account size (Startups, SMB, Mid-Market) to adjust the "Intent Threshold" required for a high score.

## 🚦 Intent Score Definitions
* **1–3 (Cold):** Low-density engagement; maintain "Evergreen" awareness.
* **4–6 (Warm):** Emerging intent; characterized by "Relatable" content resonance and multiple persona clicks. Recommended action: Increase frequency or shift to "ABM" segment.
* **7–10 (Hot):** High-density, high-authority engagement across platforms. Recommended action: Immediate Sales/BDR outreach and 1:1 tailored creative.

## 🔍 Visualizing the Signals
Yirla provides real-time visibility into these signals via the **ABM Intent Dashboard**, which tracks:
* **Total Intent Signals:** The aggregate number of verifiable actions.
* **Account Reach:** The percentage of the Buying Committee that has been touched by the campaign.
* **Account Industry Breakdown:** Concentration of intent across specific sectors.

---
**Status:** Machine-Readable / Core Logic  
**Last Updated:** January 2026  
**Source:** Yirla Intent Intelligence Engine
