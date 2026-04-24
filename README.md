# Life-Insurance-Pricing-Model-
Actuarial term life insurance premium pricing model using SOA mortality tables — Excel &amp; Python
Term Life Insurance Pricing Model
Actuarial Analysis Using SOA Mortality Experience Data

Project Overview
This project develops a term life insurance pricing model for a $500,000, 20-year term policy using real industry mortality data from the Society of Actuaries (SOA).The analysis starts with raw data, conducting an Actual vs. Expected (A/E) mortality study, and using those findings to produce defensible premium rates across a range of policyholder profiles and economic scenarios.
Key finding: A 35-year-old nonsmoker should pay approximately $478/year ($39.80/month) for a $500,000 20-year term policy under a 5% interest rate assumption — consistent with current market rates of $30–$45/month.

 Question:

How should a regional life insurer price a 20-year term product, and how sensitive is that price to mortality experience and economic assumptions?

Data Source
SOA 2003–2013 Individual Life Insurance Mortality Experience Study

Source: Society of Actuaries (soa.org)
Subset used: Term insurance, Nonsmoker, Ages 25–75
Working dataset: 339,306 policy records after filtering
Key fields: Attained Age, Policies Exposed, Actual Deaths, Expected Deaths (2015 VBT)


Methodology
Step 1 — A/E Mortality Analysis
Aggregated raw policy records by attained age to calculate:

Actual qx — observed mortality rate from experience data
Expected qx — 2015 Valuation Basic Table (VBT) predicted mortality
A/E Ratio — actual ÷ expected, measuring how well the industry table predicted real experience

Finding: A/E ratios were consistently above 1.0 across all age groups, indicating the 2015 VBT underestimated mortality for this study period. The gap widens significantly at ages 60+, likely reflecting mortality improvement trends — people are living longer today than during the 2003–2013 observation period.
Step 2 — Premium Pricing Model
Applied the actuarial equivalence principle: the gross premium is the value that equates the present value of expected premiums to the present value of expected death claims, loaded for expenses and profit.
Model components:

Survivor projection accounting for mortality (actual qx) and lapse rates (3% annually)
Death claim projection: expected deaths × $500,000 face amount
Time value of money: all cash flows discounted at the assumed interest rate
Expense loading: 15% of gross premium
Profit margin: 10% of gross premium

Step 3 — Sensitivity Analysis
Calculated gross premiums across a grid of issue ages (25–55) and interest rates (3%–7%) to quantify how pricing assumptions affect outcomes.

Results
Premium Pricing Output (5% Interest Rate)
Issue AgeMonthly PremiumAnnual Premium25$19.29$231.5430$26.59$319.0435$39.80$477.5840$63.17$758.0345$103.76$1,245.1650$174.81$2,097.7255$304.82$3,657.86
Sensitivity Analysis — Gross Annual Premium ($)
Issue Age3% Interest4% Interest5% Interest6% Interest7% Interest25$239.24$235.27$231.54$228.03$224.7630$334.46$326.55$319.04$311.94$305.2435$505.83$491.36$477.58$464.48$452.0640$804.16$780.54$758.03$736.64$716.3445$1,324.77$1,283.97$1,245.16$1,208.34$1,173.4950$2,242.82$2,168.38$2,097.72$2,030.80$1,967.5755$3,931.07$3,790.79$3,657.86$3,532.20$3,413.69
Key insight: Interest rate sensitivity increases significantly with issue age. For a 25-year-old, moving from 3% to 7% reduces the premium by ~6%. For a 55-year-old, the same rate shift reduces the premium by ~13% — meaning economic assumptions matter far more when pricing older policyholders.

Visualizations
Chart 1 — A/E Ratio by Age
Actual mortality consistently exceeded 2015 VBT predictions, with the gap widening at older ages.
Chart 2 — Actual vs Expected Mortality Curves
Both curves follow the expected exponential shape, with actual experience diverging above the VBT benchmark at ages 50+.
Chart 3 — Death Claims Projection
Expected annual death claims increase steadily over the policy term as the insured population ages.
Chart 4 — Premium Sensitivity Analysis
Five interest rate scenarios plotted across issue ages 25–55, illustrating the exponential relationship between age and premium cost.

Repository Structure:


life-insurance-pricing-model/
├── README.md
├── data/
│   ├── term_mortality_data_clean.xlsx    # Filtered SOA experience data
│   ├── ae_ratio_chart.png                # A/E ratio visualization
│   ├── actual_vs_expected_qx.png         # Mortality curve comparison
│   ├── death_claims_projection.png       # Claims projection chart
│   └── sensitivity_analysis.png         # Premium sensitivity chart
├── excel/
│   └── term_life_pricing_model.xlsx      # Excel pricing model and dashboard
└── python/
    └── term_life_pricing_analysis.ipynb  # Jupyter notebook with full analysis

Tools & Skills Demonstrated
ToolApplicationPython (pandas)Data loading, filtering, groupby aggregationPython (numpy)Actuarial calculations and array operationsPython (matplotlib)Professional data visualizationJupyter NotebookReproducible analytical workflowMicrosoft ExcelSUMIF modeling, Solver optimization, conditional formattingSOA Experience DataReal industry mortality data processing

Actuarial Concepts Applied

Mortality rates (qx) — probability of death within a policy year
Actual vs Expected (A/E) analysis — measuring experience against industry benchmarks
Equivalence principle — foundational pricing methodology from Exam P/MLC
Present value of annuities — time value of money applied to premium streams
Lapse rate modeling — policyholder behavior assumptions
Gross premium loading — expense and profit margin incorporation
Mortality improvement — interpretation of historical vs modern experience divergence
Sensitivity analysis — quantifying assumption risk in pricing models


Further Extensions: 

Incorporate gender as a rating factor and compare male vs female pricing
Add a lapse rate sensitivity analysis alongside the interest rate sensitivity
Model the impact of different face amounts ($250k, $500k, $1M)
Compare pricing results against publicly available term life rate filings
Extend the model to a whole life or universal life product


About
Built as a portfolio project demonstrating actuarial and data analysis skills relevant to entry-level roles in life insurance pricing and actuarial consulting.
Exams passed: Exam P, Exam FM
Tools: Python, Excel, GitHub
Data: SOA 2003–2013 Individual Life Insurance Mortality Experience Study
