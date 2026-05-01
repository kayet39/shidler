# Recommendation Memo: FX Hedging Strategy & Model Framework

**To:** Chief Financial Officer (CFO)  
**From:** Kaye Talioaga  
**Date:** May 2026  
**Subject:** Recommended FX Hedging Strategy and Model Reproducibility Framework    

---

## A. Exposure Summary

The company is expecting to receive **€20,000,000 in 360 days**, which exposes it to foreign exchange (FX) risk. Since the receivable is denominated in euros but financial reporting is in USD, the final dollar value depends on the EUR/USD exchange rate at settlement.

If the euro depreciates, the company will receive fewer USD, negatively impacting cash flow. If the euro appreciates, the company benefits from higher USD proceeds. This uncertainty creates risk for budgeting, forecasting, and financial planning, making hedging strategies necessary to stabilize outcomes.

---

## B. Summary of Hedge Outcomes

### Forward Hedge
- Locked-in USD proceeds: **~$21.87M**
- Provides full certainty with no variability
- Eliminates FX risk entirely
- Trade-off: No upside if EUR appreciates

---

### Money Market Hedge
- USD proceeds: **~$21.87M (nearly identical to forward)**
- Replicates forward hedge using borrowing and investing
- Confirms interest rate parity
- Trade-off: More complex and requires liquidity

---

### Put Option Hedge
- Worst-case: **~$21.40M**
- Best-case: **~$22.35M**
- Provides downside protection with upside potential
- Premium cost: **$380,000**

---

### No Hedge
- USD proceeds fluctuate based on exchange rate
- Highest risk exposure
- No protection against unfavorable movements

---

## C. Sensitivity Interpretation

### EUR Depreciation Scenario
- Forward and Money Market hedges perform best due to fixed outcomes
- Option hedge provides protection but is reduced by premium cost
- No hedge performs worst due to full exposure

---

### EUR Appreciation Scenario
- Forward and Money Market hedges do not benefit from favorable movements
- Option hedge captures upside beyond strike price
- No hedge benefits fully but carries risk

---

### Key Insight
- Forward/MM = Certainty  
- Option = Flexibility  
- No Hedge = Risk  

---

## D. Strategic Recommendation

The recommended strategy is the **Forward Hedge**.

This approach is preferred because it guarantees approximately **$21.87M**, eliminates FX risk, and does not require an upfront premium. While the option hedge allows for upside potential, the cost of the premium reduces guaranteed proceeds and introduces unnecessary expense if the company prioritizes stability.

---

## E. Executive Justification

From a management perspective, the forward hedge is the strongest option because it provides:

- **Cash Flow Stability:** Predictable USD inflows  
- **Budget Certainty:** Eliminates FX volatility in forecasts  
- **No Premium Cost:** Unlike options, no upfront payment  
- **Simplicity:** Easy to implement and communicate  
- **Full Risk Elimination:** Removes downside exposure entirely  

Overall, the forward hedge aligns best with a company focused on financial stability and predictable performance.

---

## F. Structured AI Prompt

### # GOAL
Create an Excel-based FX hedging model that evaluates Forward, Money Market, and Option hedging strategies for a foreign currency receivable.

---

### # INPUT VARIABLES (USE NAMED RANGES)

- FC_AMT = 20,000,000  
- S0_in = 1.0831  
- F0_in = 1.0935  
- R_USD = 5.00%  
- R_FC = 4.00%  
- K_PUT = 1.09  
- PREM_PUT = 0.019  
- T_DAYS = 360  

---

### # SPREADSHEET STRUCTURE

Sections:
1. Inputs (Yellow cells)  
2. Assumptions (Blue cells)  
3. Calculations (Green cells)  
4. Outputs (Gray cells)  

---

### # MODEL LOGIC

#### Forward Hedge
USD_Forward = FC_AMT * F0_in  

---

#### Money Market Hedge

Step 1:  
PV_EUR = FC_AMT / (1 + R_FC * (T_DAYS/360))  

Step 2:  
USD_Converted = PV_EUR * S0_in  

Step 3:  
USD_Final = USD_Converted * (1 + R_USD * (T_DAYS/360))  

---

#### Put Option Hedge

Premium = FC_AMT * PREM_PUT  

USD_Option = MAX(K_PUT, S_T) * FC_AMT - Premium  

---

#### No Hedge

USD_Unhedged = FC_AMT * S_T  

---

### # SENSITIVITY TABLE

- Vary S_T from 0.95 × S0_in to 1.05 × S0_in  
- Use 1% increments  
- Calculate outcomes for:
  - Forward (constant)  
  - Money Market (constant)  
  - Option (variable)  
  - No Hedge (variable)  

---

### # VERIFICATION

- Confirm Forward ≈ Money Market (interest rate parity)  
- Ensure formula consistency  
- Validate option premium deduction  

---

### # OUTPUTS

- Summary table of USD proceeds  
- Sensitivity table  
- Comparison chart:
  - X-axis: Exchange rate  
  - Y-axis: USD proceeds  
  - Lines for each strategy  

---

### # EXPORT

- Excel workbook  
- Clearly labeled sections  
- Named ranges applied  
- All formulas visible  

---

## Extra Credit – Areas for Further Study & Improvement

### AI Skills & Automation

AI tools could automate both data input and analysis by pulling live exchange rate data and updating the model in real time. This would make the model more relevant for real-world decision-making instead of relying on static assumptions.

Additionally, AI could run Monte Carlo simulations to generate thousands of exchange rate scenarios, providing deeper insight into risk beyond a simple ±5% sensitivity analysis. This would help quantify probabilities and improve decision-making.

---

### Multi-File Reasoning

This project includes multiple components: the specification, the Excel model, and the structured prompt. AI can connect all of these to ensure consistency across files.

For example, AI could verify whether the Excel model follows the specification correctly or regenerate the entire model using the structured prompt. This improves reliability and reduces the risk of errors.

---

### GitHub & Version Control

Using GitHub allows for better organization, transparency, and reproducibility. Each stage of the project is tracked, making it easy to see changes over time and revert to previous versions if needed.

This is especially important in finance, where models are frequently updated and require auditability. GitHub also supports collaboration, allowing multiple users to work on the same project while maintaining structure and control.

---
