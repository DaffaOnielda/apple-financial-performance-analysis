# Apple's Profitability Paradox: Financial & Valuation Analysis (2020–2025)

**Ever wondered why a company's stock can hit all-time highs even when their profit margins take a massive hit?**

Welcome to our data-driven deep dive into Apple Inc. As part of our Programming for Business Analytics coursework at NTHU, we wanted to look beyond the basic financial news headlines and actually crunch the numbers on a weird anomaly: Apple's net profit margin dropped in 2024 (mostly due to that €13 billion European Commission tax ruling), yet investors kept pushing the stock price up. Through data wrangling, statistical analysis, and building a custom "Normalized Growth Index" in R, this report breaks down how market optimism around Apple's Services segment and the "AI Supercycle" completely overpowered the negative signals from their statutory margins.

## What I Used & What I Did
I built the analytical pipeline in **R**, mostly living inside the `tidyverse`. 

* **Data Wrangling:** The raw financial CSVs were a mess. I wrote custom functions to force-split messy strings, used priority-based matching to grab the exact metrics needed (so I wouldn't accidentally grab "Net Interest Income" instead of "Net Income"), and pivoted everything for time-series analysis.
* **Visualization:** Used `ggplot2` to plot the divergence between profitability and stock price, and to build the Growth Index.
* **Stats & Modeling:** Ran Pearson correlations and fitted a simple linear regression to prove the inverse relationship statistically. 

The baseline regression model I tested looks like this:
$$StockPrice = \beta_0 + \beta_1(NetProfitMargin) + \epsilon$$

## The "TL;DR" Findings
1. **The "Tax Noise":** That 2024 margin drop? It wasn't a broken business model. It was a discrete fiscal event (the EU tax penalty). The market basically identified it as noise and ignored it.
2. **Cash is King:** The stock performance actually had a strong positive correlation with EBITDA growth ($r = +0.79$). Investors cared way more about operational cash flow scale than the final, tax-impacted net income.
3. **Valuation Multiple Expansion:** My Normalized Growth Index showed the stock price completely decoupling from net income growth around late 2023. The market stopped pricing Apple strictly on its current hardware margins and started pricing in the future potential of the Apple Intelligence ecosystem.

## What's in this Repo?
* `Group 4 FINAL REPORT.Rmd`: The brain of the project. All the R code, custom cleaning functions, and statistical modeling.
* `Group-4-FINAL-REPORT.pdf`: The final, clean research report if you just want to read the business insights and see the charts.
* `AAPL_Income_Statement.csv` & `AAPL_Balance_Sheet.csv`: The raw corporate datasets used.
* `AAPL_Historical.csv`: The historical daily stock market data.

## The Team & Acknowledgments
This research was a collaborative effort for our Programming for Business Analytics coursework at NTHU. As the primary contributor, I led the data pipeline and scripting, but huge shoutout to my amazing teammates who co-authored this report:

* **M. Daffa AO (Me) - Project Lead & Lead Data Analyst:** Spearheaded the project, wrote the core R scripts, engineered the data wrangling pipeline (custom splitting and matching functions), developed the Normalized Growth Index, and conducted the statistical modeling.
* **Enrico Goritman - Financial Researcher:** Researched the macroeconomic events (EU Tax Ruling, AI Supercycle) and synthesized the business context for the discussion section.
* **Vibhav Mishra - Statistical QA:** Validated the Pearson correlation and Linear Regression methodologies to ensure statistical rigor.
* **Yeowon Seo - Visualization & Documentation:** Assisted in polishing the `ggplot2` visualizations and formatting the final R Markdown PDF compilation.

Feel free to poke around the `.Rmd` file or read the full PDF report to see the complete analysis!
