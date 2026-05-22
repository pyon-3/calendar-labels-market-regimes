# Calendar Labels and Market Instability Regimes

**A case study of Mercury retrograde as a market-anomaly label**

Author: pyon  
Independent market researcher  
Volatility and regime analysis  
X: @pyon

---

This is not an astrological trading strategy.  
The purpose of this note is to examine how a popular calendar label can be decomposed into market instability regimes.

## 日本語概要

本リポジトリは、水星逆行というカレンダーラベルが株式市場のストレス局面と関係するかを検証する研究ノートです。

本稿は、水星逆行を占星術的な売買シグナルとして肯定するものではありません。  
目的は、水星逆行というカレンダーラベルが、市場不安定レジームとどの程度重なっているのかを検証することです。

主な結果は、水星逆行単独の予測力は弱く、クラッシュリスクの説明力は市場不安定レジーム指標の方が高い、というものです。

## Overview

This repository contains version 0.1 of a research note on calendar labels and market instability regimes. Mercury retrograde is treated as a calendar label, then compared against market-state indicators built from volatility, rates, currency, and realized-volatility variables.

The core question is whether a popular narrative label has independent predictive power, or whether its apparent relevance can be decomposed into observable market instability regimes.

## Main Findings

- Mercury retrograde alone has weak classification power.
- Market-regime variables such as VIX, MOVE, rates, dollar variables, realized volatility, MID, UMID, and ShockSimilarity explain crash risk more effectively.
- Crash and VIX-spike rates during Mercury retrograde were somewhat elevated relative to randomized calendar windows.
- The conditional pattern for Mercury retrograde combined with high UMID is notable, but it is not stable enough to be treated as a standalone trading signal.

## Key Results

| Model | AUC |
|---|---:|
| Calendar only | 0.531 |
| Regime only | 0.696 |
| Calendar + regime | 0.699 |
| Full interactions | 0.700 |

Mercury retrograde alone provides only weak predictive power.  
Adding market regime variables substantially improves classification performance, while adding the calendar label to the regime model provides only a marginal improvement.

Source: `results/auc_comparison.csv`

## Conditional Crash Rates

| Condition | Crash rate |
|---|---:|
| Mercury retrograde | 21.7% |
| Non-Mercury | 16.0% |
| High UMID | 24.2% |
| Low UMID | 14.7% |
| Mercury × High UMID | 32.6% |
| Mercury × Low UMID | 18.3% |

The elevated crash rate for Mercury × High UMID is an interesting conditional pattern, but the interaction terms in the logistic model were not statistically stable. Therefore, it should not be interpreted as a standalone trading signal.

水星逆行 × 高UMID のクラッシュ率は興味深い条件付きパターンですが、ロジスティック回帰の交互作用項は安定して有意とは言えませんでした。そのため、単独の売買シグナルとして解釈すべきではありません。

Source: `results/conditional_probabilities.csv`

## Repository Structure

```text
README.md
paper/
  calendar_labels_market_instability_regimes_v0_1.md
results/
  auc_comparison.csv
  conditional_probabilities.csv
  random_calendar_percentiles.csv
  logistic_coefficients.csv
  walkforward_auc.csv
  multiple_testing_summary.csv
  daily_variance_tail_tests.csv
  post_volatility_summary.csv
  post_volatility_event_tests.csv
  max_drawdown_window_comparison.csv
figures/
  README.md
  umid_signed_v0_1_may2026.png
LICENSE
CITATION.cff
.gitignore
```

## Notes on Interpretation

The results should be interpreted as evidence about calendar labels and market narratives, not as evidence for astrology. The analysis separates statistical significance, economic relevance, and out-of-sample stability.

The main conclusion is that Mercury retrograde is not a robust standalone trading signal. Its apparent relationship with market stress is better interpreted through the lens of market instability regimes.

## Citation

If you use or discuss this work, please cite this repository:

```text
pyon. (2026). Calendar Labels and Market Instability Regimes: A Case Study of Mercury Retrograde. Version 0.1.
```

See `CITATION.cff` for machine-readable citation metadata.

## License

Text, figures, and processed results are released under CC BY-NC 4.0.

If code is released in a future version, it may be licensed separately under the MIT License.
