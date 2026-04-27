# The Role of Geopolitical Risk in Exchange Rate Pass-Through
### A Comparative Study of the U.S. Dollar and Russian Ruble Against the Euro (2015–2024)

## Overview

This project investigates how geopolitical risk transmits into exchange rate volatility for two structurally different currencies — the U.S. Dollar (USD/EUR) and the Russian Ruble (RUB/EUR) — over a ten-year period spanning major global shocks including the 2015 oil crash, the COVID-19 pandemic, and the 2022 Russian invasion of Ukraine.

## Research Questions

1. How do geopolitical risk shocks transmit differently into USD/EUR and RUB/EUR exchange rate volatility?
2. Does elevated GPR reliably predict extreme currency days, or is it better understood as an amplifier of pre-existing market turbulence?
3. How do fuel and agricultural export trajectories interact with currency movements over the 2015–2024 period?

## Data Sources

| Dataset | Source | Frequency |
|---|---|---|
| USD/EUR exchange rate | Google Finance | Daily |
| RUB/EUR exchange rate | Google Finance | Daily |
| Geopolitical Risk Index (GPR) | Caldara & Iacoviello (2022) | Monthly |
| U.S. & Russia merchandise exports | WTO Time Series API | Annual |

### 4. Predictive Modeling

**Random Forest Classifier**
Predicts whether a given day will be an extreme volatility day (top 10th percentile of absolute daily change), fitted separately for USD and RUB.

**Linear Regression (Models 2 & 3)**
Two OLS models — one per currency — regress daily percentage changes on GPR scores, lagged returns, rolling volatility, and annual export growth. Features are standardized prior to fitting to allow coefficient magnitude comparison. Raw coefficients are used for RMSE/R² reporting to preserve interpretability in original units.

## Key Findings

- **Structural asymmetry**: The USD behaves as a mature reserve currency, absorbing geopolitical shocks with minimal volatility transmission. The RUB is structurally reactive, amplifying external shocks regardless of their origin.
- **GPR as an amplifier, not a predictor**: The monthly GPR index does not reliably predict extreme currency days. RUB volatility is in some regimes higher during normal GPR periods than elevated ones, suggesting the index misses sudden structural ruptures like sanctions announcements.
- **The 2022 episode**: The Russian invasion of Ukraine produced the largest RUB volatility spike in the dataset and a collapse in Russian exports — yet the GPR_RUS index continued declining rather than spiking, exposing a fundamental limitation of backward-looking risk indices in capturing regime-breaking events.
- **Export data frequency mismatch**: Annual WTO export figures produce near-zero coefficients in the regression models, not because trade is irrelevant, but because assigning the same annual figure to every trading day eliminates all within-year variation. This is a data limitation, not an economic conclusion.
- **Lagged return dominates**: The single strongest predictor in both regression models is the lagged one-day return, with the effect being substantially larger for RUB (–0.449) than USD (–0.025), indicating the ruble is more prone to mean reversion following large moves.
