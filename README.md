# Macro-Financial Drivers of Market Stress Regimes

## Project Overview....

This project studies how US financial markets switch between **calm** and **stressed** regimes. We investigate whether macroeconomic and financial indicators can help predict when market stress begins, how long it persists, and whether these forecasts can improve investment decisions.

Our main approach is a **two-state Time-Varying Transition Probability (TVTP) Markov-Switching AR model**. Unlike a standard Markov-Switching model with fixed transition probabilities, this model lets the probability of entering or remaining in a stressed regime change with economic conditions.

## Data and Variables

We use monthly US data from **January 2010 through October 2026**, subject to each series' availability. Data come primarily from [FRED](https://fred.stlouisfed.org/).

**Dependent variable (market stress):** We plan to use the Chicago Fed National Financial Conditions Index (`NFCI`) as a practical baseline. The original proposal also considers the ICE BofA US High Yield Option-Adjusted Spread (`BAMLH0A0HYM2`) and the St. Louis Fed Financial Stress Index (`STLFSI4`), depending on historical data availability.

**Explanatory variables:**

| Variable | FRED series | Monthly measure |
| --- | --- | --- |
| Z1: Yield curve | `T10Y2Y` | Monthly average of the 10-year minus 2-year Treasury spread |
| Z2: Credit spread | `BAA10YM`, `AAA10YM` | Baa spread minus Aaa spread |
| Z3: Labor market | `UNRATE` | Monthly change in unemployment rate |
| Z4: Economic activity | `INDPRO` | Year-over-year industrial production growth |
| Z5: Inflation | `CPILFESL` | Year-over-year core CPI inflation |
| Z6: Monetary policy | `DGS2` | Monthly change in the average 2-year Treasury yield |

The explanatory variables will be standardized and lagged before entering the transition equations. Publication delays and historical data revisions will be considered when evaluating real-time forecasts.

## Planned Implementation

1. **Data preparation:** Download FRED series, align monthly dates, construct variables, and check missing observations.
2. **Exploratory analysis:** Plot the series, calculate descriptive statistics, examine correlations and autocorrelations, and run ADF and KPSS stationarity tests.
3. **Baseline model:** Estimate a two-state Markov-Switching model with constant transition probabilities.
4. **TVTP model:** Allow macro-financial variables to affect the probabilities of entering and remaining in a stressed regime.
5. **Regime estimation:** Use the Hamilton filter for real-time filtered probabilities and the Kim smoother for retrospective regime analysis.
6. **Forecast evaluation:** Make 1-, 3-, and 6-month forecasts using an expanding window and compare performance with simpler benchmark models.
7. **Economic interpretation and application:** Study which variables are associated with crisis onset versus persistence, test model improvements, and evaluate a regime-based portfolio allocation strategy.

## Sample Split and Team Responsibilities

- **Training:** January 2010 - December 2020
- **Out-of-sample evaluation:** January 2021 - October 2026
- **Team member 1:** Z1 (yield curve), Z2 (credit spread), Z3 (unemployment change)
- **Team member 2:** Z4 (industrial production), Z5 (core inflation), Z6 (monetary policy)

Both sets of variables will be merged into one monthly dataset before model estimation. All results described above are **planned analyses**, not completed findings.
