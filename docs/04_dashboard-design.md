# Dashboard Design

This document outlines the layout, visualization choices, and design decisions behind the BetaLife Life Insurance Policy Dashboard built in AWS QuickSight.

The dashboard was designed as a self-service analytics tool for product managers and leadership at BetaLife to:

- Monitor the performance of their life insurance offerings
- Track trends in customer behavior and policy activity
- Make informed decisions around product strategy, retention, and customer segmentation

It eliminates the need to manually export reports or wrangle spreadsheets.

---

## How the Dashboard is Used

- Filter by product type to compare lapse trends and premium performance
- Identify which products underperform based on lapse rate or low premium revenue
- Monitor how different segments (e.g. age, location) respond to each insurance offering
- Use KPI summary to report on active policy volume, premium health, and policy age
- Track premium trends across months to spot seasonal patterns or churn risks
- Drill down into customer segments to support targeting or retention campaigns

## Layout Overview

The dashboard is organized into the following sections:

### 1. **KPI Summary**
- **Total Active Policies**
- **Avg. Monthly Premium**
- **Total Policies Lapsed**
- **Avg. Policy Duration**

These KPIs are displayed at the top for quick, at-a-glance status.

---

### 2. **Product Type Distribution**
- **Visual**: Donut chart
- **Purpose**: Show share of Term, Whole, and Universal policies

---

### 3. **Premium Trends Over Time**
- **Visual**: Line chart
- **X-axis**: Month (derived from `start_date`)
- **Y-axis**: Total premium collected
- **Purpose**: Highlight seasonality, growth, or retention trends

---

### 4. **Lapse Rate by Product Type**
- **Visual**: Horizontal bar chart
- **X-axis**: Count of lapsed policies
- **Y-axis**: Product type
- **Purpose**: Identify which products are underperforming in retention

---

### 5. **Customer Demographics**
- **Visuals**:
  - Age bucket distribution (bar chart)
  - Gender split (pie chart)
  - State-level spread (geo map)
- **Purpose**: Provide leadership a high-level customer segmentation view

---

### 6. **Filters & Interactivity**
- **Filters Used**:
  - Product Type
  - Policy Status
  - Premium Tier
  - Date Range
- **Purpose**: Allow users to explore policies by segment

---

## Design Considerations

- **Color**: Used a clean, minimal palette to align with professional insurance reporting dashboards
- **Hierarchy**: KPIs positioned at the top, followed by trends and comparisons
- **Consistency**: Reused axis labels, grouped visuals by topic
- **Responsiveness**: SPICE-backed visuals refresh quickly to support interactivity

---

## Sample User Story: View lapse trends by product type

As a Product Manager,  
I want to see how many policies are lapsing by product type,  
So that I can identify which products need retention strategy improvements.

**Acceptance Criteria: Display lapsed policies by product type**

```
Given I am viewing the BetaLife dashboard
When I select the "Policy Status" filter with values 'Lapsed' and 'Canceled'
And I group the data by product type
Then I should see a horizontal bar chart showing the percentage of lapsed policies across product types.  

When I hover over any bar in the chart
Then I should see a tooltip displaying:
- Product Type 
- Count of Lapsed Policies 
- Percentage of Total Lapsed Policies
```

![Lapsed Policies %](https://github.com/aniubom/BI-demo/blob/main/visuals/lapsed-policies-by-product-type.png?raw=true)


## Sample User Story: View high-level portfolio metrics

As a Product Manager,  
I want to be able to view key peformance metrics,    
So that I can identify trends without relying on manual exports.    

**Acceptance Criteria: Display top-level KPIs and premium trends**

```
Given I am on the BetaLife dashboard
When I load the KPI section
Then I should see the following values:
- Total Active Policies       
- Average Premium             
- Average Policy Duration    
When I scroll to the premium trends section
Then I should be able to view a line chart displaying total monthly premiums
```
## Sample User Story: Explore customer demographics

As a Product Manager,  
I want to be able to analyze our customer base by age, location, and gender,  
So that I can segment marketing efforts.  

**Acceptance Criteria: Display demographic breakdowns**

```
Given I am on the BetaLife dashboard
When I view the demographics section
Then I should see:
- A bar chart grouped by age bracket        
- A pie chart showing gender split          
- A map showing customer count by state     




