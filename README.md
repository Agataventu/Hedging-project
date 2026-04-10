# Structured Product Hedging under Variance Gamma Model

## Overview
This project develops a full pricing and hedging framework for a structured autocallable certificate on the S&P 500, using advanced stochastic modeling and market-consistent calibration.

The objective is to construct a self-financing hedging strategy that neutralizes key risk factors (delta, vega, and volatility skew).

## Methodology

### Market Data Processing
- Bootstrap of discount factors and forward prices from option quotes via put–call parity
- Extraction of consistent forward curves across maturities

### Model Calibration
- Calibration of a Variance Gamma (VG) Lévy model to S&P 500 option prices
- Filtering of option data based on liquidity and moneyness
- Parameter estimation via nonlinear optimization (RMSE minimization)

### Pricing
- Monte Carlo pricing of a path-dependent autocallable certificate
- Simulation of underlying dynamics using FFT-based methods

### Hedging Strategy
A multi-step hedging approach targeting key risk exposures:

- **Skew (η) hedge**: neutralization of volatility smile asymmetry via optimal call selection  
- **Vega hedge**: construction of a cost-efficient call–put portfolio preserving skew neutrality  
- **Delta hedge**: replication using synthetic forwards derived from put–call parity  

The hedge is dynamically rebalanced across multiple dates.

### P&L Analysis
- Daily portfolio valuation using market mid prices
- Self-financing strategy with liquidity account and funding adjustments
- Analysis of hedging effectiveness and residual risk

## Results
The strategy successfully constructs a theoretically risk-neutral portfolio, but empirical results highlight significant residual P&L volatility, suggesting sensitivity to implementation details and model limitations.

## Tools & Technologies
- MATLAB
- Monte Carlo simulation
- Fourier pricing methods (Lewis formula)
- Variance Gamma model

## Co-authors
- Bacchi Leonardo
- Casciani Alice Sofia
- Crivellaro Federico
- Imperatore Gaia


*This project was developed for academic purposes as part of the **Computational Finance** course at **Politecnico di Milano (PoliMI)**.
