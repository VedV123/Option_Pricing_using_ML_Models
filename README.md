# Option Price Prediction using Machine Learning 📈

This project explores the use of machine learning models to predict financial option prices. It implements and evaluates three different regression models: an Artificial Neural Network (ANN), a Random Forest, and an XGBoost model, comparing their performance to understand their effectiveness in a data-driven pricing approach.

## About The Project

Traditional option pricing models like Black-Scholes rely on strong assumptions that may not hold true in real-world markets. This project aims to build data-driven models that can learn complex patterns from historical market data to predict option prices more accurately.

The primary goals were:
* To preprocess, transform, and engineer features from raw options data.
* To build, train, and fine-tune three distinct machine learning models.
* To evaluate the models based on standard regression metrics like Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R-squared ($R^2$).
* To identify the most influential market features in determining option prices.

---

## Models Implemented

* **Artificial Neural Network (ANN):** A multi-layer perceptron model built to capture non-linear relationships. Initially, the standard ANN had a very high Mean Absolute Percentage Error (MAPE) of **61.42%**. To fix this, the target variable was transformed to a logarithmic scale before training. This single change **slashed the MAPE to 18.16%**.
* **Random Forest:** An ensemble model using multiple decision trees to improve prediction accuracy and control over-fitting.
* **XGBoost:** A powerful and efficient gradient boosting algorithm known for its high performance in predictive modeling tasks.

---

## Results

All models achieved a very high R-squared ($R^2$) value of ~0.998. The results clearly show the dramatic improvement in the ANN's performance after applying the log transform, reducing its MAPE from over 61% to just 18%, making it the best model on that metric.

| Model                  | R-squared ($R^2$) | MAE     | MAPE     | RMSE    |
| ---------------------- | ----------------- | ------- | -------- | ------- |
| **ANN (Baseline)** | 0.9986            | 19.30   | 61.42%   | **32.56**   |
| **ANN (with Log)** | 0.9983            | 18.96   | **18.16%** | 35.38   |
| **Random Forest** | 0.9985            | 18.17   | 20.50%   | 32.71 |
| **XGBoost** | 0.9984            | **13.88** | 36.21%   | 34.71   |

---

## Feature Importance

An analysis was performed using the trained XGBoost model to identify the most influential features in predicting option prices. The results clearly indicate that **Moneyness** is the single most dominant factor that the model relies on. Other features like the underlying stock price and time to expiration contribute but to a much lesser extent.



This insight is valuable as it confirms that the model's predictions are heavily driven by the option's intrinsic value, which aligns with financial theory.

---

## License

Distributed under the MIT License. See `LICENSE` for more information.

---

## Acknowledgments

* Inspiration drawn from the research paper: `[Name of Paper and Link if Available]`
* Dataset source: `[Name of Data Source, e.g., NSE, Kaggle]`
