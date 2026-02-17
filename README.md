# Investment-Risk-Simulation

This looks like a solid Monte Carlo simulation for capital budgeting. You’ve effectively modeled the uncertainty of Net Present Value (NPV) and Internal Rate of Return (IRR) using a normal distribution.

Since this is for GitHub, you want a README that highlights the **analytical depth** of the project—not just the Excel formulas. Here is a professional template you can use.

---

# Capital Budgeting Risk Analysis (Monte Carlo Simulation)

This project provides a comprehensive financial risk assessment for a proposed capital investment. Using **Monte Carlo simulation**, the model moves beyond static "best-case/worst-case" scenarios to provide a probabilistic distribution of potential financial outcomes (NPV and IRR).

## 📊 Project Overview

The model evaluates a 10-year project with an initial investment of **£550,000**. Instead of assuming a fixed annual cash flow, the simulation accounts for volatility by applying a **Normal Probability Distribution** to the yearly Net Cash Flows (NCF).

### Key Financial Metrics

* **Initial Investment:** £550,000
* **WACC (Discount Rate):** 11.50%
* **Project Life:** 10 Years
* **Standard Deviation:** £95,000 (Adjustable via scroll bar for sensitivity analysis)

---

## 🚀 Features

* **Dynamic Simulation:** Utilizes a standard deviation toggle to visualize how increased market volatility impacts project viability.
* **Automated Statistics:** Calculates Mean, Median, Skewness, and Kurtosis for the simulated NPV/IRR data.
* **Risk of Loss Calculation:** Quantifies the probability of the project returning a negative NPV (currently calculated at **0.90%**).
* **Data Visualization:** Includes a frequency histogram displaying the NPV Normal Distribution across 1,000+ replications.

---

## 📈 Methodology

The simulation is built on the following logic:

1. **Stochastic Modeling:** Annual cash flows are generated using the `NORM.INV(RAND(), Mean, SD)` function.
2. **Iterative Replications:** The model runs multiple replications (as seen in Appendix 1) to build a statistically significant sample size.
3. **Net Present Value (NPV):** Calculated using the formula:
$$NPV = \sum_{t=1}^{n} \frac{NCF_{t}}{(1 + r)^{t}} - \text{Initial Investment}$$

4. **Internal Rate of Return (IRR):** Determines the discount rate at which the NPV equals zero.

---

## 🔍 Key Insights from Results

* **Profitability:** With a Mean NPV of **£419.53k** and a Mean IRR of **28%**, the project is highly attractive compared to the 11.5% WACC.
* **Stability:** The Skewness (-0.03) and Kurtosis (-0.10) indicate that the NPV distribution is nearly perfectly symmetrical and follows a normal bell curve, suggesting predictable risk.
* **Safety Margin:** The "Minimum" simulated NPV is -£224.24k, but the **Risk of Loss is extremely low (0.10% for IRR)**, suggesting the project is robust against variance.

---

## 🛠️ How to Use

1. Open the `.xlsx` file.
2. Adjust the **Standard Deviation** using the scroll bar in the "Project Detail" section.
3. Observe the real-time updates in the **NPV Normal Distribution** chart and the **Statistic** table.
4. Check the **Replication** table to see the raw data for individual simulation runs.
