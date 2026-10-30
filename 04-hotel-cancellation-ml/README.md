# Hotel Booking Cancellation Prediction (scikit-learn & Spark ML)

**Question:** Can we predict whether a hotel guest will cancel their booking, and what drives room prices?

## Data
[Hotel Reservations Classification Dataset](https://www.kaggle.com/datasets/ahsan81/hotel-reservations-classification-dataset) (Kaggle): booking details such as lead time, room type, special requests and price, with a cancellation label.

## What I did
- **EDA:** checked nulls and duplicates, looked at feature distributions and plotted a correlation heatmap.
- **Feature engineering:** one-hot encoded the categorical features and turned the label into a boolean.
- **Classification with scikit-learn:** trained logistic regression and a random forest, plotted feature importances, and used PCA to keep 80% of the variance (17 components) before refitting logistic regression.
- **Regression:** predicted average room price with linear, ridge and random forest regression. The random forest raised R² from 0.45 (linear and ridge) to 0.59.
- **Clustering:** segmented bookings with K-Means, choosing the number of clusters from an elbow plot (k = 5).
- **Distributed ML with Spark ML:** rebuilt the pipeline (VectorAssembler, Pipeline, train/test split) and trained logistic regression with L1, L2 and Elastic Net regularization, a random forest and a PCA model. Evaluated each with confusion matrices.

## Results (Spark ML, test set)

| Model | Test accuracy |
|---|---|
| **Random Forest** | **87.1%** |
| PCA + Logistic Regression | 80.3% |
| Logistic Regression (Elastic Net) | 80.2% |
| Logistic Regression (L1 / L2) | 80.2% |

The random forest beat the regularized linear models by about 7 points. This suggests cancellations depend on non-linear interactions between booking features.

## Skills and tools
scikit-learn, PySpark MLlib (Spark ML), pandas, logistic regression, regularization (L1, L2, Elastic Net), random forests, PCA, K-Means, feature importance, confusion matrices, Seaborn.
