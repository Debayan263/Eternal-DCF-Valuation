# Eternal Ltd (Zomato) — DCF Valuation Model

A three-scenario, fully linked discounted cash flow model of **Eternal Limited** (NSE/BSE: ETERNAL | 543320), built in Excel.

- **Valuation date:** 24 September 2026
- **Units:** ₹ Crore unless stated
- **Method:** unlevered FCFF DCF, cross-checked with Gordon Growth and Exit Multiple terminal values
- **Scenarios:** Bear / Base / Bull, driven from a single Inputs sheet
- **File:** `Eternal_DCF_Final.xlsx`

## Workbook structure

| Sheet | What it does |
|---|---|
| Cover | Scope, author, navigation, formatting convention |
| Output | Scenario comparison, two sensitivity tables (WACC × terminal growth, WACC × exit multiple), charts, key takeaways |
| Inputs | Every hardcoded assumption (blue font): company data, WACC build, scenario drivers |
| Model | Linked schedules for each scenario: revenue, opex, PP&E and D&A, tax, working capital, FCFF, DCF |
| Sources | Source list and rationale for every assumption |

Blue font = editable input. Black font = formula. The sensitivity tables use closed-form `NPV()` formulas rather than Excel Data Tables, so they recalculate live with the rest of the model.

## Key assumptions

- **WACC ≈ 16.6%**, close to the cost of equity: risk-free rate 7.11%, India ERP 7.08%, beta 1.36, pre-tax cost of debt 8.5%. Eternal is close to net cash, so the debt weighting barely moves the number.
- **Base-case revenue** grows from ₹90,000 Cr (FY27E) to ~₹252,000 Cr (FY33E), a CAGR of about 24.5%, fading from Q1 FY27's pace toward 12% by the terminal year.
- **Base EBITDA margin** rises from 4.5% (FY27E) to 13% (FY33E), driven by four explicit cost levers: cost of goods, employee expense, delivery & logistics, and marketing/tech/other opex.
- **D&A** runs off a depreciable base of ₹7,074 Cr — net PP&E, CWIP, other intangibles, and right-of-use lease assets. This deliberately excludes ₹5,737 Cr of goodwill, which is not depreciated under Ind AS (it is tested for impairment instead) but is often bundled into "Fixed Assets" on data aggregators.
- **Terminal growth:** 4.5% / 5.0% / 5.5% (Bear/Base/Bull). **Exit EV/EBITDA:** 12x / 14x / 16x (Bear/Base/Bull).
- **Net cash of ₹11,764 Cr** (liquid investments and cash of ₹16,356 Cr less borrowings and lease liabilities of ₹4,592 Cr) is added to enterprise value to reach equity value.

## Results

| Implied price per share (₹) | Bear | Base | Bull |
|---|---|---|---|
| Gordon Growth | 61 | 95 | 131 |
| Exit Multiple | 109 | 206 | 320 |

Current market price: **₹335.50**.

## How to read the result

The model values the stock below the market price in every scenario except the Bull-case exit multiple, which comes close. That's worth understanding rather than dismissing:

- The two terminal-value methods disagree with each other. Gordon Growth implies roughly 5x FY33E EBITDA, while the assumed exit multiples imply roughly 11–13% perpetual growth. Both cross-checks are shown on the Output sheet (rows 48–49), so you can see exactly where the disagreement comes from.
- The Base-case valuation is terminal-value-heavy: the present value of the Gordon Growth terminal value is roughly 2.5x the present value of the explicit FY27E–FY33E cash flows.
- Read together, the market appears to be pricing in a growth and margin path at or above this model's Bull case, or a materially lower discount rate than the 16.6% used here.

## Known limitations

- **Timing:** FY27E is discounted as a full year and net cash is taken as of 31-Mar-2026, although the valuation date is 24-Sep-2026. There's no stub-period adjustment.
- **Terminal year:** FY33E reinvestment still reflects a higher growth rate than the 4.5–5.5% terminal growth it is capitalised at. This is a conservative simplification, not an error.
- **Beta:** 1.36 is a one-year observed beta with limited trading history. A peer-based or regression beta would be more defensible.
- **D&A vs FY26A:** the ₹7,074 Cr depreciable base produces lower FY27E D&A (~₹1,061 Cr Base case) than the FY26A actual of ₹1,597 Cr. This is plausible — FY26A D&A reflects the prior year's asset mix and any accelerated depreciation — but it hasn't been independently reconciled against the FY26 depreciation note, and is worth checking if a reader pushes on it.
- **Marketing opex** rises to 18.5% of revenue by FY33E in the Base case, which caps EBITDA margin at 13%. This assumption should be defensible on its own if questioned.
- **Data to verify:** all FY26 balance sheet and P&L figures, and the Q1 FY27 revenue figure of ₹20,211 Cr, are taken from public aggregators and should be cross-checked against Eternal's official filings before this model is relied on for any real decision.

## Disclaimer

This is an academic and interview-preparation project built on publicly available information about Eternal Ltd. Historical figures are sourced from public financial disclosures and market data aggregators; all forward-looking assumptions are the author's own estimates. This is not investment research, a price target, or a recommendation to buy or sell any security. Verify all figures against the company's official filings before relying on this model for any decision.

**Author:** Debayan Bandyopadhyay
