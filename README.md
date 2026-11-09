# cs1090a-final-project

Predicting soccer player market values from Transfermarkt data.

## Project snapshot

The modeling table contains 85,721 player-seasons from 14 consistently covered European leagues (2012/13–2025/26). The target is the log10 Transfermarkt value at season end. Models use a chronological split: train through 2023, validate on 2024, and test on 2025.

The current stats-only gradient-boosting baseline reaches R² = 0.83 on the untouched 2025 season, with a typical prediction error of about ×1.51. The planned final deliverable, **Scout Lab**, will explore player valuations, hidden gems, and replacement players.

### Modeling guardrails

- Treat predictions as **Transfermarkt-style estimates**, not actual transfer fees.
- Use only information available during or before the season being predicted; current club and player snapshot fields can leak future information.
- Treat hidden-gem rankings as scouting leads, not recommendations: the early backtest is promising at the extreme top decile but is not consistent across all groups.
- Injury logs are a promising extension: time-stamped injury type, days missed, and recurrence could help distinguish low minutes caused by injury from low minutes caused by selection and may improve predictions of future value changes. Any source should be checked for uneven coverage, and only information known by the prediction date should be used.

| File | What it does |
|---|---|
| `milestone2_data.ipynb` | Loads and cleans the raw data, builds `clean/player_seasons.parquet` (one row per player per season) |
| `milestone3_analysis.ipynb` | EDA, baseline models, feature importance, hidden-gem analysis |

**Setup:** the raw data isn't in the repo (too large). Download `archive.zip` from [Kaggle](https://www.kaggle.com/datasets/davidcariboo/player-scores) and unzip it into `data/`. You only need it to re-run Milestone 2 — `milestone3_analysis.ipynb` runs from the committed `clean/player_seasons.parquet`.
