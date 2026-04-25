# 🚗 Прогнозирование риска дорожных аварий

> Kaggle Competition: [Playground Series S5E10](https://www.kaggle.com/competitions/playground-series-s5e10)

Энд-ту-энд пайплайн для предсказания вероятности аварийности на участке дороги. Реализовано сравнение классических алгоритмов и ансамблевых методов.

## 📊 Датасет
- **Объём:** 517 754 строки (train), 172 585 строк (test)
- **Признаки:** 4 категориальных, 4 числовых, 4 бинарных
- **Целевая переменная:** `accident_risk` (регрессия)
- **Метрика:** `RMSE`

## 🛠️ Стек
- `pandas`, `numpy`, `scikit-learn`
- `XGBoost`, `LightGBM`, `CatBoost`
- `Pipeline`, `ColumnTransformer`, `RobustScaler`, `OneHotEncoder`
- `seaborn`, `matplotlib`

## 📈 Результаты (5-Fold CV)
| Модель | RMSE | Время обучения |
|--------|------|----------------|
| Ridge | `0.0577` | ~30 сек |
| RandomForest | `0.0893` | ~46 мин |
| **XGBoost** | **`0.0568`** | **~2 мин** ⭐ |
| CatBoost | `0.0571` | ~46 сек |
| LightGBM | `0.0570` | ~25 сек |
| **Stacking** | `~0.0565` | ~17 мин |

> 💡 XGBoost показал лучший баланс скорости и качества. Stacking дал незначительный прирост ценой большего времени обучения.
