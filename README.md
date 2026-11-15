# Covenant Headroom & Debt Compliance Monitor

> **Excel financial modelling portfolio project · Private credit / leveraged finance / credit risk**

A five-year, scenario-driven monitor for a **fictional €100 million senior secured term loan**, built to demonstrate the mechanics of testing financial covenants and forecasting headroom ahead of a potential breach.

**All inputs, covenant terms and borrower data are synthetic and illustrative.** This is not a legal interpretation of a real credit agreement.

## Model highlights

- **2027–2031 forecast:** single-tranche debt schedule, scheduled amortisation, estimated interest expense, EBITDA, cash taxes, maintenance capex and liquidity.
- **Base / Downside switch:** one dropdown updates EBITDA, cash flow, ratios, headroom and alerts.
- **Three maintenance-style covenant tests:** maximum net leverage, minimum cash interest coverage and minimum fixed charge coverage (FCCR).
- **Automatic exception reporting:** PASS / BREACH flags, headroom by year, first breach year and first breach type.

## Files

| File | Use |
| --- | --- |
| [Completed model](models/Covenant_Headroom_Completed_Answer.xlsx) | Working model, formulas, scenario switch and charts |

Open the workbook in **Microsoft Excel**. Select **Enable Editing** if prompted, and allow Excel to recalculate formulas. GitHub cannot render Excel dashboards or run their data validation controls in its web file viewer; download the XLSX file to use it.

## Workbook guide

| Worksheet | Description |
| --- | --- |
| `00_README` | Assumptions, definitions, model conventions and limitations |
| `01_inputs` | Synthetic loan terms, annual covenant limits and EBITDA scenario growth |
| `02_Debt_Schedule` | Opening / closing debt, amortisation, cash interest and debt audit |
| `03_Financial` | Scenario-selected EBITDA, cash flow available for debt service and cash balances |
| `04_Covenants` | Covenant ratios, contractual limits, headroom and breach flags |
| `05_Dashboard` | Scenario selector, compliance summary, first-breach alert and charts |

## How to use

1. Open [the completed model](models/Covenant_Headroom_Completed_Answer.xlsx).
2. On `05_Dashboard`, change the scenario dropdown in **B5** between **Base** and **Downside**.
3. Inspect the year-by-year headroom, PASS / BREACH indicators, first-breach year and charts.
4. Adjust the **blue input assumptions** in `01_inputs` to explore pricing, amortisation, covenant step-downs and operating performance.
5. Confirm the debt schedule checks, liquidity flag and overall covenant results behave as expected.

## Covenant definitions used in this example

| Test | Illustrative calculation | Pass condition | Headroom |
| --- | --- | --- | --- |
| Net leverage | Net debt / selected EBITDA, with the model's cash-flooring convention | Actual ≤ maximum | Maximum − actual |
| Cash interest coverage | Selected EBITDA / annual cash interest | Actual ≥ minimum | Actual − minimum |
| FCCR | (EBITDA − estimated cash taxes − maintenance capex − working-capital outflow) / (cash interest + scheduled principal) | Actual ≥ minimum | Actual − minimum |

The facility begins at **€100m**, charges a fixed **8%** annual rate (applied to average annual outstanding debt), and repays **€5m** of principal each year. Covenant limits step down / step up according to the assumptions sheet.

### Illustrative scenario-check outcomes

| Scenario | Expected result |
| --- | --- |
| **Base** | All five forecast years compliant |
| **Downside** | First covenant breach in **2028 (FCCR)**; net leverage also breaches in **2031** |

The completed workbook opens in the **Downside** scenario. These are model outputs, not statements about a real borrower or loan.

## Model limitations

This is an **annual, single-facility educational model**, not a complete debt-documentation or three-statement model. It deliberately omits quarterly/LTM testing, EBITDA adjustments or add-backs, borrower-group definitions, netting caps, restricted cash, revolvers, mandatory prepayments, cure rights, waivers, floating-rate debt, covenant holidays and lender-specific drafting. Cash taxes and debt interest timing are simplified. The **cash floor is a separate liquidity warning** and not a maintenance covenant.

For credit underwriting or actual monitoring, the precise signed credit agreement controls the calculations.

## Excel techniques demonstrated

`IF` · `AND` · `COUNTIF` · `INDEX/MATCH` · relative / absolute references · scenario dropdown / data validation · dynamic dashboards · line charts · conditional formatting · audit checks.

---
**Portfolio case study:** fictional borrower, synthetic financials, created for learning and demonstration.