# Hypothesis Testing & Inference on Global Sustainability (R)

**UOC MSc Data Science — RMarkdown project** applying descriptive analytics and classical inference to sustainability-related indicators. Focus on **hypothesis testing** and **statistical inference** using clean, reproducible R code.

---

## Highlights (for recruiters)

* Clear end-to-end **R workflow**: data prep → descriptives → **Welch t-test**, **paired t-test**, **two-proportion test**, **one-proportion test** → concise, interpretable conclusions.
* Reproducible RMarkdown (`Suesta_preproceso.Rmd`) with both **library** and **manual derivations** (z/t computed by hand for verification).
* Communication-first: each PR section states **H0/H1**, the **chosen test** (and why), **outputs**, and a short **interpretation**.

---

## Repository structure

```
.
├─ A2_20251_enunciado.pdf        # Assignment brief (statement)
├─ LICENSE                       # MIT
├─ README.md                     # You are here
├─ Suesta_preproceso.Rmd         # Main RMarkdown (source)
└─ Suesta_preproceso.html        # Rendered report (output)
```

---

## Data

* Source file used in the assignment: **WorldSustainabilityDS_clean.xlsx** (provided by the course).
* Variables renamed for readability inside the Rmd:

  * `LE`  = life expectancy (SP.DYN.LE00.IN)
  * `GINI` = inequality index (SI.POV.GINI)
  * `FOR` = net forest depletion (NY.ADJ.DFOR.GN.ZS; sustainability if **FOR ≤ 0**)

> Note: the Excel file is expected in the working directory when knitting.

---

## Methods & Tests

1. **PR1 – Life expectancy by income group (2018)**

   * Test: **Welch t-test** (two independent samples, unequal variances).
   * Result: **LE is higher** in High-income countries (p < 0.001).

2. **PR2 – Inequality change 2008 → 2018**

   * Test: **Paired t-test** (same country across two years).
   * World: **GINI decreased** (p ≈ 0.005).
   * Europe & Northern America: **no sufficient evidence of decrease** (p ≈ 0.182).

3. **PR3 – High inequality by regime (GINI > 40)**

   * Test: **Two-proportion test** (Democracy vs Autocracy, two-sided).
   * Result: **No difference** detected (p ≈ 0.891).

4. **PR4 – Net forest depletion compliance (FOR ≤ 0)**

   * Test: **One-proportion test** vs 0.5 (one-sided, greater).
   * Result: **Proportion > 50%** (p ≈ 0.014).

Each test is also **recomputed manually** (z/t formulas) to validate library outputs.

---

## How to run

1. Open `Suesta_preproceso.Rmd` in RStudio.
2. Ensure the file **WorldSustainabilityDS_clean.xlsx** is placed in the project root.
3. Knit to **HTML** (or PDF) → this builds all figures, tables, and the final summary table.

**R packages** (minimal): `dplyr`, `ggplot2`, `readxl`, `janitor`, `knitr`.
R ≥ 4.3 recommended.

---

## Key takeaways

* Demonstrates **statistical reasoning** on real indicators: income groups, time deltas, regime types, and sustainability targets.
* Emphasis on **test selection** (assumptions, directionality), **transparent reporting** (H0/H1, statistic, df, p-value), and **communication** of findings.
* Clean, compact R style suitable for **data science analytics** roles.

---

## Skills demonstrated

`R · Statistical Inference · Hypothesis Testing · Experimental Design · Data Cleaning · EDA · Reproducible Research (RMarkdown)`

---

## License

MIT — see `LICENSE`.

---

## Author

**Víctor Suesta Arribas** · UOC MSc Data Science
If you’re hiring for Data Analyst / Data Scientist roles and value clean inference + reproducible reporting, this project shows my approach.
