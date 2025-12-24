# Identifying Key Drivers of Supply Chain Disruptions

![Image](https://github.com/user-attachments/assets/20725820-5b6b-4621-9c15-ce270b85eea1)

## Overview
This repository presents an Excel-based quantitative analysis of supply chain disruptions.  
The project applies **linear and multivariate regression analysis**, supported by descriptive charts built in **Excel and Power BI**, to identify the operational, historical, coordination, and structural drivers of supply chain disruption risk and severity.

The work is designed as a **portfolio-quality analytics project**, demonstrating practical statistical reasoning, Excel modelling skills, and business-focused interpretation.

---

## Objectives
- Identify key operational drivers of supply chain disruptions
- Assess whether historical exposure increases future disruption risk or severity
- Evaluate the role of coordination and governance mechanisms
- Build an integrated model to flag high-risk supply chain situations
- Examine how disruption severity varies by disruption type and product category

---

## Tools & Methods
- **Microsoft Excel**
  - Data cleaning and preparation
  - Pivot tables and descriptive statistics
  - Linear and multivariate regression (Data Analysis Toolpak)
- **Power BI**
  - Scatter plots, clustered bar charts, coefficient plots
  - Risk-category visualisations
- **Statistical Techniques**
  - Simple linear regression
  - Multiple linear regression
  - ANOVA (embedded within regression output)
  - Visual trend analysis

Dataset size: **999 observations**

---

## Research Questions, Analysis & Findings

---
### Research Questions
1. What operational factors (demand variability, inventory levels, lead times, and reorder policies) significantly contribute to supply chain disruptions?
2. What is the relationship between order characteristics (quantity ordered and order value) and supply chain disruption risk?
3. Does historical exposure to disruptions increase the probability and severity of future supply chain disruptions?
4. How do coordination and governance factors (dominant buyer role and data-sharing consent) influence supply chain disruption outcomes?
5. Can a combination of operational, historical, and coordination variables be used to identify high-risk supply chain situations?
6. How does disruption severity vary across product categories and disruption types?


## RQ1: What operational factors (demand variability, inventory levels, lead times, and reorder policies) significantly contribute to supply chain disruptions?

### Regression Model
**Dependent Variable:** Disruption Occurrence / Risk  
**Independent Variables:** Quantity Ordered, Lead Time, Delay Days, Historical Disruption Count

### Regression Summary (RQ1)

| Metric | Value |
|------|------|
| R² | 0.439 |
| Adjusted R² | 0.437 |
| F-statistic | 194.84 |
| Significance F | < 0.001 |
| Observations | 999 |

### Coefficients

| Variable | Coefficient | p-value | Interpretation |
|--------|------------|---------|----------------|
| Delay Days | **0.1183** | **< 0.001** | Strong positive predictor |
| Quantity Ordered | 0.000038 | 0.339 | Not significant |
| Lead Time | -0.0021 | 0.623 | Not significant |
| Historical Disruption Count | -0.00033 | 0.875 | Not significant |

**Findings:** The coefficient analysis reveals that delay duration is the only operational factor with a statistically significant impact on disruption risk, highlighting execution delays as the primary operational driver of supply chain disruptions.


---

## RQ2: What is the relationship between order characteristics (quantity ordered and order value) and supply chain disruption risk?

### Regression Summary (RQ2)

| Variable | Coefficient | p-value | Result |
|--------|------------|---------|-------|
| Quantity Ordered | ~0 | > 0.05 | Not significant |
| Order Value | ~0 | > 0.05 | Not significant |

**Findings:** Disruption risk is process-driven, not transaction-size driven.

---

## RQ3: Does historical exposure increase future disruption probability or severity?

### Regression Model
**Dependent Variable:** Future Disruption / Severity  
**Independent Variable:** Historical Disruption Count

### Regression Summary (RQ3)

| Metric | Value |
|------|------|
| R² | 0.0003 |
| F-statistic | 0.27 |
| p-value | 0.606 |

### Coefficient

| Variable | Coefficient | p-value | Interpretation |
|--------|------------|---------|----------------|
| Historical Disruption Count | 0.0030 | 0.606 | Weak, not significant |

**Findings:** This finding suggests that while past disruptions increase the likelihood of future disruptions, they do not necessarily intensify how severe those disruptions are. Severity appears to be influenced more by situational or operational factors (e.g., lead times, delay days, supplier performance) rather than by historical frequency alone.

---

## RQ4: How do coordination and governance factors (dominant buyer role and data-sharing consent) influence supply chain disruption outcomes?

### Regression Model
**Independent Variables:** Dominant Buyer Flag, Data Sharing Consent

### Regression Summary (RQ4)

| Metric | Value |
|------|------|
| R² | 0.00006 |
| F-statistic | 0.028 |
| p-value | 0.972 |

### Coefficients

| Variable | Coefficient | p-value | Result |
|--------|------------|---------|-------|
| Dominant Buyer Flag | 0.010 | 0.887 | Not significant |
| Data Sharing Consent | 0.016 | 0.846 | Not significant |

**Findings:** Disruption risks are more strongly driven by operational and historical factors rather than governance structures such as buyer dominance or data-sharing agreements
Governance mechanisms alone do not significantly reduce disruption outcomes.

---

## RQ5: Can a combination of operational, historical, and coordination variables be used to identify high-risk supply chain situations?

### Multivariate Regression Model
**Independent Variables:**  
Operational + Historical + Coordination + Severity variables

### Regression Summary (RQ5)

| Metric | Value |
|------|------|
| R² | **0.753** |
| Adjusted R² | 0.751 |
| F-statistic | 301.21 |
| Significance F | < 0.001 |

### Key Coefficients

| Variable | Coefficient | p-value | Impact |
|--------|------------|---------|-------|
| Disruption Severity | **0.3255** | **< 0.001** | Very High |
| Delay Days | **0.0478** | **< 0.001** | High |
| Other Variables | — | > 0.05 | Limited |

**Findings:** Integrated models strongly identify high-risk situations, dominated by severity and delays. Operational delays and historical disruption severity are the primary risk drivers. Historical severity matters more than frequency of past disruptions. Coordination and governance mechanisms (data sharing, dominant buyer role, communication cost) play a secondary role and do not significantly reduce risk on their own.

---

## RQ6:  How does disruption severity vary across product categories and disruption types?

### Regression Model
**Dependent Variable:** Disruption Severity  
**Independent Variables:** Product Category, Disruption Type

### Regression Summary (RQ6)

| Metric | Value |
|------|------|
| R² | 0.447 |
| F-statistic | 401.80 |
| Significance F | < 0.001 |

### Coefficients

| Variable | Coefficient | p-value | Conclusion |
|--------|------------|---------|-----------|
| Disruption Type | **0.475** | **< 0.001** | Significant |
| Product Category | 0.0056 | 0.745 | Not significant |

**Findings:** Disruption severity varies significantly by disruption type but not by product category. While product categories show minor differences, the nature of the disruption itself is the dominant factor determining how severe the disruption becomes.

---

## Key Takeaways
- Operational delays consistently drive disruption risk
- Transaction size has minimal influence
- Governance mechanisms show limited standalone impact
- Integrated models explain over 75% of disruption variance
- Disruption type is the strongest determinant of severity

---

## Conclusion
This Excel-based analysis demonstrates that supply chain disruptions are primarily driven by operational stress and event characteristics rather than order size or governance structure alone. By combining regression modelling with visual analytics, the project provides a robust, data-driven foundation for identifying high-risk supply chain scenarios and improving resilience-focused decision-making.

---

