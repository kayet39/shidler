# Executive Memo: FX Exposure Management Strategy

**To:** Chief Financial Officer (CFO)   
**From:** Kaye Talioaga   
**Date:** April 9, 2026   
**Subject:** Managing Foreign Exchange Risk for EUR Receivable   

---

## 1. Executive Summary
This memo outlines our firm's exposure to foreign exchange (FX) risk regarding an upcoming receivable of €20,000,000 from our aerospace contract, due in 12 months. Without a hedging strategy, our USD proceeds are vulnerable to market fluctuations. This memo recommends evaluating specific hedging families to protect our profit margins against a weakening Euro.

## 2. Exposure Analysis
Our firm, U.S. Aerospace Manufacturer, is currently expecting a cash inflow of **€20,000,000 (EUR)**.

* **Maturity Date:** April 2027 (12 Months)
* **Risk Profile:** As the USD strengthens against the EUR, the value of our receivable decreases. At the current forward rate of 1.0935, this is worth $21,870,000. However, a 5% adverse move (depreciation of the EUR) would result in a loss of approximately **$1,093,500** in USD value.

## 3. Hedging Strategies (The Three Families)
To mitigate this risk, we are analyzing three primary "hedge families":

* **Forward Market Hedge:** Locking in the guaranteed exchange rate of 1.0935 today for the future date.
    * *Pros:* Zero upfront cost; eliminates all uncertainty for the $21.87M proceeds.
    * *Cons:* No upside potential if the Euro unexpectedly strengthens.

* **Money Market Hedge:** Borrowing EUR now at the **[EUR Interest Rate]**, converting to USD at the spot rate, and investing in the U.S. at the **[USD Interest Rate]** to "create" a synthetic forward.
    * *Pros:* Locks in a rate based on interest rate differentials.
    * *Cons:* Uses up our corporate credit lines and appears on the balance sheet.

* **Options Market Hedge:** Purchasing a Put Option on the EUR with a strike price of **[k]** and a premium of $0.019 per contract.
    * *Pros:* Provides a "floor" to protect against the downside while allowing us to benefit if the Euro gains value.
    * *Cons:* Requires an upfront "premium" cost of $380,000 (0.019 * 20M) regardless of the outcome.

## 4. Next Steps
In Stage 2, I will build a comprehensive Excel model to calculate the exact net proceeds for each of these three strategies using our specific 12-month rates. Following that, Stage 3 will involve creating a technical specification to automate this analysis, culminating in a final recommendation in Stage 4.

---
