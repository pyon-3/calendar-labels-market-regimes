# Conditional Momentum in Japanese Equities

Author: pyon  
X: @pyon

## Summary

This research note revisits the Japanese equity momentum exception.

The working hypothesis is that Japan is not a market where momentum is absent. Instead, momentum appears conditionally when trend, volatility, policy reform, currency, semiconductor cycles, and foreign investor flow line up.

## Main Takeaway

Japanese momentum should be separated into three layers:

- Broad cross-sectional momentum: historically weak in Japan.
- Time-series momentum: observable in Japanese indices, especially in recent regimes.
- Theme and sector momentum: strong when capital concentrates in policy, currency, semiconductor, AI, or balance-sheet repair themes.

## Key Public Figures

- `outputs/figures/long_term_synthetic_nikkeivi.png`
- `outputs/figures/post_it_bubble_sector_rotation_2002_2005.png`
- `outputs/figures/post_2007_sector_rotation_2007_2012.png`
- `outputs/figures/post_gfc_recovery_sector_rotation_2009_2012.png`

## Public Tables

- `outputs/tables/event_window_synthetic_vi.csv`
- `outputs/tables/tsmom_periods.csv`
- `outputs/tables/cross_section_periods.csv`
- `outputs/tables/regime_conditioning.csv`
- `outputs/tables/post_it_bubble_sector_rotation_2002_2005.csv`
- `outputs/tables/post_2007_sector_rotation.csv`

## Interpretation

The current Japanese equity regime looks less like a quiet low-volatility momentum market and more like a high-volatility upside momentum market. This distinction matters because high-volatility momentum can work while the upside trend persists, but it can reverse sharply when volatility remains elevated and 12-month momentum breaks.

## Important Limitations

`Synthetic_NikkeiVI` is a realized-volatility proxy constructed from Nikkei 225 returns. It is not the official Nikkei Stock Average Volatility Index.

Sector results are based on representative stock baskets where official long-run sector total-return series are not included. These are proxies and should not be read as formal TOPIX sector index results.

See:

- `docs/methodology.md`
- `docs/limitations.md`
- `docs/research_note_jp.md`
- `docs/qiita_article_draft.md`
