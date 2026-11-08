# cs1090a-final-project

Predicting soccer player market values from Transfermarkt data.

| File | What it does |
|---|---|
| `milestone2_data.ipynb` | Loads and cleans the raw data, builds `clean/player_seasons.parquet` (one row per player per season) |
| `milestone3_analysis.ipynb` | EDA, baseline models, feature importance, hidden-gem analysis |

**Setup:** the raw data isn't in the repo (too large). Download `archive.zip` from [Kaggle](https://www.kaggle.com/datasets/davidcariboo/player-scores) and unzip it into `data/`. You only need it to re-run Milestone 2 — `milestone3_analysis.ipynb` runs from the committed `clean/player_seasons.parquet`.
