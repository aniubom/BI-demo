# Data Cleaning & Preparation

This section documents the transformations, field creation, and cleaning steps taken to prepare the BetaLife datasets for visualization inside AWS QuickSight.

---

## Joins & Relationships

The following relationships were defined across the datasets:

- **`customers.csv` → `policies.csv`**  
  Joined via `customer_id`  
  One-to-many: A customer can hold multiple policies.

- **`policies.csv` → `payments.csv`**  
  Joined via `policy_id`  
  One-to-many: A policy can have multiple associated payments.

These joins were created inside QuickSight during dataset preparation using the visual join interface.

---

## Calculated Fields

The following calculated fields were created in QuickSight to support grouping, aggregation, and filtering across the dashboard:

**policy_duration**  
`datediff({end_date}, {start_date}, 'MM')`  
→ Calculates policy lifespan in months for use in KPI metrics.

**lapsed_policies**  
`ifelse(status = 'Lapsed' OR status = 'Canceled', 1, 0)`  
→ Used to count lapsed/canceled policies across product types.

**lapsed_policy_percent**  
`sumOver(ifelse(status = 'Lapsed' OR status = 'Canceled', 1, 0), [], PRE_AGG) / countOver({policy_id}, [], PRE_AGG)`  
→ Used to display % of lapsed policies by product in bar chart tooltip.

**payment_month**  
`truncDate("MM", parseDate({payment_date}, 'yyyy-MM-dd'))`  
→ Used to group payments by month for trend analysis.

**age_bracket**  
ifelse(age <= 25, '18–25', age <= 35, '26–35', age <= 45, '36–45', age <= 60, '46–60', '60+')
→ Used to group customers for the demographic bar chart.

.

---

## Field Formatting & Parsing

- **Dates**: `start_date`, `end_date`, and `payment_date` were parsed as date objects. `payment_date` was originally stored as text and converted using `parseDate()`. A truncated version using `truncDate("MM", ...)` was created to support monthly trend analysis.
Extracted `Year` and `Month` components for trend-based visualizations.

- **Text Normalization**: All status and product type fields were capitalized consistently (e.g., `Term`, `Whole`, `Universal`) to avoid grouping errors.

---

## Data Quality Considerations

- **Removed PII**: Names were generic, and no emails, SSNs, or contact info were included.
- **De-duped Customer Records**: Ensured each customer had a unique `customer_id`.
- **Payments Validation**: Each payment was linked to a valid policy. No orphaned records were included.

---




