# AI Capabilities

---

## AI Strategy

Perff AI's core competitive advantage is its **MENA-trained AI engine** — machine learning models built on 250+ MENA affiliate campaigns, trained on regional consumer behavior, Arabic content, and MENA-specific fraud patterns that no global competitor possesses.

Our AI strategy follows a **crawl → walk → run** approach:

| Phase | Timeline | Focus |
|---|---|---|
| **Foundation** (Crawl) | 2022–2024 | Data collection, basic automation, fraud detection v1 |
| **Intelligence** (Walk) | 2025–2026 | Predictive scoring, optimization, recommendation engines |
| **Autonomy** (Run) | 2027–2028 | Self-serve AI, autonomous campaign management, NLP |

---

## Live AI Features

### 1. Fraud Detection (MVP — Live)

**What it does:** Identifies and blocks fraudulent traffic in real-time before brands pay for invalid conversions.

**Why it matters for MENA:** The region has unique fraud patterns — VPN masking from neighboring countries, organized click farms, bot traffic disguised as mobile users. Global fraud tools miss ~40% of MENA-specific patterns.

**How it works:**
- Analyzes 50+ signals per click event (IP reputation, device fingerprint, behavioral patterns, geo-consistency, session duration, click velocity)
- ML model trained on 250+ MENA campaigns with labeled fraud data
- Real-time scoring: each click/conversion gets a fraud probability score
- Auto-blocks traffic exceeding configurable thresholds
- Continuous learning from new fraud patterns

**Results:**
- 95%+ fraud detection rate on MENA traffic
- <5% false positive rate
- Saves brands ~15% on campaign spend (blocked invalid conversions)
- 3× more effective than global fraud tools on MENA traffic

---

### 2. Predictive Campaign Scoring (Live)

**What it does:** Predicts campaign success probability before launch, helping brands optimize setup and publishers choose high-performing campaigns.

**How it works:**
- Scores campaigns 1–100 based on historical data from similar campaigns
- Features: vertical, commission structure, creative quality, target market, seasonality, publisher pool
- Recommends optimizations to improve score (adjust commission, change market, add creatives)

**Results:**
- Campaigns with score >70 convert 3.2× better than those below 50
- Reduces time-to-first-conversion by 40%
- 78% accuracy on conversion rate prediction (within ±20%)

---

### 3. Automated Reporting (Live)

**What it does:** Generates intelligent performance reports with AI-written insights and recommendations.

**How it works:**
- Aggregates campaign data across all dimensions (publisher, geo, device, time)
- ML model identifies patterns, anomalies, and trends
- Natural language generation produces human-readable insights
- Scheduled delivery (daily/weekly/monthly) via email

**Example Output:**
> "Campaign 'noon Summer Sale' saw a 23% conversion spike on mobile in KSA between 8-11pm. Top performer CouponMENA drove 34% of total conversions. Recommend increasing CouponMENA's commission tier and allocating 15% more budget to KSA mobile."

---

### 4. Budget Optimization (Live)

**What it does:** Dynamically allocates campaign budgets across publishers based on real-time performance.

**How it works:**
- Multi-armed bandit algorithm balances exploitation (top performers) and exploration (new publishers)
- Reallocates budget every hour based on conversion velocity, ROAS, and fraud rate
- Respects brand-set constraints (minimum/maximum per publisher, daily caps)

**Results:**
- 18% improvement in overall ROAS vs. static budget allocation
- 22% reduction in wasted spend on underperforming publishers
- Automatic pausing of publishers with declining performance

---

## Under Development

### 5. Multi-Layer Fraud Detection v2 (Building — Q3 2026)

**Enhancements over v1:**
- Graph-based detection: identifies fraud networks (publishers colluding with bots)
- Behavioral sequencing: models full user journeys, not just individual events
- Cross-campaign intelligence: fraud patterns in one campaign flag similar traffic in others
- Real-time feedback loop: human analyst decisions retrain model within hours
- Target: 98%+ detection rate, <2% false positive rate

---

### 6. Adaptive Budget Allocation (Building — Q4 2026)

**Beyond v1 optimization:**
- Multi-objective optimization (ROAS + volume + quality)
- Time-of-day and day-of-week optimization
- Seasonal pattern recognition (Ramadan, Black Friday, Singles Day)
- Publisher fatigue detection (diminishing returns on over-allocated publishers)
- Predictive budget forecasting for campaign planning

---

## Planned AI Features

### 7. Publisher Recommendation Engine (Planned — Q2 2027)

**What it will do:** Match brands with ideal publishers using collaborative filtering and content analysis.

- Analyze publisher audience demographics, content type, traffic quality, historical performance
- Score publisher-brand compatibility on a 0–100 scale
- Auto-invite high-match publishers to new campaigns
- Cold-start solution: onboard new publishers with similar-publisher performance estimates

---

### 8. Arabic NLP Engine (Planned — Q3 2027)

**What it will do:** Analyze Arabic content for brand safety, sentiment, and audience targeting.

- Arabic content classification for brand safety screening
- Sentiment analysis on Arabic social media mentions
- Keyword extraction from Arabic product reviews for SEO recommendations
- Dialect detection (Gulf, Levantine, Egyptian) for geo-targeting
- Bilingual content optimization (Arabic/English)

---

### 9. Self-Serve AI Assistant (Planned — Q4 2027)

**What it will do:** Natural language interface for campaign management and analytics.

- "Show me my top publishers in KSA for food delivery this Ramadan"
- "Why did my conversion rate drop last week?"
- "Set up a campaign like my best-performing one but for Egypt"
- "Recommend a commission structure for a fintech campaign"

---

## AI Data Moat

Perff AI's AI improves with every campaign, creating a **compounding data advantage**:

```
More Campaigns → More MENA Data → Better AI Models →
Higher CVR → More Brands → More Campaigns (repeat)
```

| Data Asset | Volume | Value |
|---|---|---|
| MENA click events | 50M+ | Behavioral patterns unique to region |
| Attributed conversions | 500K+ | Ground truth for ML training |
| Fraud-labeled events | 2M+ | MENA-specific fraud signatures |
| Publisher profiles | 870+ | Audience and quality scoring data |
| Campaign outcomes | 250+ | Campaign success/failure features |
| Arabic content corpus | 100K+ pages | NLP training data |

> **No global competitor has this dataset.** Building it from scratch would take 3+ years and require deep MENA network relationships.

---

© 2026 Perff AI (Perff Inc.). Confidential & Proprietary.
