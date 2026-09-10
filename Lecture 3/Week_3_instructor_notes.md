# Week 5 — Instructor notes (cohort analysis)

Polished student notebook: `Week_5_Cohort_Analysis.ipynb`  
Drop this file into the [course repo](https://github.com/armhijacker/customer_behaviour) next to `data/data_cleared.csv` and `docs/cohort.png`. A copy of the figure is already in `docs/` here.

## What was wrong in the original

The old notebook was a thin code walkthrough: one definition block, then groupby → pivot → two heatmaps, then a spend chart that repeated the same pattern. Fine as a lab scrap, weak as a lecture.

Concrete problems:

- **Broken / sloppy presentation.** Unused imports (`re`, `mcolors`), commented-out scratch cells, an empty last cell, axis label `Period Number'`, y-label “Month of Purchase” on a chart whose rows are *first* purchase month.
- **Wrong grain.** `InvoiceNo: count` on line items counts products, not orders. `TotalPrice: mean` on line items is not customer spend.
- **Spend chart was mislabelled.** Dividing average spend by period-0 spend is an *index*, not a retention rate. The heatmap used `mask=cohort_pivot.isnull()` (the customer-count frame) instead of the spend frame.
- **Behavioral cohorts were defined and never built.**
- **No interpretation protocol.** Students were left staring at a red-green grid.
- **Retail vs subscription never stated.** In this dataset a quiet month is not churn; the heatmap can go up.

## What the new lecture adds

1. Learning objectives and a 90-minute agenda.
2. A 3-customer toy table *before* the 400k-row file — period, empty vs zero, reactivation.
3. New vs returning stacked bar (growth vs engagement in one picture).
4. Shared `plot_cohort_heatmap` helper; correct labels; period-0 unit test.
5. Average retention curve with a “how many cohorts feed this point” bar (right-censoring).
6. Spend among actives + spend index + period-1 customer vs revenue retention gap.
7. High vs low first-month spend (the missing behavioral cohort).
8. Mistake table, course map to RFM / churn, four exercises with hidden sketches.

If `data/data_cleared.csv` is absent the loader synthesizes a smaller retail file so the live demo still runs. Prefer the real file in class.

## Pacing

| Min | Do this | Do not skip |
|-----|---------|-------------|
| 0–10 | Vanity-metric story + vocabulary | Activity vs subscription |
| 10–25 | Toy table on paper, then run the two cells | “Empty is not zero” and “A came back” |
| 25–45 | Real grain, first observed month, stacked bar | Left-censoring sentence |
| 45–65 | Heatmaps + four reading questions | Column read (is the product improving?) |
| 65–80 | Spend + behavioral split | Index ≠ retention |
| 80–90 | E1 live, assign E2/E3 | Quote a period-1 number out loud |

## Live numbers to ask for (real file)

On the UCI Online Retail window (Dec 2010–Dec 2011) expect:

- Period 1 monthly retention typically in the **20–40%** band, not 80%.
- December 2010 is a large, left-censored first cohort — treat it as “first observed,” not “new to the brand.”
- Later columns for late-2011 cohorts are incomplete. If a student says “November churned,” send them back to right-censoring.

Exact percentages depend on the cleaned file; do not memorize a slide number. Compute E1 in front of them.

## If you only have 45 minutes

Keep: sections 1, 2, 3, 4 (counts + % heatmaps), mistake table.  
Cut: spend index, revenue-retention gap, behavioral curves, E2–E4.
