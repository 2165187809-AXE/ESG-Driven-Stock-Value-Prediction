ESG-Driven Stock Value Prediction Model

This is a machine learning research project conducted as part of an undergraduate research study (Nov 2023 – Mar 2024).
The objective of the project is to predict the intrinsic value of stocks using Environmental, Social, and Governance (ESG) factors, combining feature engineering and machine learning models.

This project uses Python as its primary language and leverages libraries such as Pandas, NumPy, Scikit-learn, and Matplotlib to build a complete end-to-end pipeline, from data processing and feature engineering to model training, validation, and visualization.

1. Methodology

The project follows a structured machine learning workflow:

1.1 Data Processing

Data Loading: Stock price and ESG factor data (500+ companies over 10 years).

Data Cleaning: Missing values handled via mean/median imputation to ensure data quality.

Transformation: Standardized numerical features with StandardScaler for better model performance.

1.2 Feature Engineering

To allow the models to learn both financial and sustainability-related patterns, several categories of features were engineered:

Composite ESG Score: Average of environmental, social, and governance ratings.

Momentum Indicator: 5-day price percentage change ().momentum_5d

Rolling Mean: 10-day moving average of stock prices ().rolling_mean_10

1.3 Validation Strategy

A walk-forward backtesting approach was adopted to respect the time-series nature of financial data:

The dataset was split into 5 sequential folds by date.

In each fold, models were trained on past data and tested on future data.

This ensured no data leakage and provided a realistic evaluation of predictive performance.

1.4 Model Training

Random Forest Regressor: Trained to predict stock prices, then converted to classification labels (above/below median).

Logistic Regression (Baseline): Used as a benchmark classification model.

Performance Metrics: Root Mean Squared Error (RMSE) for regression, and Accuracy for classification.

2. Results

The Random Forest model outperformed Logistic Regression, achieving a 15% relative lift in classification accuracy.

Walk-forward backtesting confirmed consistent outperformance across folds.

Visualization highlighted the performance gap between the two models:

<p align="center"> <img src="results/backtest_plot.png" width="600" alt="Backtest Results"> </p>


3. Conclusion and Future Work

This project demonstrates that incorporating ESG factors into stock prediction models provides measurable performance improvements.

Potential areas for future improvement include:

Expanding feature engineering (e.g., volatility indicators, interaction terms).

Hyperparameter optimization using Grid Search or Optuna.

Testing advanced models such as Gradient Boosting (XGBoost, LightGBM).

Incorporating portfolio-level optimization and risk-adjusted return metrics (e.g., Sharpe ratio).
