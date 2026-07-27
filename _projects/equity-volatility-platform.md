---
layout: page
title: Equity Volatility Research Platform
description: A reproducible Python and SQL platform for equity-option data pipelines, implied-volatility surface estimation, no-arbitrage diagnostics, and historical volatility features.
importance: 1
category: quantitative finance

images:
  lightbox2: true
---

## Overview

I built a modular research platform for equity-option data ingestion,
pricing, implied-volatility estimation, surface modeling, and volatility
feature engineering.

The platform integrates option quotes, underlying prices, interest-rate
curves, dividend data, event calendars, and underlying-price history into
analysis-ready Parquet datasets, CSV reports, and DuckDB tables.

It calculates implied volatilities, Greeks, parity-implied forwards,
standardized volatility points, realized-volatility measures, and daily
surface features while applying automated data-quality and no-arbitrage
controls.

[View the GitHub repository](https://github.com/absacademic/equity-volatility-platform)

## Key features

- Black–Scholes and Black–76 pricing with analytical Greeks
- Bid, midpoint, and ask implied-volatility estimation
- Exact time-to-expiration and interpolated zero-rate calculations
- Put–call-parity forward estimation using multiple near-ATM option pairs
- Discrete-dividend present-value and dividend-adjusted forward calculations
- Early-exercise risk flags for American-style calls and puts
- SVI and cubic-spline volatility-smile fitting
- Equal, vega, inverse-spread, and quote-quality weighting
- RMSE, residual, coverage, stability, and failure-rate diagnostics
- Strike-monotonicity, butterfly-convexity, total-variance, and calendar checks
- Automated rejection or adjustment of invalid fitted surfaces
- Standardized 10-delta, 25-delta, and ATM volatility points
- Downside-skew, risk-reversal, butterfly, curvature, and term-structure features
- Five-, 20-, and 60-day realized-volatility calculations
- Volatility-risk-premium and historical surface comparisons
- Point-in-time event features without future-information leakage
- Parquet, CSV, DuckDB, Markdown report, Typer CLI, and pytest workflows

## Project architecture

1. Raw market-data adapters
2. Data validation and quality-control flags
3. Underlying-price alignment and quote rejection
4. Partitioned Parquet storage and metadata reports
5. DuckDB analytical views
6. Pricing, Greeks, and implied-volatility calculations
7. Rate interpolation and parity-based forward estimation
8. SVI and cubic-spline surface fitting
9. Model evaluation and no-arbitrage controls
10. Standardized volatility-point interpolation
11. Daily volatility-feature construction
12. Event-linked and historical surface comparisons
13. Reproducible reports, tests, and command-line workflows

## Image gallery

<div style="display:grid; grid-template-columns:repeat(auto-fit,minmax(260px,1fr)); gap:1rem; margin:1.5rem 0;">

<a href="{{ '/assets/img/projects/volatility/surface.png' | relative_url }}"
     data-lightbox="volatility-gallery"
     data-title="Estimated implied-volatility surface">
<img
      src="{{ '/assets/img/projects/volatility/surface.png' | relative_url }}"
      alt="Estimated implied-volatility surface"
      style="width:100%; border-radius:8px;">
</a>

<a href="{{ '/assets/img/projects/volatility/smile.png' | relative_url }}"
     data-lightbox="volatility-gallery"
     data-title="Observed and fitted volatility smile">
<img
      src="{{ '/assets/img/projects/volatility/smile.png' | relative_url }}"
      alt="Observed and fitted volatility smile"
      style="width:100%; border-radius:8px;">
</a>

<a href="{{ '/assets/img/projects/volatility/residuals.png' | relative_url }}"
     data-lightbox="volatility-gallery"
     data-title="Smile-fit residual diagnostics">
<img
      src="{{ '/assets/img/projects/volatility/residuals.png' | relative_url }}"
      alt="Smile-fit residual diagnostics"
      style="width:100%; border-radius:8px;">
</a>

<a href="{{ '/assets/img/projects/volatility/atm_term_structure.png' | relative_url }}"
     data-lightbox="volatility-gallery"
     data-title="ATM volatility term structure">
<img
      src="{{ '/assets/img/projects/volatility/atm_term_structure.png' | relative_url }}"
      alt="ATM volatility term structure"
      style="width:100%; border-radius:8px;">
</a>

</div>

## Takeaways

This project has strengthened my understanding of option-pricing models,
market-data engineering, no-arbitrage conditions, nonlinear optimization,
volatility-surface diagnostics, point-in-time feature construction, and
production-oriented Python design.

It has also given me experience designing tested analytical pipelines that
produce reproducible datasets, databases, reports, and model-quality
indicators for further quantitative research.