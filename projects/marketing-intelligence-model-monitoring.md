---
layout: default
title: Marketing Intelligence & Model Monitoring System
description: Synthetic-data portfolio case study using Python, PyMC and Power BI to analyse marketing performance and monitor model outputs.
permalink: /projects/marketing-intelligence-model-monitoring/
---

# Marketing Intelligence & Model Monitoring System

**Python · pandas · Statistical Modelling · PyMC · Power BI**

An end-to-end portfolio project exploring how a marketing analytics team could investigate paid-media performance, audit data quality, build an illustrative marketing mix model (MMM), and monitor revenue predictions.

<blockquote>
<strong>Project scope:</strong> Independent portfolio project using synthetic e-commerce data. It is not a production deployment or a case study for a real advertiser.
</blockquote>

## Business question

How can an analyst distinguish changes in marketing performance from data-quality problems and model-prediction errors, then communicate the findings to decision-makers?

## Project overview

The simulated dataset covers 104 weekly periods across 2024–2025 and three advertising channels: Google Ads, Meta Ads, and TikTok Ads. It combines advertising performance, weekly sales, and promotion/seasonality data.

The workflow covers:

1. Data profiling, quality auditing, and remediation.
2. Channel-level marketing performance analysis.
3. Adstock and Hill saturation feature engineering.
4. Regression-based and Bayesian modelling.
5. Weekly business, data-quality, and model monitoring.
6. A three-page Power BI report.

## Analytical workflow

### 1. Data quality and preparation

Introduced and investigated representative data issues, including missing values, a duplicate record, inconsistent campaign labels, and a negative spend value. Documented remediation decisions and created a clean modelling input.

Simulation-only ground-truth fields were excluded from model predictors to avoid target leakage. Missing spend values interpolated for time-series modelling are treated as assumptions, not observed values.

### 2. Marketing performance

Calculated channel-level CTR, CVR, CPC, and CPA alongside spend, clicks, and conversions.

The weekly ROAS measure is **blended ROAS**: total business revenue divided by total advertising spend. It is not channel-attributed or incremental ROAS. Blended CAC is advertising spend divided by new customers.

### 3. Illustrative marketing mix model

Built a regression model using adstock and Hill saturation transformations, promotion and seasonality variables, and a chronological train/test split.

The adstock decay and Hill half-saturation parameters were assumed for the simulation. Modelled channel contributions are associations under the model specification, not causal or incremental effects.

### 4. Bayesian regression

Fitted a Bayesian regression model in PyMC with weakly informative Normal priors. Reviewed R-hat, effective sample size, divergences, and posterior predictive checks.

Good convergence diagnostics support the sampling run; they do not prove model validity, causal identification, or generalisability.

### 5. Monitoring

Generated weekly monitoring outputs for:

- blended revenue, advertising spend, ROAS, and CAC;
- spend movement versus a rolling historical baseline;
- advertising data-quality issue counts and flags; and
- actual-versus-predicted revenue error.

The 30% spend-change rule and 10% absolute percentage error rule are illustrative alert thresholds, not industry standards.

## Power BI report

The dashboard contains three pages:

| Page | Focus |
|---|---|
| Executive Overview | Headline business metrics, weekly revenue and spend trends, alert status |
| Channel Performance | Channel spend, clicks, conversions, CPC/CPA comparisons |
| Model Health & Anomalies | Actual versus predicted revenue, residuals, model alerts, data-quality flags |

## Key outputs

- Data-quality audit
- Channel performance metrics
- MMM model input and predictions
- Modelled channel contribution estimates
- Bayesian coefficient summary and trace
- Marketing monitoring report
- Model monitoring report

## Tools and skills demonstrated

**Tools:** Python, pandas, PyMC, Google Colab, Power BI.

**Skills:** Data quality, marketing analytics, regression modelling, time-series feature engineering, adstock and saturation concepts, Bayesian regression, model diagnostics, monitoring logic, dashboard design, and analytical communication.

## Limitations

- All observations are synthetic and findings are illustrative.
- No real platform attribution or customer-level journey data is used.
- Revenue is not allocated to individual advertising channels.
- Adstock and saturation parameters are simulation assumptions.
- Channel contributions are not causal estimates.
- Alert thresholds are demonstration rules requiring business-specific calibration.
- This is an analytical prototype, not a deployed production monitoring service.

## Project files

- [GitHub project repository](https://github.com/oluwaseun-tech/marketing-intelligence-model-monitoring)
- The repository currently includes the project documentation, dependency specification, selected result exports, and a downloadable cleaned notebook bundle.
- The original CSV data set files and Power BI `.pbix` dashboard are not yet committed to the repository; they remain in the project ZIP shared for publication.

---

**Author:** Oluwaseun Aribisogan · [GitHub](https://github.com/oluwaseun-tech) · [LinkedIn](https://www.linkedin.com/in/oluwaseun-aribisogan)
