# Model Specification: Foreign Exchange Hedging Strategies

**Created by:** Kaye Talioaga   
**Updated by:**  Kaye Taliaoga  
**Date Created:**  April 2026  
**Date Updated:**  April 2026  
**Version:**  1.0

---

## 1. Objective

The company is exposed to foreign exchange risk due to a **foreign-currency receivable (FC_AMT)** that will be settled in the future (**T_DAYS**). Because exchange rates fluctuate, the USD value of this receivable is uncertain and could decrease if the foreign currency depreciates.

The objective of this model is to:
* **Evaluate and compare** three hedging strategies: Forward Hedge, Money Market Hedge, and Option Hedge.
* **Determine** which strategy provides the most stable and favorable USD outcome.
* **Quantify** risk exposure and identify trade-offs between certainty, cost, and upside potential.

---

## 2. Scope

### **In-Scope**
* **Exposure:** Single foreign-currency receivable.
* **Calculations:** Forward, Money Market, and Option hedge valuations.
* **Analysis:** Sensitivity testing of exchange rate movements ($\pm5\%$).
* **Comparison:** Comparative analysis of USD proceeds across all strategies.

### **Out-of-Scope**
* Multi-currency or portfolio-wide hedging.
* Dynamic or rolling hedging strategies.
* Credit, liquidity, and counterparty risks.
* Complex accounting treatments (e.g., specific hedge accounting entries).
* Transaction costs beyond the explicitly stated assumptions.

---

## 3. Inputs
*All inputs are defined using standardized named ranges to ensure clarity and reproducibility.*

| Named Range | Description | Unit | Value |
| :--- | :--- | :--- | :--- |
| **FC_AMT** | Foreign-currency receivable | EUR | 20,000,000 |
| **S0_in** | Spot rate at inception | USD/EUR | 1.0831 |
| **F0_in** | Forward rate (1-year) | USD/EUR | 1.0935 |
| **R_USD** | USD interest rate | Annual % | 5.00% |
| **R_FC** | Euro interest rate | Annual % | 4.00% |
| **K_PUT** | Put option strike | USD/EUR | 1.09 |
| **PREM_PUT** | Put premium | USD/EUR | 0.019 |
| **T_DAYS** | Time to settlement | Days | 360 |

**Data Source:** Model assumptions and provided case inputs.

---

## 4. Workflow & Methodology

### **Step 1: Define Exposure**
* **Asset:** €20,000,000 receivable.
* **Timeline:** Settlement in 360 days.
* **Baseline:** Current spot rate of **1.0831 USD/EUR**.

### **Step 2: Forward Hedge**
* **Action:** Lock in the forward rate of **1.0935 USD/EUR**.
* **Calculation:** $€20,000,000 \times 1.0935 = \$21,870,000$.
* **Outcome:** Risk is eliminated; the final USD amount is guaranteed.

### **Step 3: Money Market Hedge**
1.  **Discount:** Calculate the PV of the EUR receivable at the 4% EUR rate.
2.  **Convert:** Exchange the EUR PV for USD at the current spot rate (**1.0831**).
3.  **Invest:** Place USD in a 1-year deposit at the 5% USD rate.
* **Final Proceeds:** **$21,870,288**.
* **Outcome:** Parity confirmed; results are nearly identical to the Forward Hedge.

### **Step 4: Option Hedge (Put Option)**
* **Strike (K):** 1.09 | **Premium Cost:** $0.019 \times €20,000,000 = \$380,000$.
* **Scenarios:**
    * **Worst-Case (Exercise):** Net proceeds of **$21,401,000**.
    * **Best-Case (Favorable Spot):** Upside potential if the EUR appreciates (e.g., **$22,347,000**).
* **Outcome:** Provides a "floor" while allowing for profit if rates move favorably.

### **Step 5: Sensitivity Analysis**
* **Parameters:** Test a range of exchange rates from **0.95 × 1.0831** to **1.05 × 1.0831**.
* **Method:** Use 1% increments to visualize how each strategy performs under volatility.

---

## 5. Expected Outputs

* **Summary Results Table:** A snapshot of the total USD proceeds for each strategy.
* **Sensitivity Table:** A data grid indexing USD outcomes against exchange rate shifts.
* **Comparison Chart:** A visual line graph illustrating the "break-even" points.
* **Strategic Insights:**
    * **Forward:** Best for budget certainty.
    * **Money Market:** Used to verify market efficiency/parity.
    * **Option:** Best for maintaining upside potential in a volatile market.

---

## 6. Evaluation Criteria

* **Clarity:** Is the documentation structured logically and easy for a stakeholder to follow?
* **Accuracy:** Are the financial formulas and interest rate conventions applied correctly?
* **Reproducibility:** Can a third party rebuild the Excel model using only this specification?
* **Analytical Logic:** Does the model clearly highlight the trade-offs between each strategy?

---

## 7. AI Prompt Library

> **Prompt 1: Baseline Calculation**
> "Using the inputs FC_AMT = 20,000,000 EUR, S0 = 1.0831, F0 = 1.0935, R_USD = 5%, R_FC = 4%, and T = 360 days, calculate USD proceeds for forward and money market hedges and verify parity."

> **Prompt 2: Sensitivity & Visualization**
> "Build a sensitivity table showing USD proceeds for forward, money market, and option hedges across a ±5% range of exchange rates and generate a comparison chart."
