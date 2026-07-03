# F1 Pit Stop Prediction | Kaggle Playground Series S6E5

> Predicting whether an F1 driver will pit on the next lap using race strategy data.

---

## 🏁 Project Overview

- **Competition**: Kaggle Playground Series S6E5 (Predicting F1 Pit Stops)
- **Task**: Binary classification (pit or not on next lap)
- **Metric**: ROC AUC
- **Public Score**: 0.94541
- **Rank**: 2047/3023 (top 68%)

---

## 📊 Dataset

- 439,140 training samples, 188,165 test samples
- 15 features including:
  - Race context (lap, race number, position)
  - Tyre information (compound, age, wear)
  - Driver information
- Target imbalance: 80% no-pit, 20% pit

---

## 🔧 Approach

<img width="1980" height="5116" alt="diagram" src="https://github.com/user-attachments/assets/f4814c95-eaa4-429f-b3dd-7f09387bf07b" />

©️🖼️ Diagram Credits: [https://gitdiagram.com/](https://gitdiagram.com/)

### Data Preprocessing
- Categorical encoding: Label encoding for `Driver`, `Compound`, `Race`
- Train/validation split: 80/20 stratified
- No missing values

### Model
- **Algorithm**: LightGBM (gradient boosting with leaf-wise tree growth)
- **Hyperparameters**:
  - `num_leaves`: 31
  - `learning_rate`: 0.05
  - `feature_fraction`: 0.9
  - `num_boost_round`: 500
- **Validation AUC**: 0.9466

### Results
- **Public LB AUC**: 0.94541
- **Rank**: 2047/3023 with single submission
- **No feature engineering** or hyperparameter tuning

---

## 📂 Files

- `notebooks/baseline_lightgbm.ipynb` — Main notebook with full pipeline
- `submission.csv` — Final predictions for test set
- `README.md` — This file

## 🛠 Setup

```bash
pip install pandas numpy scikit-learn lightgbm
```

## 🚀 Future Work

- [ ] Feature engineering (lap phase, stint features, position changes)
- [ ] Cross-validation (5-fold)
- [ ] Hyperparameter tuning
- [ ] Ensemble with XGBoost/CatBoost
- [ ] Threshold calibration

## 📚 References

- [Kaggle Competition](https://www.kaggle.com/competitions/playground-series-s6e5)
- [LightGBM Documentation](https://lightgbm.readthedocs.io)

## 📬 Contact

Feel free to reach out for questions or feedback!
