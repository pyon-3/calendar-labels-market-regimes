# Limitations

This project is a public research note, not a full academic replication package.

## Data Limits

- `Synthetic_NikkeiVI` is not the official Nikkei Stock Average Volatility Index.
- J-Quants Nikkei 225 VI futures data requires a subscription that includes derivatives futures.
- Yahoo Finance adjusted prices may differ from official total-return series.
- Sector and theme baskets are representative proxies, not official TOPIX sector total-return indices.
- Representative stock baskets can have survivorship bias.
- Public outputs omit raw price caches and vendor-specific data.

## Model Limits

- Regime conditioning is descriptive, not causal.
- Volatility, yen weakness, semiconductor cycles, and foreign flows are not independent in recent regimes.
- Transaction costs, taxes, slippage, and borrow constraints are not included in the public tables.
- Cross-sectional momentum should ideally be rebuilt with historical TOPIX500 or Nikkei225 constituents.

## Publication Rule

Public repository contents should include only:

- notes
- sanitized methodology
- derived figures
- aggregated tables

Do not publish:

- API keys
- `.env`
- raw J-Quants data
- raw full price caches
- files containing credentials or local private paths
