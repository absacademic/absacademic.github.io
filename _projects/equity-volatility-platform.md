---
layout: page
title: Equity Volatility Research Platform
description: A reproducible Python and SQL platform for option pricing, implied-volatility estimation, surface modeling, and data-quality analysis.
img: assets/img/projects/volatility/cover.png
importance: 1
category: quantitative finance

images:
  lightbox2: true
---

## Overview

I built a modular research platform that integrates equity-option quotes,
underlying prices, interest rates, and event data into analysis-ready
Parquet datasets and DuckDB views.

The platform calculates implied volatility, Greeks, forward prices,
term structures, and volatility surfaces while running automated checks
for invalid contracts, crossed markets, stale observations, duplicate
records, and low-liquidity quotes.

[View the GitHub repository](https://github.com/absacademic/equity-volatility-platform)

## Key features

- Black–Scholes and Black–76 pricing
- Bid, midpoint, and ask implied-volatility estimation
- Put–call-parity forward estimation
- SVI and cubic-spline smile fitting
- Equal, vega, spread, and quote-quality weighting
- RMSE, residual, coverage, stability, and failure-rate diagnostics
- Polars, DuckDB, Parquet, SciPy, NumPy, Typer, and pytest workflows

## Project architecture

1. Raw market-data adapters
2. Data validation and quality-control flags
3. Analysis-ready Parquet storage
4. DuckDB analytical views
5. Pricing and implied-volatility calculations
6. Surface fitting and model comparison
7. Reproducible reports and visualizations

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

<a href="{{ '/assets/img/projects/volatility/term-structure.png' | relative_url }}"
     data-lightbox="volatility-gallery"
     data-title="ATM volatility term structure">
<img
      src="{{ '/assets/img/projects/volatility/term-structure.png' | relative_url }}"
      alt="ATM volatility term structure"
      style="width:100%; border-radius:8px;">
</a>

</div>

## Takeaways

This project has strengthened my understanding of option-pricing models,
market-data validation, nonlinear optimization, model diagnostics,
reproducible research workflows, and production-oriented Python design.
