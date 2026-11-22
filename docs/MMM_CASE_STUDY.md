# M3 · Marketing Mix Modeling with Google Meridian

**Exploratory synthetic case study — public fast-restoration executed; full independent refit and causal validation pending**

> **Business question:** A fictional DTC replenishment retailer spends across Search, Social and Display. Which channels appear to produce additional revenue, and how would a fixed budget be reallocated under a Bayesian MMM? This is a controlled synthetic research exercise, **not** a real deployed advertising campaign.

## From a marketing correlation to a measurement question

We modeled **48 simulated markets × 120 pre-experiment weeks = 5,760 geo-weeks**. Sales and media observations come from a unified synthetic data-generating process that also produces customer journeys, transactions and researcher-only counterfactual worlds. The MMM does **not** use these withheld truth labels to fit its coefficients.

The modeling question is more demanding than “Which advertising channel appears beside the most sales?” Shoppers may buy without ads, and organic intent/seasonality can influence both marketing exposure and conversions. We therefore started with an understandable regression benchmark before fitting Google Meridian.

## 1 · Regression baseline: why controls matter

A geo-fixed-effects OLS model gave a combined media-spend coefficient of approximately **10.8** (R² **0.59**) before adding business controls. When we added observed organic queries, promotion discounts, list-price changes and competitor conditions, the coefficient fell to **3.0147** (R² **0.703**); the market-clustered 95% confidence interval was **[2.46, 3.57]**. This is an *observational association* and is **not** verified incremental ROAS.

## 2 · Meridian Bayesian model

The analysis uses **Google Meridian 2.2.0**, three impressions-based media channels with separately supplied USD spend, four observed controls, a balanced random **20% geo-week predictive holdout**, and **2 MCMC chains × 1,000 retained posterior draws**. A checksummed posterior is publicly distributed in `artifacts/mmm/` and restored using fixed versioned inputs, without Google Drive or manually uploaded files. This reproduces the previous fit’s analysis; full Bayesian resampling is a separate, as-yet-unverified workflow.

The model represents media **adstock** (carryover) and **Hill saturation** (diminishing returns), and estimates distributions rather than a single unquestioned channel effect. Holdout model fit is not the same as a randomized incremental advertising experiment.

## 3 · Observed results and uncertainty

| Measurement | Reported result |
|---|---:|
| Train / test R² | 0.9978 / **0.8803** |
| Test wMAPE | **6.14%** |
| Total modeled revenue | ~$8.31M |
| Baseline contribution | ~$6.49M, roughly 78% |
| Modeled media revenue | ~$1.065M Social, ~$612K Search, ~$147K Display |
| **Posterior mean** channel ROI | **6.43× Social, 3.21× Search, 3.64× Display** |

See [original official Meridian model results report](../reports/mmm/MMM_Meridian_Model_Results.html) for channel contribution and ROI visualizations.

**Interpretation:** Social leads the model's estimated average media ROI and modeled incremental contribution. Display's posterior has high relative uncertainty and a long upper tail; a high posterior mean is not a point of precise causal truth. A model can predict observed revenue well while misallocating channel effects when ad exposure and underlying intent are correlated.

## 4 · Health score versus stricter convergence

Meridian produced an official **100.0/100 model-health score**, with all six automated checks passing, including a convergence pass under its own reported screening criteria. A separate **rank-normalized R-hat** calculation found significant mixing concerns: maxima of **1.3781** for `knot_values` and `mu_t`, **1.1924** for `tau_g`, and **1.0218** for media ROI (`roi_m`). **44.7% of finite parameter elements** exceeded R-hat 1.05. We have not resolved why the automated health card and the separate calculation present different views of convergence. **We therefore do not call this fit decision-grade.**

## 5 · A fixed-budget optimization scenario

Google Meridian's historical fixed-budget optimizer proposed the following mix, subject to its **default ±30% per-channel constraints**. These limits were applied by the library; they were **not an explicit budget policy chosen by the owner**.

| Paid channel | Historical spend | Modeled optimized spend | Difference |
|---|---:|---:|---:|
| Search | $190,700 | $147,600 | −$43,100 |
| Social | $165,700 | $215,400 | +$49,700 |
| Display | $40,500 | $33,900 | −$6,600 |
| **Total** | **$396,900** | **$396,900** | **$0** |

See [original official Meridian optimization report](../reports/mmm/MMM_Meridian_Budget_Optimization.html) for the allocation chart.

The model predicted **+$68,228 in incremental revenue**, approximately **+3.74%** relative to the baseline modeled media contribution, without increasing the historical budget. **Social is at the +30% ceiling**—so this allocation is the best modeled result *under the imposed scenario bounds*, not necessarily the unconstrained optimum. The $68K is **not realized revenue**, an experimental finding, or a verified future forecast.

## What is the defensible takeaway?

**Social is the leading channel under our exploratory Bayesian MMM, and the fixed-budget optimizer suggests a transfer from Search and Display into Social.** That is a *hypothesis to test*, not a final causal allocation recommendation. Strong predictive fit and a green automated health card have not resolved baseline chain mixing or the DGP's demand confounding.

The major lesson is to separate **model fit**, **convergence**, **causal identification** and **conditional budget optimization**. A strong result in one category does not certify the others.

## Source materials and replication status

- [Portable Meridian notebook with saved execution outputs](../notebooks/02_Meridian_MMM_Portable.ipynb)
- [Official Meridian model-results HTML](../reports/mmm/MMM_Meridian_Model_Results.html)
- [Official Meridian model-health HTML](../reports/mmm/MMM_Meridian_Model_Health.html)
- [Official Meridian optimization HTML](../reports/mmm/MMM_Meridian_Budget_Optimization.html)
- [Versioned model artifact and file hash manifest](../artifacts/mmm/manifest.json)
- [Observable weekly input dataset](../mmm_geo_weekly.csv) and [synthetic release configuration](../release.json)

**Reproduction disclosure (2026-11-22):** A clean public-input Colab run successfully downloaded and checksum-verified three public inputs, restored the 2 × 1,000 saved posterior and generated all three HTML reports, with 12/12 executed code cells and no error outputs. The notebook was subsequently pinned to the exact data/model input commit; that final URL change needs a brief rerun before calling the pinned version tested. The committed HTML reports were generated from the earlier exploratory fit; readers can regenerate their own reports using the notebook. This fast run is **not an independent full model refit**.

## Next in the complete Marketing Measurement Lab

Separate project workstreams will compute **M4: last-touch/MTA**, **M5: independent simulated Social geo-incrementality**, and then **M6: triangulation** with explicitly aligned estimands and the separately withheld simulator causal truth. Only after those comparisons, plus targeted MMM convergence follow-up, will we make a final evidence-weighted budget recommendation.

**Milestone:** M3 exploratory execution and public fast-restoration demonstrated; full M3 scientific acceptance criteria and independent refit remain open. Synthetic observations are not evidence of a live campaign.
