# Methodology

## Research Question

Has Japan remained an exception where momentum is weak, or has the market shifted into a regime where momentum appears under specific conditions?

## Momentum Definitions

### Time-Series Momentum

For each market index:

- compute monthly prices
- compute prior 3-, 6-, and 12-month returns
- optionally skip the most recent month
- go long next month when the prior return is positive
- otherwise hold cash

The public tables focus on comparable period-level results.

### Cross-Sectional Momentum

The formal benchmark is Fama-French Japan WML.

The public sector/theme sections use representative stock baskets as proxies. These are used for historical regime interpretation and should be treated as supplementary evidence.

## Volatility Regime Proxy

`Synthetic_NikkeiVI` is computed from Nikkei 225 daily returns:

- 20-trading-day annualized realized volatility
- 60-trading-day annualized realized volatility
- weighted proxy: `0.7 * RV20 + 0.3 * RV60`

When Nikkei 225 VI futures are available through J-Quants, `NikkeiVI_Futures` can be used for the post-2012 portion. In the public outputs here, the derivative futures endpoint was not available under the current subscription, so the long-run chart uses the synthetic proxy.

## Historical Windows

The note highlights:

- 1987 global crash
- 1989/1990 Japan bubble peak
- 2000 IT bubble unwind
- 2005/2006 postal reform market
- 2007 global financial crisis and post-GFC recovery
- 2023 onward TSE reform, yen weakness, AI, and semiconductor regime

## Public Artifacts

This repository intentionally contains only derived figures, aggregated CSV tables, and notes. Raw API caches and credentials are excluded.
