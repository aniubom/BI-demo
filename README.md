# BI-demo

Dashboard project built in AWS QuickSight to visualize life insurance policy trends, customer demographics, and premium performance. This is a personal portfolio project simulating the development of an internal dashboard, focused on life insurance policy analytics.

## 🎯 Project Goal

To build a QuickSight dashboard that visualizes key metrics around life insurance products such as policy activity, premiums, lapse trends, and customer demographics.

## 🛠️ Tools Used

- AWS QuickSight
- AWS IAM Identity Center
- Excel (for early-stage data inspection)
- Python (mock data generation)
- GitHub (project documentation)

## 📁 Datasets

Located in `/data/`

- `policies.csv` - policy-level data including product type, premium, and status
- `customers.csv` - customer demographics (age, gender, location)
- `payments.csv` - transaction-level payment data tied to policies

## 🔄 Data Prep Highlights

- Joined customer + policy + payment datasets
- Created calculated fields:
  - `policy_duration` = `end_date` - `start_date`
  - `premium_tier` = bucketed based on premium amount
- Cleaned and formatted date fields
- Removed PII for demo purposes

## 📊 Dashboard Features

- KPI summary cards for active policies and avg premiums
- Product mix (Term, Whole, Universal) visualized by share
- Monthly trend line for premiums collected
- Breakdown of customer age/gender/location
- Filters by policy type, status, and date

## 📹 Loom Walkthrough

[Loom Video: Dashboard + Thought Process](paste-your-link-here)

## ✍️ Author

Aniema Ubom  
[LinkedIn](https://www.linkedin.com/in/aniemaubom) | [Portfolio](https://aubom.online)
