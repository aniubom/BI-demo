# Data Overview

This section outlines the datasets used in the BetaLife Life Insurance Dashboard project.

## 1. Dataset Summaries

### `policies.csv`
- **Grain**: One row per policy
- **Fields**:
  - `policy_id` (unique ID)
  - `product_type` (Term, Whole, Universal)
  - `start_date`, `end_date`
  - `premium_amount`
  - `status` (Active, Cancelled, Paid-up)

### `customers.csv`
- **Grain**: One row per customer
- **Fields**:
  - `customer_id` (unique ID)
  - `age`, `gender`, `state`
  - `customer_since`
  - `policy_id` (foreign key)

### `payments.csv`
- **Grain**: One row per payment transaction
- **Fields**:
  - `payment_id` (unique ID)
  - `policy_id` (foreign key)
  - `payment_date`
  - `amount_paid`

## 2. Relationships

- `customers` ➝ `policies`: one-to-many
- `policies` ➝ `payments`: one-to-many

## 3. Assumptions

- Premiums are billed monthly unless otherwise stated
- All data is synthetic; PII has been excluded
- Customer records are de-duplicated
