## Overview
This project tackles a product optimization problem for beverage mugs using consumer preference data. We aim to identify the optimal combination of product features and price that maximizes expected profit per customer, while also exploring trade-offs between market share, cost, margin, and revenue. The solution employs discrete choice modeling using a compensatory rule with logit adjustment and a scaling factor c = 0.0139.

## Problem Setup
  Attributes and Levels
  Each product is defined by 5 features and price:
  Price: $30, $10, $5
  Time Insulated: 0.5 hr, 1 hr, 3 hrs
  Capacity: 12 oz, 20 oz, 32 oz
  Cleanability: Difficult (7 min), Fair (5 min), Easy (2 min)
  Containment: Slosh resistant, Spill resistant, Leak resistant
  Brand: A, B, C

## Market Scenario

| Product      | Price | Time Insulated | Capacity | Cleanability | Containment     | Brand |
|--------------|-------|----------------|----------|--------------|------------------|--------|
| Incumbent 1  | $30   | 3 hrs          | 20 oz    | Easy         | Leak resistant   | A      |
| Incumbent 2  | $10   | 1 hr           | 20 oz    | Fair         | Spill resistant  | B      |
| Candidate    | $30   | 1 hr           | 20 oz    | Easy         | Leak resistant   | C      |

## Methodology

This analysis uses a **Discrete Choice Model** with **logit adjustment** to simulate customer preferences and evaluate product performance.
- **Utilities** are computed from individual-level preference parameters.
- **Purchase probabilities** are calculated using the logit formula:
  \[
  P_i = \frac{e^{c \cdot U_i}}{\sum_j e^{c \cdot U_j}}
  \]
  where:
  - \( P_i \) = probability of choosing product *i*
  - \( U_i \) = utility of product *i*
  - \( c \) = scaling constant (0.0139 in this analysis)

- **Expected Profit Per Person (EPPP)** is calculated as:
  \[
  \text{EPPP} = \text{Market Share} \times (\text{Price} - \text{Cost})
  \]

All computations are implemented in **Python** using `pandas` and `NumPy`.

## Disclaimer
This project was completed as part of an academic exercise focused on product and pricing optimization using discrete choice modeling. Please note:

- **The dataset used in this project is not included** due to academic integrity and data confidentiality policies.
- **Only the methodology and code** have been provided in this repository to illustrate the analytical approach and modeling techniques used.
- The results and insights derived are specific to a simulated market scenario and should not be interpreted as commercial recommendations.

This repository is intended solely for educational and demonstration purposes.

