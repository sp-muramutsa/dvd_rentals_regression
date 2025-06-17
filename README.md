# 🎬 DVD Rental Duration Prediction

![Python](https://img.shields.io/badge/Python-3.10-blue) ![scikit-learn](https://img.shields.io/badge/scikit--learn-1.2-green) ![XGBoost](https://img.shields.io/badge/XGBoost-1.7-orange) ![License](https://img.shields.io/badge/license-MIT-brightgreen)

---

## 📖 Project Overview

This project develops and evaluates **regression models** to predict the number of days a customer will rent a DVD, leveraging historical rental data. Precise rental duration prediction assists in:

* Optimizing inventory management
* Enhancing customer service
* Improving operational planning

The solution includes multiple modeling approaches, thorough validation, hyperparameter tuning, and final evaluation on unseen data.

---

## 🗃️ Dataset

* **Size:** 15,861 records
* **Features include:**

  * Rental & return timestamps (`rental_date`, `return_date`)
  * Rental details (`amount`, `rental_rate`, `length`, `replacement_cost`)
  * Categorical features one-hot encoded (`movie_rating`, `special_features`)
* **Target:** Rental duration in days, calculated from rental and return dates.

---

## 🔧 Data Preprocessing & Feature Engineering

* Extracted date/time features from timestamps (month, day of week, hour).
* One-hot encoded special DVD features (trailers, behind-the-scenes, deleted scenes).
* Used a preprocessing pipeline for numerical features including imputation and scaling.

---

## ⚙️ Modeling & Evaluation

| Model             | Mean CV RMSE | Std. Dev | Notes                         |
| ----------------- | ------------ | -------- | ----------------------------- |
| Linear Regression | 1.63 days    | 0.015    | Baseline model                |
| Decision Tree     | 1.91 days    | 0.048    | Overfits training data        |
| Random Forest     | 1.43 days    | 0.028    | Best baseline model           |
| XGBoost           | 1.47 days    | 0.019    | Strong but slightly behind RF |

---

## 🔍 Hyperparameter Tuning

* **Grid Search:** Explored different `n_estimators` and `max_features`, with and without bootstrapping.
* **Randomized Search:** Broader parameter search revealed improved results, best RMSE \~1.21 days on CV.
* Tuning improved model robustness but gains were moderate.

---

## 🎯 Final Results

* **Test set RMSE:** \~1 day, 9 hours
* **95% Confidence Interval:** 1 day, 8 hours to 1 day, 10 hours
* Demonstrates *strong generalization* and practical accuracy for rental duration prediction.

---

## 🚀 How to Use

1. Clone or download the repo.
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```
3. Run the Jupyter Notebook to reproduce training, validation, tuning, and evaluation.
4. Use the final Random Forest model for predictions on new rental data.

---

## 📊 Feature Importance

The final model highlights key predictive features, with **amount** and **rental rate** showing highest importance. Visualized using pie charts for interpretability.

---

## 📚 References & Tools

* [scikit-learn](https://scikit-learn.org/) for ML modeling
* [XGBoost](https://xgboost.readthedocs.io/) for ensemble learning
* [Matplotlib](https://matplotlib.org/) for data visualization
* [SciPy](https://scipy.org/) for statistical analysis

---

## ⚖️ License

This project is licensed under the **MIT License** — see the LICENSE file for details.

---

