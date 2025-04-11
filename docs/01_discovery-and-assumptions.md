# Discovery & Assumptions

This document outlines the initial understanding of the business problem, intended audience, defined metrics, and key assumptions made to simulate the dashboard development process for Navy Mutual's life insurance policy analytics.

---

## Business Understanding

BetaLife offers life insurance products to service members and their families. Business stakeholders need visibility into the performance of these policies over time, segmented by product type and customer demographics. The purpose of this dashboard is to simulate an internal analytics solution that would help the organization make data-informed decisions around product effectiveness, risk exposure, and customer trends.

---

## Intended Audience

- Insurance Product Managers
- Customer Experience Leads
- Executive Leadership
- Actuarial & Risk Management Teams

---

## Metrics & KPIs

The following core metrics were selected for this initial dashboard based on common insurance analytics use cases:

- **Total Active Policies**
- **Lapsed or Canceled Policy Count**
- **Average Premium per Policy**
- **Policy Mix by Product Type (Term, Whole, Universal)**
- **Customer Distribution by Age, Gender, and Region**
- **Policy Duration (calculated from start and end dates)**
- **Premium Tiering (Low / Medium / High)**

---

## Data Assumptions

The following assumptions were made when generating mock data:

- **Policy Premiums**: Randomized values between $50–$1,000 representing monthly or annual premium amounts (no inflation adjustments).
- **Status Values**: Policies were randomly assigned a status of “Active”, “Lapsed”, “Canceled”, or “Paid-up” to simulate real-world variation in policy life cycles.
- **Policy Duration**: Derived using the difference between `start_date` and `end_date`.
- **Premium Tier**: Bucketed into three categories:
  - Low: <$100
  - Medium: $100–$499
  - High: $500+
- **Customer Data**: Generated with randomized age, gender, and geographic region (e.g. DC, VA, TX, CA) to reflect a U.S.-based customer base.
- **Payments**: Mock payment entries were created to represent individual transactions linked to a given policy.

All personally identifiable information (PII) was excluded. No real user data or customer history was used in this project.

---



