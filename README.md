# Market Regime Research Notes

Author: pyon  
X: @pyon

This repository collects public research-note style market regime studies. The common theme is to separate narrative labels from observable market-state variables such as volatility, trend, rates, currency, sector rotation, and investor flows.

This repository is for research and discussion. It is not investment advice.

## Research Notes

### 1. Calendar Labels and Market Instability Regimes

Location: `research/calendar-labels-market-regimes/`

A case study of Mercury retrograde as a calendar label. The note tests whether the label has independent predictive power, or whether its apparent relationship with market stress is better explained by observable regime variables.

### 2. Conditional Momentum in Japanese Equities

Location: `research/japan-momentum-regime/`

A research note on the Japanese equity momentum exception. The project separates time-series momentum, broad cross-sectional momentum, theme/sector proxy momentum, and volatility-regime conditioning.

Core interpretation:

> Japanese equities are not a market where momentum is absent. They are better understood as a conditional momentum market where trend, volatility, policy reform, currency, semiconductor cycles, and foreign flows determine whether momentum becomes observable.

## Public Data Policy

Only publishable artifacts are included here:

- research notes
- methodology notes
- limitation notes
- aggregated CSV tables
- derived figures
- sanitized scripts or script notes

Do not commit:

- API keys
- `.env`
- raw J-Quants caches
- raw vendor data
- full price caches
- personal credentials
- notebooks containing local paths or tokens

## Repository Structure

```text
research/
  calendar-labels-market-regimes/
    README.md
    paper/
    results/
    figures/
  japan-momentum-regime/
    README.md
    docs/
    outputs/
      figures/
      tables/
    scripts/
data/
  sample/
```

## License

Text, figures, and processed results are released under CC BY-NC 4.0 unless otherwise noted.

Code, when provided, may be licensed separately under the MIT License.
