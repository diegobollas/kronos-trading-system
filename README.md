# KRONOS — Algorithmic Trading System for EUR/USD

> *"Knowing when to trade is more valuable than knowing what to predict."*

KRONOS is a machine learning pipeline for generating trading signals on the EUR/USD forex pair. Built as a research project to explore the intersection of deep learning, NLP, and reinforcement learning applied to financial markets.

---

## Results

| System | Sharpe Ratio | Active Days | vs Benchmark |
|---|---|---|---|
| Buy & Hold | -0.142 | 100% | baseline |
| Naive Momentum | 0.382 | 100% | +0.382 |
| KRONOS v1.0 | 0.307 | 100% | -0.075 |
| **KRONOS v2.0** | **0.860** | **20%** | **+0.478** |

Key finding: KRONOS v2.0 achieves Sharpe 0.860 operating only 20% of the time.

---

## Alpha Validation

| Test | Result | Interpretation |
|---|---|---|
| Hurst Exponent (R/S) | H = 0.565 | Trending market — alpha exists |
| Perfect Foresight Sharpe | 17.36 (1-day) | Abundant alpha available |
| Permutation Test | p = 0.40 | Model needs real sentiment data |
| Annual Stability | 2/13 years positive | Regime filtering needed |

---

## Key Insight

KRONOS v1.0 predicted direction at 5-day horizon — Sharpe 0.307, below naive benchmark 0.382.

Two problems identified:
1. **Wrong horizon**: 20-day horizon has 80% naive accuracy vs 49% at 1-day
2. **Wrong regime**: model destroys returns in Quiet regimes

KRONOS v2.0: predicts at 20-day horizon, operates only in regime 1 or 2.

---

## Tech Stack

| Component | Technology |
|---|---|
| Price forecasting | PatchTST (neuralforecast) |
| Regime detection | GaussianHMM (hmmlearn) |
| Sentiment analysis | FinBERT (HuggingFace) |
| Signal fusion | XGBoost + SHAP |
| RL agent | PPO (stable-baselines3) |
| Data | yfinance, NewsAPI |
| Environment | Python 3.11, Jupyter |

---

## Roadmap

- [x] Phase 0-12: Complete
- [ ] Phase 13: Live paper trading
- [ ] Phase 14: Academic paper

---

## Author

Diego Bollas — Universidad del Valle de Mexico
GitHub: [@diegobollas](https://github.com/diegobollas)

*For educational and research purposes only. Not financial advice.*