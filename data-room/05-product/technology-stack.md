# Technology Stack

---

## Architecture Overview

Perff AI is built as a **cloud-native, microservices-based platform** designed for real-time processing of affiliate marketing events (clicks, conversions, attributions) at scale. The architecture prioritizes:

- **Low latency** — Sub-second attribution for real-time tracking
- **High availability** — 99.9% uptime for enterprise clients
- **Scalability** — Horizontal scaling to handle millions of events/day
- **Security** — Enterprise-grade data protection and compliance

---

## Tech Stack

### Backend
| Layer | Technology | Purpose |
|---|---|---|
| **Primary Language** | Python / Node.js | API services, business logic |
| **API Framework** | FastAPI / Express.js | RESTful API endpoints |
| **Database** | PostgreSQL | Primary relational data store |
| **Cache** | Redis | Session management, real-time counters |
| **Message Queue** | RabbitMQ / Kafka | Event streaming, async processing |
| **Search** | Elasticsearch | Publisher discovery, campaign search |

### Frontend
| Layer | Technology | Purpose |
|---|---|---|
| **Framework** | React.js | Dashboard SPA |
| **State Management** | Redux / Zustand | Application state |
| **UI Components** | Custom design system | Brand-consistent UI |
| **Charts** | D3.js / Recharts | Analytics visualizations |
| **Mobile** | Responsive Web | Mobile-first dashboards |

### AI / Machine Learning
| Layer | Technology | Purpose |
|---|---|---|
| **ML Framework** | Python (scikit-learn, TensorFlow) | Model training and inference |
| **Feature Store** | Custom | Campaign features, publisher profiles |
| **Model Serving** | FastAPI + model pipeline | Real-time predictions |
| **NLP** | Arabic NLP models | Content analysis, sentiment |
| **Data Pipeline** | Apache Airflow | ETL, model retraining |

### Infrastructure
| Layer | Technology | Purpose |
|---|---|---|
| **Cloud** | AWS / GCP | Primary cloud infrastructure |
| **Containerization** | Docker | Application packaging |
| **Orchestration** | Kubernetes | Container management |
| **CDN** | CloudFlare | Global edge delivery |
| **Monitoring** | Grafana, Prometheus | System observability |
| **CI/CD** | GitHub Actions | Automated deployments |
| **Logging** | ELK Stack | Centralized logging |

### Tracking & Attribution
| Layer | Technology | Purpose |
|---|---|---|
| **Click Tracking** | Custom redirect service | Sub-millisecond redirects |
| **Conversion Tracking** | Server-side pixel + postback | Privacy-compliant attribution |
| **Deep Linking** | Custom link service | Product-level attribution |
| **Fingerprinting** | Probabilistic matching | Cross-device attribution |
| **Deduplication** | Real-time dedup engine | Prevent double-counting |

---

## Architecture Diagram

```
                    ┌─────────────────────────┐
                    │       CDN / Edge        │
                    │     (CloudFlare)        │
                    └────────────┬────────────┘
                                 │
                    ┌────────────┴────────────┐
                    │      Load Balancer      │
                    │       (NGINX)           │
                    └────────────┬────────────┘
                                 │
          ┌──────────────────────┼──────────────────────┐
          │                      │                      │
┌─────────┴─────────┐ ┌─────────┴─────────┐ ┌─────────┴─────────┐
│  Tracking Service │ │   API Gateway     │ │   Dashboard       │
│  (Click/Conv)     │ │   (REST API)      │ │   (React SPA)     │
└─────────┬─────────┘ └─────────┬─────────┘ └───────────────────┘
          │                      │
          │          ┌───────────┼───────────┐
          │          │           │           │
          │  ┌───────┴──┐ ┌─────┴─────┐ ┌───┴────────┐
          │  │ Campaign │ │ Publisher │ │ Analytics  │
          │  │ Service  │ │ Service   │ │ Service    │
          │  └───────┬──┘ └─────┬─────┘ └───┬────────┘
          │          │           │           │
          └──────────┼───────────┼───────────┘
                     │           │
          ┌──────────┴───────────┴──────────┐
          │         Message Queue           │
          │     (RabbitMQ / Kafka)          │
          └──────────┬───────────┬──────────┘
                     │           │
          ┌──────────┴──┐  ┌────┴───────────┐
          │  AI Engine  │  │  Fraud Engine  │
          │  (ML Models)│  │  (Detection)   │
          └──────────┬──┘  └────┬───────────┘
                     │           │
          ┌──────────┴───────────┴──────────┐
          │         Data Layer              │
          │  PostgreSQL │ Redis │ Elastic   │
          └─────────────────────────────────┘
```

---

## Data Processing Pipeline

1. **Click Event** → Tracking service captures click with publisher ID, campaign ID, device info, geo data
2. **Real-Time Enrichment** → Add publisher profile, campaign rules, fraud signals
3. **Fraud Screening** → ML model scores traffic (VPN, bot, click farm probability)
4. **Redirect** → User sent to brand's landing page with tracking parameters
5. **Conversion Event** → Brand fires postback/pixel upon conversion
6. **Attribution** → Match conversion to originating click using deterministic/probabilistic matching
7. **Deduplication** → Prevent double-counting across publishers and channels
8. **Recording** → Store attributed conversion in database; update dashboards
9. **Payment Queue** → Approved conversions queue for publisher payment

**Latency:** Click-to-redirect: <50ms | Conversion attribution: <500ms | Dashboard update: <2s

---

## Scalability Targets

| Metric | Current | Post-Investment Target |
|---|---|---|
| Events processed/day | ~500K | 5M+ |
| Concurrent campaigns | 250+ | 1,000+ |
| Publisher connections | 870+ | 2,000+ |
| API requests/second | ~100 | 1,000+ |
| Data retention | 24 months | 36 months |
| Uptime SLA | 99.5% | 99.9% |

---

## Security Measures

| Category | Implementation |
|---|---|
| **Data at Rest** | AES-256 encryption |
| **Data in Transit** | TLS 1.3 |
| **Authentication** | JWT + 2FA |
| **Authorization** | Role-based access control (RBAC) |
| **API Security** | Rate limiting, API keys, OAuth 2.0 |
| **Audit Trail** | Full action logging with immutable records |
| **Backups** | Daily automated backups with point-in-time recovery |
| **Penetration Testing** | Annual third-party security audits |

---

© 2026 Perff AI (Perff Inc.). Confidential & Proprietary.
