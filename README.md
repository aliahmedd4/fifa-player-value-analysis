# FIFA Player Value Analysis

Exploratory data analysis and preprocessing pipeline for the FIFA Player Performance and Market Value dataset, building toward ML-based market value classification.

## Problem Statement

This project explores, cleans, and prepares the **FIFA Player Performance and Market Value** dataset for future machine learning tasks — specifically predicting and categorizing player market value into three tiers (**Low / Medium / High**) based on a player's performance metrics, club affiliation, and biographical attributes.

## Dataset

**Source:** Kaggle — [FIFA Player Performance and Market Value Analytics](https://www.kaggle.com/datasets/jayjoshi37/fifa-player-performance-and-market-value-analytics)

> The dataset is **not included** in this repository (excluded via `.gitignore`). Download it from Kaggle and place it in the project root before running the notebook.

## Approach

The notebook implements a full EDA and preprocessing pipeline:

| Step | Details |
|------|---------|
| **Data Exploration** | Summary statistics, missing value audit, distribution checks |
| **Encoding** | Binary encoding, ordinal encoding, one-hot encoding for categorical features |
| **Normalization** | StandardScaler applied to continuous features |
| **Binning** | Equal-width binning to discretize the market value target into Low / Medium / High |
| **Feature Engineering** | Derived features such as `goals_per_90` |
| **Feature Selection** | Pearson correlation analysis for numeric features; chi-square testing for categorical features |
| **Sampling** | Stratified sampling to address class imbalance |
| **Visualizations** | Histograms, boxplots, scatterplots, and a full correlation heatmap |

## Key Insights

- **Position has no significant effect on market value** — one-way ANOVA found no statistically significant difference in market value across player positions (p > 0.05).
- **Interaction effect detected** — `injury_prone` and `transfer_risk_level` together have a meaningful interaction effect on market value, beyond either variable alone.
- **Counter-intuitive finding** — 255 players rated **85+ overall** fall into the **Low Value** category, suggesting overall rating alone is not a reliable proxy for market value.
- **Scouting recommendation** — Target players aged **22–26** from lower-value clubs who combine a high `overall_rating` with a low `transfer_risk` score for maximum value acquisition.

## Running Locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/aliahmedd4/fifa-player-value-analysis.git
   cd fifa-player-value-analysis
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Download the dataset**
   - Go to the [Kaggle dataset page](https://www.kaggle.com/datasets/jayjoshi37/fifa-player-performance-and-market-value-analytics)
   - Download `fifa_player_performance_market_value.csv`
   - Place it in the project root (same folder as the notebook)

4. **Launch the notebook**
   ```bash
   jupyter notebook fifa_value_analysis.ipynb
   ```

## Project Structure

```
fifa-player-value-analysis/
├── fifa_value_analysis.ipynb  # Main analysis notebook
├── requirements.txt      # Python dependencies
├── README.md
└── .gitignore
```

## Contributors

- **Ali Sherif**
- **Ahmed Rashad**
- **Asser Ehab**
- **Ali Ahmed**
