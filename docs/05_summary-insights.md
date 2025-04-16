# Summary & Insights

## What Business Questions Does the Dashboard Answer?
- **Where are we losing policies?**  
  → Lapse trends highlight retention gaps by product type.

- **What is the overall health of our policy portfolio?**  
  → KPIs and trend charts track active count, revenue, and policy lifecycle.

- **Who are our customers and where are they located?**  
  → Demographic breakdowns (age, gender, state) support targeting and segmentation.

---

## What Steps Did I Take?
- **Discovery**: Defined fictional org, goals, audience, KPIs
- **Data Inventory**: Explored datasets, documented keys/relationships
- **Data Prep**: Cleaned fields, created calculated columns, joined tables
- **Design**: Grouped visuals by user need, built in QuickSight
- **Documentation**: Tracked logic, matched visuals to stories

---

## Problem-Solving Approach
1. Start with the stakeholder’s need
2. Reverse-engineer required data
3. Design the best visual to answer it
4. Validate with the “5-second test”
5. Work around tool limitations with calculated fields or settings

---

## Challenges I Faced
- `payment_date` text → used `parseDate()` + `truncDate()`
- KPI styling limits → leaned into clarity and font consistency
- State code misread → manually set geographic type
- SPICE refresh bugs → re-mapped fields, revalidated visuals
- AWS configuration issues

---
