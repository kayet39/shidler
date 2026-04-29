FX Hedging Model Specification

Created by: Kaye Talioaga
Updated by: Kaye Talioaga
Date Created: April 2026
Date Updated: April 2026
Version: 1.0

1. Problem Statement (Objective)

The company is exposed to foreign exchange risk due to a €20,000,000 receivable that will be settled in 360 days. Because exchange rates fluctuate, the USD value of this receivable is uncertain and could decrease if the euro depreciates against the U.S. dollar.

The objective of this model is to evaluate and compare three hedging strategies—forward hedge, money market hedge, and option hedge—to determine which provides the most stable and favorable USD outcome. This model supports decision-making by quantifying risk exposure and identifying trade-offs between certainty, cost, and upside potential.

2. Scope
In-scope:
Single foreign-currency receivable exposure (EUR)
Forward hedge, money market hedge, and option hedge calculations
Sensitivity analysis of exchange rate movements (±5%)
Comparison of USD proceeds across hedging strategies
Out-of-scope:
Multi-currency portfolios
Dynamic hedging strategies
Credit and counterparty risk
Accounting treatment (hedge accounting)
Transaction costs beyond stated assumptions
3. Inputs (Known Variables)
Named Range	Description	Unit	Value
FC_AMT	Foreign-currency receivable	EUR	20,000,000
S0_in	Spot rate at inception	USD per EUR	1.0831
F0_in	Forward rate (1-year)	USD per EUR	1.0935
R_USD	USD interest rate	Annual %	5.00%
R_FC	Euro interest rate	Annual %	4.00%
K_PUT	Put option strike	USD per EUR	1.09
PREM_PUT	Put premium	USD per EUR	0.019
T_DAYS	Time to settlement	Days	360

Data Source: Model assumptions and provided case inputs

4. Assumptions & Constraints
Interest rates use ACT/360 convention
No transaction costs included
Interest rate parity holds between forward and money market hedges
Options are European-style (exercise at maturity only)
Markets are liquid with borrowing/lending at stated rates
No taxes or fees included
5. Calculation Flow (Workflow / Steps)
Step 1: Define Exposure
€20,000,000 receivable in 360 days
Current spot rate = 1.0831 USD/EUR
Step 2: Forward Hedge
Lock in forward rate: 1.0935 USD/EUR
USD proceeds:
€20,000,000 × 1.0935 = $21,870,000
Outcome: Fully locked, no risk
Step 3: Money Market Hedge
Discount EUR receivable:
€20,000,000 ÷ (1 + 0.04 × 360/360)
Convert to USD at spot rate (1.0831)
Invest USD at 5% for 1 year
Final USD proceeds:
$21,870,288
Outcome: Nearly identical to forward hedge (parity confirmed)
Step 4: Option Hedge (Put Option)
Strike price = 1.09
Premium = 0.019 × €20,000,000 = $380,000

Outcomes:

Worst-case (exercise put):
$21,401,000
Best-case (favorable spot):
$22,347,000
Outcome:
Downside protection + upside potential
But comes at a cost (premium)
Step 5: Sensitivity Analysis
Exchange rate range:
0.95 × 1.0831 → 1.05 × 1.0831
Increment: 1% steps
Recalculate USD proceeds for all strategies
Compare performance across scenarios
6. Outputs (Expected Deliverables)
Summary Results:
Forward Hedge: $21,870,000
Money Market Hedge: $21,870,288
Option Hedge (at S₀): $21,401,000
Sensitivity Table:
USD outcomes across exchange rate scenarios
Comparison Chart:
Line graph showing strategy performance
Insights:
Forward = most stable
Money Market = nearly identical
Option = flexible but costly
7. Model Review — What Worked & What to Improve
What Worked:
Forward and money market hedge results aligned (parity holds)
Sensitivity analysis clearly shows exposure to FX risk
Model structure allows easy comparison across strategies
What to Improve:
Add error checks for invalid inputs
Improve naming consistency across all sections
Include transaction costs for realism
Expand sensitivity range beyond ±5%
Add dashboard-style visuals for decision-making
8. Sensitivity Plan
Range: ±5% around current spot rate (1.0831)
Increment: 1%
Purpose: evaluate how USD proceeds change under different FX scenarios

Key Insight:

Forward & Money Market = stable, predictable
Option = better in strong EUR scenarios, worse in weak EUR scenarios
9. Limitations & Next Steps
Limitations:
Assumes constant interest rates
Ignores transaction costs and liquidity constraints
Does not incorporate credit risk
Static (not real-time) model
Next Steps:
Use this specification to build an AI-enhanced model (Stage 4)
Automate sensitivity analysis and outputs
Improve flexibility and scalability
10. Evaluation Criteria
Clarity: Easy to understand and well-structured
Accuracy: Financial logic and calculations are correct
Reproducibility: Model can be rebuilt from this spec
Analytical Logic: Clear comparison of hedging strategies
11. AI Prompts (Examples)
Prompt 1:
“Using the inputs FC_AMT = 20,000,000 EUR, S0 = 1.0831, F0 = 1.0935, R_USD = 5%, R_FC = 4%, and T = 360 days, calculate USD proceeds for forward and money market hedges and verify parity.”
Prompt 2:
“Build a sensitivity table showing USD proceeds for forward, money market, and option hedges across a ±5% range of exchange rates and generate a comparison chart.”
