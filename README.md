# sklearn Pipeline Drill

A short exercise on sklearn `Pipeline` and `ColumnTransformer`. I found preprocessing leakage in my previous startup success prediction project, and I built this to close that gap.

The notebook fits one untuned `LogisticRegression` twice on 8,837 Crunchbase companies. The clean run fits the median, the scaler and the encoder inside every cross-validation fold. The leaky run fits them on all rows first. The clean run scored 0.794265 and the leaky run scored 0.794240, and the per-fold difference changes sign, so the gap is noise. A `Pipeline` prevents leakage. It does not detect it.

The data has a second problem a pipeline cannot fix. `funding_total_usd`, `funding_rounds` and `funding_duration` are final values recorded after each company's outcome, so the notebook keeps them and states the problem rather than solving it.

Rendered notebook: [Preprocessing Leakage on a Startup Model](https://www.kaggle.com/code/toextoe/preprocessing-leakage-on-a-startup-model) on Kaggle.

## Data

[Startup Success/Fail Dataset from Crunchbase](https://www.kaggle.com/datasets/yanmaksi/big-startup-secsees-fail-dataset-from-crunchbase)

The CSV is not in this repo. Download it from the link above and place it in the project root.

## Setup

```
pip install -r requirements.txt
```
