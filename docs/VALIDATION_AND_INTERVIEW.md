# Model checks and interview discussion

## Validation procedure

Open `models/Covenant_Headroom_Completed_Answer.xlsx` in Excel, then:

1. Select **Base** in `05_Dashboard!B5`. Confirm all five forecast years show **COMPLIANT**.
2. Select **Downside**. Confirm **2028** is flagged as the first covenant breach, caused by **FCCR**.
3. In the Downside scenario, confirm the **2031 net leverage covenant breaches** under the stricter 2.50x limit.
4. Confirm each annual principal payment is **€5m**, and ending principal balances progress **€95m → €90m → €85m → €80m → €75m**.
5. Confirm annual cash interest starts at **€7.8m** in 2027 (average outstanding loan €97.5m at 8%).
6. Check that `02_Debt_Schedule` debt audits read **OK**, and negative headroom is displayed as a warning.
7. Adjust one synthetic assumption, recheck all linked ratios, and restore it before saving the portfolio version.

## What the model does NOT prove

A model result marked PASS is **not a lender certification**. Signed documentation may use adjusted EBITDA, a restricted group, net debt cash caps, quarterly LTM periods, permitted add-backs, threshold baskets or cure provisions.

## Suggested interview questions

- Why is leverage headroom computed as **maximum allowed minus actual**, while coverage headroom is **actual minus minimum required**?
- Can a borrower breach if principal is being repaid? Yes: covenant limits can tighten faster than leverage improves.
- Why might the covenant ratio differ from a simple debt/EBITDA calculation? Loan documentation defines the metric and permitted adjustments.
- What happens if cash falls below the minimum cash floor? The workbook reports a **liquidity warning**, distinct from the three covenant tests.
- What would you add for a live credit-monitoring application? Quarterly LTM tests, debt agreement definitions, restricted cash/netting caps, cure rights, drawdowns and an actuals import.
