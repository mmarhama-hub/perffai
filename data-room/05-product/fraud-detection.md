# Fraud Detection — MENA-Specific Protection

---

## The MENA Fraud Problem

Affiliate marketing fraud costs the industry $3.4B globally per year. In MENA, the problem is **disproportionately worse** due to:

| Factor | Description | MENA Impact |
|---|---|---|
| **VPN Prevalence** | High VPN usage across the region masks true user geography | Enables geo-spoofing (traffic appearing as UAE but originating from low-value geos) |
| **Click Farms** | Organized operations in neighboring markets generate fake clicks | 3–5× higher click fraud rates than NA/EU |
| **Bot Sophistication** | Bots designed to mimic mobile user behavior on Arabic sites | Hard to distinguish from real users |
| **Attribution Manipulation** | Last-click hijacking via cookie stuffing and click injection | Inflates publisher commissions fraudulently |
| **Limited Tools** | Global fraud solutions not trained on MENA patterns | Miss 40%+ of regional fraud |

### Cost to Brands

Without MENA-specific fraud protection, brands lose an estimated **15–25% of affiliate spend** to fraudulent conversions. For a brand spending $100K/month on affiliates, that's $15K–$25K wasted monthly.

---

## Perff AI's Fraud Detection System

### Architecture

```
INCOMING TRAFFIC
       │
       ▼
┌──────────────────┐
│  Signal Capture  │ ← 50+ signals per event
│  (Click/Conv)    │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Real-Time       │ ← IP, device, geo, behavior
│  Enrichment      │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Rule Engine     │ ← Known fraud patterns (deterministic)
│  (Layer 1)       │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  ML Scoring      │ ← Probabilistic fraud score (0–100)
│  (Layer 2)       │
└────────┬─────────┘
         │
    ┌────┴────┐
    │         │
    ▼         ▼
  PASS      BLOCK
(score<40) (score>70)
    │
    ▼
  REVIEW    ← Manual review queue (score 40–70)
```

### Signal Categories

#### Device Signals
- Device fingerprint (hardware, OS, browser combination)
- Screen resolution and language settings
- JavaScript execution patterns
- WebGL renderer information
- Battery API inconsistencies (bots)

#### Network Signals
- IP address reputation score
- VPN/proxy/TOR detection
- ISP classification (residential vs. datacenter)
- Geo-IP vs. timezone consistency
- IPv4/IPv6 analysis

#### Behavioral Signals
- Click-to-conversion time (suspiciously fast = bot)
- Session depth and page view patterns
- Mouse movement / touch interaction patterns
- Scroll behavior analysis
- Form fill speed and patterns

#### Attribution Signals
- Click velocity (too many clicks in short window)
- Cookie age analysis (freshly injected vs. natural)
- Referrer chain validation
- Sub-ID pattern analysis
- Duplicate conversion detection

#### MENA-Specific Signals
- Arabic browser language consistency
- MENA ISP fingerprint database
- Regional VPN provider detection
- Cross-border traffic patterns (e.g., traffic claiming UAE but ISP from neighboring country)
- Ramadan/weekend traffic pattern validation

---

## ML Model Details

### Training Data
- **2M+ labeled fraud events** from 250+ MENA campaigns
- Human analysts labeled 500K+ borderline cases for ground truth
- Continuous feedback loop: analyst decisions retrain model weekly

### Model Architecture
- **Ensemble model**: Gradient Boosted Trees (XGBoost) + Neural Network
- XGBoost handles structured signals (IP, device, timing)
- Neural network handles sequential behavior patterns
- Ensemble voting for final fraud score

### Performance Metrics

| Metric | Perff AI (MENA) | Industry Average | Global Tools on MENA |
|---|---|---|---|
| **Detection Rate** | 95.3% | 85% | 55–60% |
| **False Positive Rate** | 4.2% | 8–12% | 15–20% |
| **Precision** | 93.1% | 82% | 65% |
| **Recall** | 95.3% | 85% | 55% |
| **F1 Score** | 0.942 | 0.835 | 0.598 |
| **Latency** | <100ms | 200–500ms | 300ms+ |

---

## Fraud Types Detected

| Fraud Type | Description | Detection Method |
|---|---|---|
| **Click Fraud** | Fake clicks to inflate publisher metrics | Click velocity + IP analysis |
| **Conversion Fraud** | Fake conversions to earn commissions | Behavioral analysis + device fingerprint |
| **Cookie Stuffing** | Injecting affiliate cookies without user action | Cookie age + referrer validation |
| **Click Injection** | Mobile apps fire clicks before conversion | Install-to-click time analysis |
| **Geo Masking** | VPN to fake high-value geography | VPN detection + locale consistency |
| **Click Farms** | Organized human clicking operations | IP clustering + behavioral uniformity |
| **Bot Traffic** | Automated browsing to generate traffic | JS challenge + interaction patterns |
| **Attribution Theft** | Stealing credit for organic conversions | Attribution chain analysis |
| **Incent Fraud** | Incentivized traffic disguised as organic | Conversion quality scoring |
| **Device Farms** | Multiple apps on one device simulating users | Device fingerprint clustering |

---

## Fraud Detection v2 (Under Development — Q3 2026)

### Enhancements

1. **Graph-Based Network Detection**
   - Build relationship graphs between publishers, IPs, devices, and conversion events
   - Detect fraud rings: multiple publishers controlled by same entity
   - Identify shell publishers created solely for fraud

2. **Behavioral Sequence Modeling**
   - LSTM neural network models full user session sequences
   - Detects bots that pass individual signal checks but fail on session-level behavior
   - Time-series anomaly detection for traffic pattern changes

3. **Cross-Campaign Intelligence**
   - Fraud detected in Campaign A automatically flags same publisher's traffic in Campaign B
   - Industry-wide fraud blacklists (anonymized, shared across brands)
   - Real-time publisher reputation scores

4. **Faster Learning Loop**
   - Analyst decisions retrain model within hours (not weeks)
   - Auto-generated fraud rules from analyst patterns
   - A/B testing framework for new detection algorithms

### v2 Performance Targets

| Metric | v1 (Current) | v2 (Target) |
|---|---|---|
| Detection Rate | 95.3% | 98%+ |
| False Positive Rate | 4.2% | <2% |
| New Fraud Type Response | ~2 weeks | <48 hours |
| Auto-Resolution Rate | 60% | 85% |

---

## Business Impact

| Impact Area | Metric |
|---|---|
| Revenue saved for brands | ~$2M cumulative across all campaigns |
| Fraudulent conversions blocked | ~150K in 2024 |
| Brand trust improvement | 87% retention (vs. 60–70% industry) |
| Time saved on manual review | ~200 hours/month automated |
| Publisher network quality | 95%+ clean traffic across active publishers |

---

© 2026 Perff AI (Perff Inc.). Confidential & Proprietary.
