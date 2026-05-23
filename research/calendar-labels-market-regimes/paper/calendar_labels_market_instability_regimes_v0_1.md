# Calendar Labels and Market Instability Regimes:
## A Case Study of Mercury Retrograde

Author: pyon  
Independent market researcher  
Volatility and regime analysis  
Version: 0.1  
Date: May 2026

---

This is not an astrological trading strategy.  
The purpose of this note is to examine how a popular calendar label can be decomposed into market instability regimes.

本稿は、水星逆行を占星術的な売買シグナルとして肯定するものではありません。  
目的は、水星逆行というカレンダーラベルが、市場不安定レジームとどの程度重なっているのかを検証することです。

## Abstract

This research note reassesses Mercury retrograde as a market anomaly by treating it not as an astrological cause, but as a calendar label. We compare its apparent relationship with equity-market stress against market-state-based instability measures constructed from volatility, rates, currency, and realized-volatility variables.

The results show that Mercury retrograde alone has weak predictive content. However, crash rates and VIX spike frequencies during Mercury retrograde periods are somewhat elevated relative to randomized calendar windows. More importantly, market instability regime variables such as UMID and ShockSimilarity explain crash risk more effectively than the calendar label itself.

These findings suggest that Mercury retrograde is better understood as a narrative label that may coincide with unstable market regimes, rather than as a causal or standalone trading signal.

## 1. Introduction

Calendar anomalies are often discussed in markets because they provide simple stories for complex price behavior. Mercury retrograde is one such label. It is easy to remember, easy to narrate, and often invoked after periods of market stress.

This note asks whether that label contains independent information, or whether its apparent relevance is better explained by observable market instability. The analysis treats Mercury retrograde as a binary calendar indicator and compares it with market-regime variables built from volatility, rates, currency, realized volatility, and shock-template similarity.

## 2. Data

The analysis uses daily market data for equity, volatility, rates, and currency variables. The core state vector includes S&P 500 returns, Nikkei returns, VIX, MOVE, U.S. 10-year yield changes, dollar index changes, USDJPY changes, realized volatility, SKEW, and a correlation proxy.

Mercury retrograde windows are treated as calendar labels. They are not treated as causal variables.

The processed result files are stored in `results/`.

## 3. Methodology

### 3.1 Mercury Retrograde as a Calendar Label

Each trading day is assigned a binary label indicating whether it falls within a Mercury retrograde window. The label is used as a calendar variable, not as an astrological mechanism.

### 3.2 Market State Vectors

For each trading day, a market state vector is constructed from equity returns, volatility levels and changes, rates, currency moves, realized volatility, SKEW, and a correlation proxy.

The feature vector is standardized before distance-based analysis:

```text
Z_t = standardize(X_t)
```

The baseline distance measure is Euclidean distance in standardized feature space.

### 3.3 MID and UMID

Market Instability Density, or MID, measures how densely recent market states cluster in standardized feature space.

UMID, or Unstable Market Instability Density, restricts the density calculation to market states classified as unstable based on volatility, MOVE, realized volatility, or drawdown conditions.

Conceptually:

```text
MID_t  = close-pair density among recent market states
UMID_t = close-pair density among recent unstable market states
```

These metrics are designed to capture whether current market conditions resemble a dense unstable regime rather than a random isolated movement.

### 3.4 ShockSimilarity

ShockSimilarity compares each current market state with pre-shock templates. The template windows include periods before major volatility or policy shocks such as the 2018 VIX shock, the 2020 COVID shock, the 2022 rate and inflation shock, the 2024 Ueda shock, and the 2025 tariff shock.

The similarity score is based on nearest-neighbor distance to prior pre-shock states.

### 3.5 Random Calendar Test

To avoid over-interpreting one calendar label, the Mercury retrograde windows are compared against randomized calendars with the same approximate structure. The main comparison uses 10,000 randomized calendar samples.

The goal is to evaluate whether Mercury retrograde is unusual relative to arbitrary calendar cuts of similar length and frequency.

### 3.6 Logistic Regression and AUC

Crash risk is modeled using logistic regression. The dependent variable is a forward crash indicator based on future return and drawdown thresholds.

Model families include:

- Calendar only
- Regime only
- Calendar plus regime
- Full interactions

The analysis focuses on AUC, coefficient stability, and whether interaction terms remain statistically reliable.

## 4. Results

### 4.1 Simple Calendar Test

Mercury retrograde alone has weak predictive power. In the classification exercise, the calendar-only model produced an AUC of 0.531.

This is only slightly above random classification and is not strong enough to support a standalone trading rule.

### 4.2 Conditional Crash Rates

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

### 4.3 Random Calendar Comparison

Compared with 10,000 randomized calendar samples, Mercury retrograde periods ranked relatively high for crash rate and VIX-spike frequency:

| Metric | Mercury percentile vs random calendars |
|---|---:|
| Crash rate | 91.69 |
| VIX spike rate | 95.36 |
| UMID mean | 43.52 |
| ShockSimilarity mean | 38.82 |

This suggests that the calendar label coincided with somewhat elevated stress outcomes, but not with consistently higher instability-density or shock-similarity levels.

### 4.4 Regime Model vs Calendar Model

| Model | AUC |
|---|---:|
| Calendar only | 0.531 |
| Regime only | 0.696 |
| Calendar + regime | 0.699 |
| Full interactions | 0.700 |

The regime-only model substantially outperformed the calendar-only model. Adding the calendar label to the regime model produced only a marginal improvement.

### 4.5 Walk-Forward AUC

Walk-forward results were not stable across all time splits. Later periods showed stronger classification performance, while earlier folds were weaker. This reduces confidence that the model should be interpreted as a stable trading system.

## 5. Discussion

The results are consistent with the idea that calendar labels can become narratives attached to stressful market environments. Mercury retrograde periods showed somewhat elevated crash and VIX-spike frequencies relative to randomized calendars, but the explanatory power was much stronger for observable market-regime variables.

This distinction matters. A calendar label can appear meaningful if it overlaps with known unstable regimes, but that does not imply causal power. In practical terms, VIX, MOVE, rates, dollar variables, realized volatility, and market-state density should be given priority over the calendar label.

## 6. Conclusion

Mercury retrograde is not a robust standalone trading signal.  
Its apparent relationship with market stress is better interpreted through the lens of market instability regimes.

In other words, stars do not move markets. Rather, humans may attach meaning to calendar labels after market instability has already become visible.

水星逆行は、単独で使える堅牢な売買シグナルではありません。  
相場ストレスとの見かけ上の関係は、市場不安定レジームを通して解釈する方が妥当です。

星が相場を動かすのではなく、市場が不安定になったあとで、人間がカレンダーラベルに意味を貼っている可能性があります。

## Limitations

This is version 0.1 of the analysis. It should be interpreted as a research note rather than a production trading model.

Limitations include:

- dependence on available public market data,
- sensitivity to crash definitions,
- sensitivity to feature construction and threshold choices,
- instability of interaction terms,
- limited out-of-sample robustness,
- no transaction-cost-adjusted trading strategy.

## Disclaimer

This is not investment advice. It is not an astrological trading strategy. The purpose is to examine a calendar label as a market narrative and compare it with observable market instability regimes.
