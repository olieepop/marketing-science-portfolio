# Marketing Science Portfolio

Causal inference and incrementality measurement - the part of analytics where the question is harder than the math.

Just saving some notes here to document my thoughts and process running GEO holdout analysis. 

---

## What's here

### 📊 [Geo Holdout Test: Measuring Paid Search Incrementality](./geo_holdout_incrementality.ipynb)

This is a common question business usually encounter : how many bookings/demand/orders/sales do paid search actually drive, versus how many would have happened anyway?

Last-click attribution has a convenient answer to that question. It's also usually wrong considering it usually captures how conversion was made but not created. This notebook works through a geo holdout framework : the method I'd reach for first when you need a defensible, business-ready incrementality estimate for a paid channel.

**What's covered:**
- Why geo holdout over MMM or user-level A/B (and when that call changes)
- Market selection and the parallel trends check most teams skip
- Difference-in-Differences estimation with confidence intervals
- Translating the output into an actual budget recommendation — not just a lift number

**Stack:** Python · pandas · statsmodels · matplotlib · scipy

---

## How I think about measurement

Getting to a statistically significant result is the easy part. The harder questions are:

- Is the effect size meaningful enough to act on?
- What would have to be true for this recommendation to be wrong?
- What does the business actually do differently because of this number?

Most measurement work I've seen stops before those questions. That's the gap I'm interested in closing.

---

## What's next

| Notebook | Method | Status |
|---|---|---|
| `geo_holdout_incrementality.ipynb` | Geo Holdout + DiD | ✅ Live |
| `synthetic_control.ipynb` | Synthetic Control | 🔜 In progress |
| `method_comparison.ipynb` | DiD vs SC vs PSM — when to use which | 🔜 In progress |
| `ai_measurement_workflow.ipynb` | AI-augmented analytical workflows | 🔜 In progress |

---

## About

Analytics leader with a background in large-scale consumer insights, product/UX experimentation, marketing measurement, and the unglamorous work of getting organizations to actually use what the data says. (at lesat I tried.)

Previously: Nike, Director of BI Development (2018–2026).  
Currently: building in public.

[GitHub](https://github.com/olieepop) · [LinkedIn](https://www.linkedin.com/in/oliviapan)
