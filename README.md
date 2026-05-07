# Marketing Science Portfolio

A portfolio of applied causal inference projects built on realistic synthetic data. Each notebook tackles a real measurement problem a practitioner would face — wrong method for the context, and your number falls apart under scrutiny. These are designed to show not just the math, but the *reasoning* behind method selection.

All scenarios are e-commerce. All methods execute end-to-end with ground truth embedded so recovery accuracy is scoreable.

---

## Projects

| # | Notebook | Scenario | Method | Status |
|---|----------|----------|--------|--------|
| 1 | [`geo_holdout_incrementality.ipynb`](geo_holdout_incrementality.ipynb) | $15M paid search budget decision | Geo holdout + DiD | ✅ Live |
| 2 | [`synthetic_control_shop_the_look.ipynb`](synthetic_control_shop_the_look.ipynb) | 'Shop the Look' UX feature launch — North America | Synthetic Control + placebo permutation | ✅ Live |
| 3 | [`method_comparison.ipynb`](method_comparison.ipynb) | Program rollout — same question, three designs | DiD vs. Synthetic Control vs. PSM head-to-head | ✅ Live |
| 4 | [`compute_allocation.ipynb`](compute_allocation.ipynb) | Frames the Databricks budget problem as a constrained optimization. | Linear programming (PuLP), shadow prices / sensitivity analysis, Monte Carlo simulation | ✅ Live |
| 5 | `ai_measurement_workflow.ipynb` | AI-augmented analytical workflows | TBD | 🔜 Coming |
| 6 | `Queueing Ops` | Use case to translate "an AI tool deflected 40% of requests" into a staffing cost calculation with a defensible break-even point.  | TBD | 🔜 Coming |
| 7 | `Geo Experiments` | DiD TWFE + Synthetic Control + power table | TBD | 🔜 Coming |
| 8 | `Switchbacks` | Globally-trained personalization model framing maps directly to Nike | TBD | 🔜 Coming |


---

## Project Summaries

### P1 — Geo Holdout Incrementality
**Scenario:** A travel e-commerce platform is deciding whether to cut $15M in paid search spend. The question: is the channel driving incremental revenue, or capturing demand that would have converted anyway?

**Method:** Geo holdout design with Difference-in-Differences. Markets are split into treatment (spend reduced) and control (spend maintained). DiD regression with two-way fixed effects recovers the incremental revenue attributable to paid search — not just the correlated revenue.

**Covers:** Methodology selection rationale, parallel trends validation, DiD regression with region and time fixed effects, iROAS calculation, business recommendation framing.

---

### P2 — Synthetic Control: Shop the Look
**Scenario:** A blurred e-commerce platform (Nike-adjacent) launches a 'Shop the Look' UX feature in North America. The feature changes how users discover and bundle products. Does it lift conversion, AOV, bundle mix, and repeat visits — or just look good in dashboards?

**Method:** Synthetic Control with placebo permutation tests. Parallel trends fail explicitly (shown), justifying the SC approach. Donor pool: UK, Germany, France, Netherlands, Australia, Japan, South Korea, Brazil, Mexico. A single set of weights recovers four outcome metrics simultaneously.

**Covers:** Parallel trends failure as the decision gate for SC, scipy weight optimization under convexity constraints, placebo tests as the correct significance method for small donor pools, multi-outcome measurement from one synthetic control.

---

### P3 — Method Comparison: DiD vs. SC vs. PSM
**Scenario:** A collectio rolls out three ways simultaneously — geographic regions, a single country market (Japan), and user-level opt-in eligibility. Same business question. Three different right answers depending on data structure.

**Method:** Head-to-head comparison with ground truth ATT (+12%) embedded in all three DGPs so recovery accuracy is scoreable.

- **DiD:** 30 treatment / 60 control regions, two-way fixed effects, parallel trends validated — near-perfect recovery under ideal conditions
- **Synthetic Control:** Japan single-market launch, common factor donor pool, scipy weight optimization, permutation placebo tests — strong pre-period fit (R² > 0.93)
- **PSM:** 10K user opt-in design, logistic propensity model, 1:1 nearest-neighbor matching — reduces 32%+ naive selection bias toward truth; residual error explicitly acknowledged as expected, not a bug

**Covers:** Decision matrix (when to use which method), method selection flowchart (unit of treatment → assignment type → method), head-to-head recovery accuracy comparison, honest discussion of residual bias under conditional unconfoundedness.

Readme · MDCopyMarketing Science & Analytics Portfolio
Applied notebooks demonstrating measurement science, operations research, and experimentation methodology — grounded in ecommerce and marketing analytics contexts.

### P4 — Compute Budget Allocation Under Constraints
**Scenario:** An analytics engineering org runs multiple pipeline and modeling workloads on a shared Databricks cluster budget. Each workload has a different ROI — some power executive dashboards (high visibility, low tolerance for latency), others run batch ML inference (cost-sensitive, flexible SLA), others support ad-hoc analysis (bursty, unpredictable demand).

**Method:** 
- Linear programming (PuLP) for deterministic budget allocation
- Sensitivity analysis on shadow prices — what's the marginal value of another $1K in budget?
- Stochastic extension: Monte Carlo over demand uncertainty to find robust allocations

- **Techniques:** Linear programming (PuLP), shadow prices / sensitivity analysis, Monte Carlo simulation
- **Business question:** Given a fixed Databricks compute budget and SLA commitments across pipeline workloads, what allocation maximizes business value delivered?
- **Key output:** Shadow price on budget constraint (marginal ROI of budget increases); stochastic allocation under bursty demand.

---

## Skills Demonstrated

**Causal inference methods:** DiD (TWFE), Synthetic Control, Propensity Score Matching, geo holdout design, placebo permutation testing

**Statistical foundations:** Parallel trends validation, propensity score estimation, weight optimization under convexity constraints, permutation-based inference

**Measurement strategy:** Method selection given data structure constraints, iROAS framing, selection bias diagnosis, multi-outcome measurement design

**Tools:** Python (numpy, pandas, scipy, sklearn, matplotlib), Jupyter, statsmodels-compatible regression patterns

---

## Design Philosophy

These notebooks are not toy examples. Each one:
- Starts with a realistic business decision, not a textbook problem
- Selects the method based on what the data actually allows — not preference
- Validates assumptions explicitly before trusting results
- Quantifies recovery accuracy against ground truth where possible
- Frames outputs as business recommendations, not statistical artifacts

Method choice is constrained by data structure. The portfolio demonstrates knowing *when* each tool applies — which is the harder skill.

---

*Built as part of an active transition into Director-level incrementality and causal measurement roles.*
