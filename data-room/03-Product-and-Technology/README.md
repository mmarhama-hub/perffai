# 03 — Product & Technology

## Table of Contents
- [Platform Overview](#platform-overview)
- [AI Capabilities](#ai-capabilities)
- [Technology Architecture](#technology-architecture)
- [Product for Brands](#product-for-brands)
- [Product for Publishers](#product-for-publishers)
- [Competitive Technical Advantages](#competitive-technical-advantages)
- [Product Roadmap](#product-roadmap)
- [IP & Defensibility](#ip--defensibility)

---

## Platform Overview

Perff AI is a full-stack affiliate marketing platform purpose-built for MENA. It serves two primary user groups — **brands** (advertisers) and **publishers** (affiliates) — connected through an AI-powered marketplace with real-time tracking, fraud detection, and performance optimization.

### Platform Architecture (High-Level)

```
┌──────────────┐    ┌──────────────────┐    ┌──────────────────┐
│   BRANDS     │    │    PERFF AI       │    │   PUBLISHERS     │
│              │    │                  │    │                  │
│ Campaign Mgmt│◄──►│ Matching Engine  │◄──►│ Offer Marketplace│
│ Analytics    │    │ Fraud Detection  │    │ Tracking Links   │
│ Budget Ctrl  │    │ Attribution      │    │ Earnings Dash    │
│ AI Insights  │    │ Budget Optimizer │    │ AI Tips          │
│ Publisher LB │    │ Payments Engine  │    │ Payment History  │
└──────────────┘    └──────────────────┘    └──────────────────┘
```

---

## AI Capabilities

### Currently Live (Production)

| AI Feature | Description | Impact |
|-----------|-------------|--------|
| **Fraud Detection MVP** | Detects VPN-masked traffic, bot clicks, click farms, geo-mismatches, and cookie stuffing specific to MENA traffic patterns | Saves brands 15-30% on ad spend |
| **Predictive Campaign Scoring** | Scores campaigns before launch based on publisher mix, vertical, creative assets, and historical market data | Improves campaign ROAS by 20-40% |
| **Automated Reporting** | Real-time dashboards with AI-generated insights — anomaly detection, trend analysis, recommendations | Replaces manual Excel reporting |
| **Budget Optimization Engine** | Reallocates budget across publishers in real-time based on conversion performance | Increases overall ROAS by 15-25% |

### Planned (Post-Funding Development)

| AI Feature | Description | Timeline |
|-----------|-------------|----------|
| **Multi-Layer Fraud Detection v2** | Deep learning model combining behavioral biometrics, device fingerprinting, and traffic pattern analysis | Month 1-6 |
| **Adaptive Budget Allocation** | Reinforcement learning that autonomously manages brand budgets across publisher portfolio | Month 3-9 |
| **Publisher Recommendation Engine** | ML model that recommends high-match campaigns to publishers based on audience, content type, and geography | Month 3-9 |
| **Self-Serve Dashboard** | No-code campaign setup for SMB brands with AI-guided configuration | Month 6-12 |
| **API Platform** | RESTful API for agencies and enterprise clients to integrate Perff AI into their existing stack | Month 9-15 |
| **Natural Language Insights** | AI generates human-readable campaign summaries and recommendations in English and Arabic | Month 12-18 |

---

## Technology Architecture

### Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | React.js, TypeScript, Tailwind CSS |
| **Backend** | Node.js / Python (FastAPI for ML services) |
| **Database** | PostgreSQL (primary), Redis (caching), ClickHouse (analytics) |
| **ML/AI** | Python, scikit-learn, TensorFlow/PyTorch, custom fraud detection models |
| **Cloud** | AWS (primary) — EC2, S3, SageMaker, CloudFront |
| **Tracking** | Custom pixel-based tracking, server-to-server postbacks, mobile SDK |
| **Payments** | Custom multi-currency payout engine (AED, SAR, JOD, EGP, USD) |
| **Monitoring** | CloudWatch, Grafana, Sentry |

### Data Infrastructure

| Component | Scale |
|-----------|-------|
| **Daily tracking events** | 5M+ clicks/impressions processed |
| **Real-time attribution** | < 500ms conversion attribution latency |
| **Fraud scoring** | Real-time scoring on every click event |
| **Publisher data** | 870+ publisher profiles with performance history |
| **Campaign data** | 250+ campaigns with historical performance data |
| **Training data** | 3+ years of MENA-specific affiliate conversion data |

---

## Product for Brands

### Brand Dashboard Features

| Section | Functionality |
|---------|--------------|
| **KPI Overview** | Total spend, revenue generated, ROAS, conversions, active publishers, fraud savings |
| **Campaign Manager** | Create, edit, pause campaigns; set budgets, commission structures, targeting |
| **Publisher Leaderboard** | Ranked list of publishers by revenue, conversions, CVR — with AI recommendations |
| **Revenue & Spend Charts** | Interactive time-series charts with daily/weekly/monthly views |
| **Channel Breakdown** | Revenue by publisher type (coupon, content, social, comparison) |
| **AI Insights Panel** | AI-generated recommendations: budget reallocation, publisher suggestions, anomaly alerts |
| **Fraud Detection Panel** | Blocked clicks, flagged publishers, money saved, fraud type breakdown |
| **Reporting & Export** | Automated PDF/CSV reports, scheduled email digests |

### Campaign Types Supported

| Model | Description |
|-------|-------------|
| **CPS** (Cost per Sale) | Commission on completed purchases — most common for e-commerce |
| **CPA** (Cost per Acquisition) | Fixed fee per conversion — popular for fintech, insurance, real estate |
| **CPL** (Cost per Lead) | Fee per qualified lead — used for real estate (DAMAC), trading platforms |
| **Hybrid** | Base CPA + bonus for volume tiers |

---

## Product for Publishers

### Publisher Dashboard Features

| Section | Functionality |
|---------|--------------|
| **Earnings Overview** | Available balance, pending payments, monthly earnings, payment history |
| **Campaign Marketplace** | Browse available campaigns matched to publisher's profile and audience |
| **Tracking Links** | Generate, manage, and track performance of affiliate links |
| **Performance Analytics** | Clicks, conversions, CVR, earnings by campaign and time period |
| **AI Recommendations** | Campaign suggestions, content tips, audience insights |
| **Payment Center** | Payout settings, invoice generation, payment history |

### Publisher Types Supported

| Type | Examples |
|------|---------|
| **Coupon & Cashback** | Regional coupon websites, cashback platforms |
| **Content & Blog** | Review sites, comparison articles, niche blogs |
| **Social Media** | Instagram, TikTok, YouTube, Twitter/X affiliates |
| **Comparison Sites** | Price comparison, product aggregation |
| **Email & SMS** | Newsletter affiliates, SMS marketing |
| **Mobile Apps** | Cashback apps, deal alert apps |

---

## Competitive Technical Advantages

| Advantage | Detail |
|-----------|--------|
| **MENA-specific fraud models** | Trained on 3+ years of MENA traffic data — understands regional VPN usage, bot patterns, and fraudulent publisher behavior specific to GCC and Levant |
| **Arabic NLP** | Campaign content analysis and publisher content matching in Arabic and English |
| **Multi-currency payment engine** | Native support for AED, SAR, JOD, EGP, USD — automated cross-border payouts |
| **Regional attribution** | Understands MENA's multi-channel shopping behavior (social → web → app → in-store) |
| **Data moat** | 3+ years of MENA affiliate conversion data from 250+ campaigns and 870+ publishers — impossible for new entrants to replicate quickly |
| **Low-latency tracking** | Sub-500ms attribution across MENA — optimized for regional CDN and network conditions |

---

## Product Roadmap

### 2026

| Quarter | Development Priority |
|---------|---------------------|
| **Q1** | Multi-layer fraud detection v2; KSA onboarding infrastructure |
| **Q2** | Publisher recommendation engine; adaptive budget allocation MVP |
| **Q3** | Self-serve dashboard for SMB brands; mobile publisher app |
| **Q4** | API platform for agencies; Egypt market technical setup |

### 2027

| Quarter | Development Priority |
|---------|---------------------|
| **Q1** | Arabic NLP insights engine; advanced cohort analytics |
| **Q2** | Mobile SDK for in-app tracking; cross-device attribution |
| **Q3** | Agency white-label platform; Bahrain & Kuwait market setup |
| **Q4** | Predictive lifetime value scoring; advertiser self-optimization tools |

---

## IP & Defensibility

| Asset | Status |
|-------|--------|
| **Proprietary fraud detection model** | Trained on MENA-specific data — live in production |
| **Campaign scoring algorithm** | Predictive campaign ROI model — live in production |
| **Publisher matching engine** | AI-powered brand-publisher matching — live in production |
| **MENA affiliate dataset** | 3+ years of conversion, click, and fraud data across 9 verticals — growing daily |
| **Domain expertise** | Rima Hani: 10+ years MENA performance marketing; Fahad Alsaedi: tech leadership + 1× exit |
| **Network effects** | 870+ publishers and 50+ brands create a flywheel — each new participant increases value for all |

---

*Last updated: February 2026*
