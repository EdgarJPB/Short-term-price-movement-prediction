# Short-term-price-movement-prediction

This project builds a machine learning-based trading strategy using Bitcoin order book data. A Random Forest classifier is trained to predict short-term price movement—up, down, or unchanged—based on engineered features from the order book.

----

## Objective:

Use historical order book data (top 10 bid/ask levels) from two days to predict the next 15-minute price direction on the third day and design a trading strategy based on the model's predictions.

----

## Data Overview:

Source: High-frequency Bitcoin order book snapshots.

Granularity: Resampled to 3-minute intervals for stability and feature consistency.

Duration: Uses 2 days of data for training, 1 day for testing.

---

## Feature Engineering:

Includes both raw and derived features:

  + Mid Price: Average of best bid and ask.

  + Spread: Difference between bid and ask.

  + Order Book Imbalance: Measures supply/demand pressure.

  + Momentum and Rolling features: Capture trends and smooths out noise.

## Target Variable

  +1: Price expected to rise > 0.1%

  -1: Price expected to fall < -0.1%

  0: Price change between -0.1% and 0.1% (stable)

---

## Modeling
Algorithm: RandomForestClassifier (from scikit-learn)

Evaluated via: Accuracy, Precision, Recall, and F1-score

Final use: Generate trade signals and simulate trading performance

---

## Strategy Outcome

The notebook concludes with a backtest of the strategy based on the classifier's output, demonstrating potential profitability under specific thresholds and assumptions.
