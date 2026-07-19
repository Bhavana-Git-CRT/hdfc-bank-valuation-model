# HDFC Bank Valuation Model — Trading Comps & Dividend Discount Model

A two-part equity valuation of **HDFC Bank** (NSE: HDFCBANK), built as a portfolio project to demonstrate financial modeling and sector-specific valuation judgment for banking/finance recruiting.

## Why this project

Most student valuation models apply a standard DCF to any company. Banks don't work that way — leverage is core to their business model, not a financing choice, so a normal free-cash-flow DCF breaks down. This project instead uses the two methods banking analysts actually use:

1. **Trading Comparables** — HDFC Bank benchmarked against ICICI Bank, Axis Bank, Kotak Mahindra Bank, and SBI on P/E, P/B, and ROE
2. **Dividend Discount Model (DDM)** — a two-stage DDM with a CAPM-derived cost of equity, plus a sensitivity table

## Key finding

The two methods disagree, and that disagreement is the interesting part:

- **Comps** suggest HDFC Bank is trading close to fair value (implied range ~₹740–₹829 vs. a market price of ₹799)
- **DDM** implies HDFC is significantly overvalued (~₹243 fair value) — and this holds across a full range of cost-of-equity and terminal-growth assumptions, not just the base case

This isn't a modeling error. It's a known limitation of DDM for **low dividend-payout, high-ROE banks**: HDFC pays out only ~31% of earnings and retains the rest to compound book value at a ~14% ROE. A plain DDM only values the cash actually paid out to shareholders, so it systematically understates the value created by reinvested earnings. This is exactly why analysts pair DDM with comps (or a residual-income / warranted P/B approach) rather than relying on it alone for financials.

## Structure

| Tab | Contents |
|---|---|
| `Comps` | Peer set financials (price, market cap, EPS, P/E, book value/share, P/B, ROE), peer average/median multiples, and implied valuation for HDFC Bank |
| `DDM` | CAPM cost of equity, two-stage dividend projection, terminal value, intrinsic value per share, and a 5×5 sensitivity table (cost of equity × terminal growth) |
| `Summary` | Chart comparing implied value per share across all methodologies vs. current market price |

## Methodology notes

- **Cost of equity (CAPM):** Ke = Risk-free rate + Beta × Equity Risk Premium
- **High-growth phase (Years 1–5):** dividend growth = ROE × (1 − Payout Ratio)
- **Terminal value:** Gordon Growth model applied to Year-6 dividend
- All financial inputs (price, market cap, EPS, book value, ROE) are sourced from [Screener.in](https://www.screener.in), consolidated financials, accessed 15-Jul-2026
- CAPM inputs (risk-free rate, equity risk premium, beta) are editable assumptions — highlighted in yellow in the workbook — since these are analyst judgment calls, not hard data

## How to use

1. Download `HDFC_Bank_Valuation_Model.xlsx`
2. Blue cells = hardcoded inputs (sourced data). Yellow cells = editable assumptions. Black cells = formulas — don't overwrite these.
3. Update the blue cells with current market data to refresh the model, or adjust the yellow assumption cells to run your own scenarios
4. The sensitivity table on the `DDM` tab updates automatically if you change the cost-of-equity or growth assumption cells it's linked to

## Limitations

- This is a simplified two-stage DDM, not a full residual-income or embedded-value model
- CAPM inputs (beta, ERP, risk-free rate) are approximations — verify against a live source before relying on this for investment decisions
- Comps use trailing multiples only; no forward estimates were incorporated

## Disclaimer

Built for educational/portfolio purposes only. Not investment advice.
