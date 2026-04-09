# Goal-Scoring Prediction Model

A machine learning project that classifies whether **Tolu Arokodare** scored in a given Belgian Pro League match during the 2024/25 season, using match statistics and expected goals (xG).

## Key Findings

- **xG and Shots on Target** are the strongest predictors of goal-scoring
- Arokodare massively **overperformed his xG** (17 goals vs ~8 xG) — a sign of elite finishing
- A **pre-match only model** (venue + opponent quality) performs significantly worse, confirming that in-match stats drive the model
- Multiple models compared using cross-validation suited to the small sample size (30 games)

## Dataset

| Feature | Description |
|---------|-------------|
| Venue | Home or Away |
| Shots / Shots on Target | Attacking volume |
| xG | Expected Goals from chance quality |
| Key Passes | Chances created |
| Minutes | Playing time |
| Opp_GA_per_game | Opponent defensive quality |

30 matches from the 2024/25 Belgian Pro League season.

## Methodology

- **Binary classification:** Did Arokodare score (1) or not (0)?
- **5 models compared:** Logistic Regression, KNN, SVM, Random Forest, Gradient Boosting
- **Cross-validation:** Leave-One-Out CV and Repeated Stratified 5-Fold CV (no single train/test split on small data)
- **Feature engineering:** Shot Accuracy, xG per Shot
- **Honest evaluation:** Pre-match vs full-model comparison to address data leakage

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook stats.ipynb
```

## Results

| Model | Mean CV Accuracy |
|-------|-----------------|
| **Logistic Regression** | **87.7%** |
| Random Forest | 85.0% |
| SVM (RBF) | 84.0% |
| Gradient Boosting | 82.3% |
| KNN (k=5) | 80.3% |

- **Leave-One-Out CV accuracy (Logistic Regression): 90.0%** (27/30 correct predictions)
- Pre-match only model (venue + opponent quality): 56.7% — barely above random chance, showing in-match stats are essential
- Logistic Regression was the best performer with the lowest variance across folds

## Limitations

- 30-match sample from a single season and single player — results may not generalise
- Most features are in-match statistics, making this an explanatory model rather than a true pre-match predictor
- No temporal validation (e.g., using first half of season to predict second half)

## Built With

Python, pandas, scikit-learn, matplotlib, seaborn
