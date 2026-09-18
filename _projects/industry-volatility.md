---
layout: page
title: Downside Dominance in Industry Volatility Networks
description: An empirical study of how common market factors and the definition of a negative shock shape measured volatility relationships across U.S. industries.
importance: 2
category: research
images:
  lightbox2: true
---

## Overview

I investigate why negative shocks appear to dominate volatility relationships across industries, and how that conclusion changes after accounting for common market factors. Using 30 U.S. industry portfolios, I compare networks constructed from raw returns with networks constructed from factor-adjusted returns.

The central insight is that factor adjustment changes both the size of a return and potentially its sign. An industry can lose value while performing better than its factor model predicts: its raw return is negative, but its adjusted return is positive. Separating these two changes reveals how the definition of a negative shock affects the results.

This project forms the basis of my September 2026 working paper, _Downside dominance in industry volatility networks: The role of shock classification_.

[View the GitHub repository and read the paper](https://github.com/absacademic/industry-volatility-networks)

## Research question

How much downside dominance remains after removing common-factor exposure while keeping the original definition of a negative day—and how much of the apparent disappearance comes from changing that definition?

## Data and methodology

- **Data:** 30 value-weighted U.S. industry portfolios and daily factors from the Kenneth French Data Library, with weekly observations spanning 1972–2025 and reported comparisons covering 2014–2025.
- **Factor adjustment:** Rolling market, Fama–French three-factor (FF3), and five-factor (FF5) regressions, estimated over 504 trading days and updated every 21 days.
- **Weekly variation:** Sums of squared daily returns or residuals, divided into negative and nonnegative categories.
- **Network estimation:** Relationships between one industry's variation and another industry's next-week variation, controlling for the receiving industry's recent volatility and lagged market volatility. Estimates use 156-week windows, updated every four weeks.
- **Validation:** Conditional block-bootstrap intervals, eight data treatments, and 499 independent-shock simulations per factor model.

## The key comparison

1. **Raw returns:** Measure variation and classify negative days using observed industry returns.
2. **Adjusted returns, original signs:** Remove factor exposure but retain the original daily classifications.
3. **Adjusted returns, residual signs:** Keep the same adjusted returns and classify days using their signs relative to the factor model.

Network strength averages positive correlations remaining after the controls; negative correlations are set to zero. The **negative share** measures the negative category's contribution to combined strength, averaged across network update dates. It is not the percentage of return variance explained or a causal spillover estimate.

## Main findings

| Return specification                    | Negative share |
| --------------------------------------- | -------------: |
| Raw returns                             |         94.37% |
| Market-adjusted returns, original signs |         63.64% |
| Market-adjusted returns, residual signs |         48.95% |

**Changing shock labels accounts for 32.4% of the measured decline under the market model.** Adjustment with original signs reduces the share by 30.72 percentage points; switching to residual signs reduces it by another 14.70 points. These changes use unrounded estimates. FF3 and FF5 produce similar results.

The ordering also survives alternative transformations and treatment of weeks without observations in one sign category. Near balance, however, does not mean that dependence disappears: observed residual network strength exceeds every corresponding simulation in all 24 reported strength comparisons.

## Selected figures

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(min(100%, 420px), 1fr)); gap: 1.5rem; margin: 1.5rem 0;">
  <figure style="margin: 0; min-width: 0;">
    <a href="{{ '/assets/img/projects/industry-volatility/negative-share-comparison.png' | relative_url }}" data-lightbox="industry-volatility-gallery" data-title="Downside dominance depends on the daily sign definition">
      <img src="{{ '/assets/img/projects/industry-volatility/negative-share-comparison.png' | relative_url }}" alt="Raw negative share is 94.37 percent. After factor adjustment, shares remain around 63 percent with original signs but fall to about 49 percent with residual signs across the market, FF3, and FF5 models." width="2080" height="1560" loading="lazy" decoding="async" style="display: block; width: 100%; height: auto; border-radius: 8px;">
    </a>
    <figcaption style="margin-top: 0.75rem; font-size: 0.95rem; line-height: 1.6;">
      <strong>Downside dominance depends on how negative days are defined.</strong> Factor adjustment reduces the negative share, but the share remains above 50% when original daily signs are retained. Using residual signs brings it close to one-half across all three factor models. Whiskers show conditional 95% bootstrap intervals that treat the fitted networks as given.
    </figcaption>
  </figure>
  <figure style="margin: 0; min-width: 0;">
    <a href="{{ '/assets/img/projects/industry-volatility/residual-strength-benchmark.png' | relative_url }}" data-lightbox="industry-volatility-gallery" data-title="Balanced residual shares can coexist with dependence beyond the benchmark">
      <img src="{{ '/assets/img/projects/industry-volatility/residual-strength-benchmark.png' | relative_url }}" alt="Observed combined residual network strength is 0.07043 for the market model, 0.07859 for FF3, and 0.07536 for FF5. Each exceeds the corresponding 95 percent simulation range under an independent-shock benchmark." width="2080" height="1560" loading="lazy" decoding="async" style="display: block; width: 100%; height: auto; border-radius: 8px;">
    </a>
    <figcaption style="margin-top: 0.75rem; font-size: 0.95rem; line-height: 1.6;">
      <strong>A balanced split does not imply that dependence disappears.</strong> With residual signs, observed combined network strength exceeds the benchmark for each factor model. Simulations retain common returns and persistent, asymmetric industry volatility while drawing industry-specific shocks independently. Bars show the middle 95% of 499 simulated outcomes per model, not confidence intervals for the observed estimates.
    </figcaption>
  </figure>
</div>

## Technical methods

- Rolling factor regressions and signed weekly variation
- HAR-style volatility controls and partial-correlation networks
- Circular moving-block bootstrap inference
- GJR-GARCH simulation with independently resampled industry shocks
- Sensitivity analysis for transformations, ranks, and zero observations

## Technical stack

Python, NumPy, pandas, SciPy, arch, PyArrow, Matplotlib, PyYAML, joblib, threadpoolctl, pytest, LaTeX

## Limitations and extensions

These are exploratory statistical relationships, and so not necessarily causal contagion. Omitted common shocks may contribute to residual dependence, and the simulation benchmark does not rule out other explanations without direct transmission. Bootstrap intervals condition on fitted networks; simulation comparisons condition on fitted parameters and the observed factor history. Factor adjustment uses realized contemporaneous factors, making it an after-the-fact decomposition. The analysis uses daily rather than intraday data.

Future work could extend the comparison to individual firms, intraday observations, other markets, and alternative factor models. Testing on new data could assess whether shock classification improves volatility forecasts or portfolio risk estimates; supply-chain information and research designs isolating industry-specific shocks could help investigate transmission.

## Takeaways

This project strengthened my experience in financial time-series analysis, factor modeling, network measurement, simulation, and robustness assessment. Its practical lesson is to report both the factor adjustment and the shock-classification rule; indeed, a change in measured downside dominance can reflect both economic exposure and the way shocks are labeled.
