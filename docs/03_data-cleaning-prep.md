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

Two custom fields were created directly in QuickSight to support grouping and filtering:

- **`policy_duration`**

datediff({end_date}, {start_date}, 'DD')

Used to calculate the number of days a policy was active (or expected to remain active).

- **`premium_tier`**  

ifelse( {premium} < 100, 'Low', ifelse({premium} <= 499, 'Medium', 'High') )

Bucketed premium amounts into categories for easier filtering and analysis.

---

## Field Formatting & Parsing

- **Dates**: `start_date`, `end_date`, and `payment_date` were parsed as date objects.  
Extracted `Year` and `Month` components for trend-based visualizations.

- **Text Normalization**: All status and product type fields were capitalized consistently (e.g., `Term`, `Whole`, `Universal`) to avoid grouping errors.

---

## Data Quality Considerations

- **Removed PII**: Names were generic, and no emails, SSNs, or contact info were included.
- **De-duped Customer Records**: Ensured each customer had a unique `customer_id`.
- **Payments Validation**: Each payment was linked to a valid policy. No orphaned records were included.

---

## SPICE Import

After cleaning and transforming, the data was imported into QuickSight's SPICE engine to allow:

- Faster performance with large joins and filters
- Support for scheduled refreshes
- Lightweight column-level calculations


