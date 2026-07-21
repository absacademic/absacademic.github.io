---
layout: page
title: Minimum Wage and Restaurant Price Pass-Through
description: An R-based difference-in-differences study of how minimum-wage increases affect food-away-from-home prices across major U.S. metropolitan areas.
importance: 2
category: research
images:
  lightbox2: true
---

## Overview

I developed an R-based empirical research pipeline to examine whether minimum-wage increases pass through to restaurant prices. The project builds a metro-month panel for Los Angeles, New York, and Chicago by combining Food Away From Home (FAFH) CPI data with federal, state, and local minimum-wage changes.

Developed as part of a six-person research team, my work as project lead focused on the econometric analysis, data construction, model implementation, figures, and diagnostic outputs.

[View the GitHub repository](https://github.com/absacademic/minimum-wage-BRB-project-github)

## Research question

To what extent do changes in binding minimum wages affect month-to-month restaurant-price inflation, after accounting for persistent differences across metropolitan areas, recurring calendar patterns, and broader inflation?

## Data and methodology

- Constructed a monthly panel beginning in 2009 for Los Angeles, New York, and Chicago
- Combined metro-level FAFH CPI series with federal, state, and local minimum-wage schedules
- Mapped overlapping state and local wage ordinances into metro-level treatment measures
- Calculated monthly log changes in restaurant prices, minimum wages, and national CPI
- Estimated fixed-effects difference-in-differences models with metro-clustered standard errors
- Exported cleaned panels, treated-month records, coefficient tables, model summaries, and figures

## Model specifications

1. **Main intensity model:** Relates changes in FAFH prices to changes in the binding state or local minimum wage.
2. **Treated-month model:** Compares months with a minimum-wage increase against untreated months.
3. **Dynamic model:** Includes lead, contemporaneous, and lagged wage changes to examine timing.
4. **Multistate sensitivity model:** Uses an alternative treatment measure for metropolitan areas spanning multiple states.
5. **Year-month fixed-effects model:** Absorbs shocks common to all metropolitan areas in a given month.

## Main findings

Across the principal specifications, estimated pass-through was generally positive but small and statistically imprecise. The alternative treatment construction produced a similar qualitative conclusion, while the dynamic specification was unstable.

The results therefore do not provide strong evidence of a clear short-run restaurant-price response in this limited three-metro sample. The analysis emphasizes uncertainty, treatment sparsity, and sensitivity to specification choices.

## Technical tools

- R and R Markdown
- `dplyr`, `tidyr`, `readr`, `readxl`, and `lubridate`
- `quantmod` for FRED data retrieval
- `fixest` for fixed-effects regressions
- `ggplot2` for visualization
- Reproducible CSV, text, and figure exports

## Selected figures

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 1.25rem; margin: 1.5rem 0;">
  <figure style="margin: 0;">
    <a
      href="{{ '/assets/img/projects/minimum-wage/treatment_calendar_plot.png' | relative_url }}"
      data-lightbox="minimum-wage-gallery"
      data-title="Treatment calendar by metro"
    >
      <img
        src="{{ '/assets/img/projects/minimum-wage/treatment_calendar_plot.png' | relative_url }}"
        alt="Calendar of minimum-wage increases across Chicago, Los Angeles, and New York"
        style="width: 100%; border-radius: 8px"
      >
    </a>
    <figcaption style="margin-top: 0.6rem; font-size: 0.95rem;">
      <strong>Treatment timing and intensity.</strong> Each tile marks a month in which a metro experienced a minimum-wage increase, with the label showing the size of the increase. The figure highlights that identifying variation comes from a relatively small and unevenly distributed set of policy changes.
    </figcaption>
  </figure>

  <figure style="margin: 0;">
    <a
      href="{{ '/assets/img/projects/minimum-wage/model_5_plot.png' | relative_url }}"
      data-lightbox="minimum-wage-gallery"
      data-title="Pass-through estimates across core specifications"
    >
      <img
        src="{{ '/assets/img/projects/minimum-wage/model_5_plot.png' | relative_url }}"
        alt="Estimated restaurant-price pass-through under the main, alternative-mapping, and stricter fixed-effects models"
        style="width: 100%; border-radius: 8px"
      >
    </a>
    <figcaption style="margin-top: 0.6rem; font-size: 0.95rem;">
      <strong>Robustness across specifications.</strong> The points compare implied FAFH price changes for a 10% minimum-wage increase under the main model, an alternative treatment mapping, and stricter year-month fixed effects. Estimates remain small, while the wide intervals show substantial uncertainty.
    </figcaption>
  </figure>
</div>

Together, the figures show both the source of the research design's identifying variation and the central empirical conclusion: treatment events are sparse, and the estimated short-run price response remains small and imprecise across the principal specifications.

## Limitations

The panel contains only three metropolitan areas and a relatively small number of treated metro-months. Clustered inference is therefore fragile, and the results should be interpreted as an exploratory econometric exercise rather than definitive causal evidence.

Additional work could expand the metro sample, improve treatment mapping, test heterogeneous effects across restaurant categories, and use alternative event-study estimators designed for staggered policy adoption.

## Takeaways

This project strengthened my experience with panel-data construction, difference-in-differences research design, fixed-effects regression, robustness analysis, economic interpretation, and empirical workflows in R.