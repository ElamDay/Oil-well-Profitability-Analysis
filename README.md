# Oil Well Profitability Analysis

Machine learning project focused on selecting the most profitable and lowest-risk region for oil well development using linear regression and bootstrap-based risk analysis.

## Project Overview

The objective of this project is to help an oil extraction company determine the best region for developing 200 new oil wells.

Three different regions were analyzed using geological data containing well characteristics and known reserve volumes.

The analysis combines machine learning predictions with business constraints and risk estimation.

## Business Conditions

- 500 candidate wells are evaluated per region.
- The 200 wells with the highest predicted reserves are selected.
- Total development budget: **$100 million**.
- Revenue per unit of product: **$4,500**.
- Only regions with a probability of loss below **2.5%** are considered.
- Among acceptable regions, the one with the highest average profit is selected.

## Methodology

The project follows these main steps:

1. Data loading and exploration.
2. Data validation and duplicate analysis.
3. Train/validation split using a 75/25 ratio.
4. Linear regression model training for each region.
5. Model evaluation using RMSE.
6. Selection of the 200 wells with the highest predicted reserves.
7. Profit estimation based on actual reserves.
8. Bootstrap simulation with 1,000 samples.
9. Calculation of:
   - Average profit
   - 95% confidence interval
   - Probability of financial loss

## Model Performance

| Region | Predicted Average Reserves | RMSE |
|---|---:|---:|
| Region 0 | 92.59 | 37.58 |
| Region 1 | 68.73 | 0.89 |
| Region 2 | 94.97 | 40.03 |

Region 1 produced the most accurate predictions, with a substantially lower RMSE than the other two regions.

## Preliminary Profit Analysis

| Region | Potential Profit |
|---|---:|
| Region 0 | $33.21M |
| Region 1 | $24.15M |
| Region 2 | $27.10M |

Based only on the best 200 wells in the validation dataset, Region 0 initially appeared to be the most profitable option.

## Bootstrap Risk Analysis

| Region | Average Profit | 95% Confidence Interval | Loss Risk |
|---|---:|---:|---:|
| Region 0 | $3.96M | -$1.12M to $9.10M | 6.9% |
| Region 1 | $4.56M | $0.34M to $8.52M | 1.5% |
| Region 2 | $4.04M | -$1.63M to $9.50M | 7.6% |

## Final Recommendation

Region 1 is the recommended region for oil well development.

Although Region 0 initially showed the highest potential profit, its estimated loss risk exceeded the maximum allowed threshold.

Region 1 was the only region with a loss risk below **2.5%**, while also providing the highest average profit among the acceptable regions.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Jupyter Notebook
- Linear Regression
- Bootstrap Sampling
- Git / GitHub

## Repository Structure

```text
Oil-well-Profitability-Analysis/
│
├── notebook.ipynb
├── geo_data_0.csv
├── geo_data_1.csv
├── geo_data_2.csv
└── README.md