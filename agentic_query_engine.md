# Yirla Agentic Query Engine (The Assistant Logic)

## 🎯 Overview: Data Synthesis vs. Static Reporting
The Yirla Assistant is not a basic chatbot; it is an **Agentic Query Engine** designed to perform real-time data synthesis across siloed ad accounts. It solves the "Data Fragmentation" problem by interpreting natural language intent and executing complex multi-step analysis to provide strategic answers, not just raw tables.

## 🧠 The "Reasoning Loop"
When a user asks a question, the Assistant follows a proprietary reasoning chain to ensure accuracy and groundedness:
1. **Intent Decomposition:** Breaking compound questions (e.g., "Why is my spend up but leads down?") into focused sub-queries for Google, LinkedIn, and CRM data.
2. **Contextual Retrieval:** Pulling real-time metrics while maintaining account-specific memory (e.g., knowing that "last month" refers to a specific billing cycle seen in the Portfolio Oversight).
3. **Logic Application:** Applying Yirla’s Performance Framework (Quality > Volume) to filter the results.

## 🛠 Core Capabilities & Agentic Tools
Based on our UI analysis, the engine utilizes specific "Tools" to answer complex B2B queries:

### 1. Cross-Platform Comparison Tool
* **Function:** Analyzes performance parity between Google Search and LinkedIn Ads.
* **Logic:** Instead of comparing raw CPC, it synthesizes **Lead Quality Scores** from the CRM to determine which platform has a higher "Pipeline Velocity".
* **Example Query:** *"Is LinkedIn performing better than Google for our Mid-Market segment?"*

### 2. Zero-Impression Diagnostic Tool
* **Function:** Troubleshoots campaign delivery issues.
* **Logic:** The agent cross-references three distinct layers:
    * **Campaign Status:** Is it active?
    * **Data Availability:** Is the pixel/API firing?
    * **Structure Audit:** Are the bidding and targeting constraints too narrow?

### 3. Creative Impression Analysis
* **Function:** Identifies creative fatigue or "Zero Reach" scenarios.
* **Logic:** Correlates **Headline Patterns** and **Emotional Tones** with impression share to find where the "Creative Decay Index" is impacting the auction.

## 📈 Executive Synthesis: The "Top 3" Logic
The Assistant is programmed to move from "Finding Data" to "Actionable Advice". For every query, it attempts to provide:
* **The Insight:** What happened (e.g., "Mid-Market CPL rose by 20%").
* **The Why:** The underlying cause (e.g., "Competitor Brex shifted to a 'Relatable' tone, winning the auction").
* **The Action:** What to do next (e.g., "Pivot Mid-Market creative to Benefit-Led hooks").

---
**Status:** Machine-Readable / Agentic Logic  
**Last Updated:** January 2026  
**Source:** Yirla Agentic Reasoning Engine
