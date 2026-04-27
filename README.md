# Marketing Science Portfolio
### Causal Inference & Incrementality Measurement

This repository contains applied marketing science work focused on **causal measurement frameworks** — the methods that tell you what actually *caused* a business outcome, not just what correlated with it.

Built by a Director-level analytics leader with experience designing and scaling experimentation programs across large retail and e-commerce organizations.

---

## Projects

### 📊 [Geo Holdout Test: Measuring Paid Search Incrementality](./geo_holdout_incrementality.ipynb)

**Business question:** How many bookings does paid search actually drive — beyond what organic demand would have produced anyway?

**Method:** Geo holdout experiment + Difference-in-Differences (DiD) estimation

**What's inside:**
- Methodology selection rationale (geo holdout vs. MMM vs. user-level A/B)
- Experimental design: market selection criteria, parallel trends validation, power considerations
- Full DiD regression with confidence intervals and coefficient visualization
- Business translation: incremental ROAS, scenario ranges, and an explicit go/no-go recommendation
- Documented assumptions and conditions that would change the recommendation

**Tools:** Python · pandas · statsmodels · matplotlib · scipy

---

## Measurement Philosophy

Good incrementality measurement answers three questions in order:

1. **Is the effect real?** — statistical validity, parallel trends, significance
2. **How big is it?** — effect size, confidence interval, practical significance
3. **What should we do about it?** — business recommendation with explicit assumptions

Most measurement work stops at #1 or #2. The value is in #3.

---

## Methods Covered (Roadmap)

| Method | Notebook | Status |
|---|---|---|
| Geo Holdout + DiD | `geo_holdout_incrementality.ipynb` | ✅ Published |
| Synthetic Control | `synthetic_control.ipynb` | 🔜 Coming |
| Causal Inference Method Comparison | `method_comparison.ipynb` | 🔜 Coming |
| AI-Augmented Measurement Workflow | `ai_measurement_workflow.ipynb` | 🔜 Coming |

---

## About

I'm a data and analytics leader focused on the intersection of **causal measurement, business strategy, and marketing effectiveness**. This portfolio reflects the type of thinking I bring to marketing science problems — from experimental design through to executive recommendation.

Connect on [LinkedIn](https://www.linkedin.com/in/oliviapan) · Questions or collaboration: open an issue.
