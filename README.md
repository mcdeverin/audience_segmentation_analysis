# Host Growth & Audience Segmentation Analysis
### A Reusable Marketplace Analytics Framework

---

## Overview

This project applies audience segmentation and growth analytics to Airbnb's host ecosystem using publicly available Inside Airbnb data. The analytical framework mirrors techniques used in media and consumer platforms to understand user behavior, identify high-value segments, and surface retention signals.

**Built with:** Python, Pandas, Scikit-learn, Matplotlib, Seaborn

---

## Key Questions Answered

1. **Who are the platform's most valuable hosts?** — RFM-inspired segmentation identifies four distinct host archetypes
2. **What drives engagement and retention?** — Activity tier analysis surfaces churn risk signals
3. **Where are the growth opportunities?** — Segment-level recommendations for platform strategy

---

## Methodology

### RFM-Inspired Host Segmentation

Adapted from e-commerce analytics, this framework scores hosts on three dimensions:

| Dimension | Proxy Metric | Business Question |
|-----------|-------------|-------------------|
| **Recency** | Days since last review | Is this host currently active? |
| **Frequency** | Reviews per month | How often do guests book? |
| **Magnitude** | Price × availability | What is the revenue potential? |

### K-Means Clustering

- Silhouette analysis used to select optimal cluster count (k=4)
- Features normalized via StandardScaler before clustering
- Segments validated against business logic and domain knowledge

### Activity Tier Classification

Rule-based classification assigns listings to activity tiers (High / Medium / Low / Inactive) based on booking frequency and availability patterns — providing a retention risk framework applicable to any marketplace.

---

## Segments Identified

| Segment | Characteristics | Strategic Priority |
|---------|----------------|-------------------|
| **Power Hosts** | High revenue + high engagement | Retain — superhost programs |
| **Active Hosts** | High engagement, moderate price | Grow — upsell to premium |
| **Premium Hosts** | High price, lower frequency | Re-engage — availability optimization |
| **Casual Hosts** | Low engagement, low price | Retain — onboarding support |

---

## Files

```
├── airbnb_audience_segmentation.ipynb   # Main analysis notebook
├── README.md                            # Project documentation
```

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/mcdeverin/marketing_attribution_model.git

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# Launch notebook
jupyter notebook airbnb_audience_segmentation.ipynb
```

The notebook automatically loads the Inside Airbnb NYC dataset from the public API. If the connection fails, it falls back to a representative synthetic dataset.

---

## Generalizing This Framework

This segmentation approach is **reusable across any marketplace or consumer platform**:

- Swap host metrics for user engagement metrics (DAU, session frequency, purchase value)
- Adapt RFM dimensions to the specific platform context
- The K-Means clustering pipeline generalizes to any audience segmentation problem

---

## Data Source

[Inside Airbnb](http://insideairbnb.com/) — publicly available NYC listings data. This project is for analytical and educational purposes only.

---

*Built as part of a portfolio demonstrating applied data science in marketplace and consumer analytics contexts.*
