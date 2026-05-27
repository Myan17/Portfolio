# ML Module - ICU Capacity Forecasting

This folder contains the **machine learning layer** for the ICU Capacity Forecasting project.

## Current forecasting strategy

The first version of the ML stack uses:

1. **Baseline forecast** for a sanity-check benchmark
2. **SARIMA** for interpretable classical time-series modeling
3. **Prophet** for trend + seasonality modeling
4. **Risk labeling** on top of predictions for Green / Yellow / Red alerts

## Why this approach

We are intentionally starting with simple, interpretable models before moving to more complex methods like LSTMs or hybrid models. That gives us:

- easier debugging
- cleaner demos
- faster iteration
- stronger explainability for project reviews

## Folder overview

- `preprocessing/` - load, validate, clean, and resample data
- `features/` - optional time-based feature generation
- `models/` - forecast model wrappers
- `pipelines/` - training and inference orchestration
- `utils/` - metrics, risk labeling, serialization helpers
- `artifacts/` - saved models and forecast outputs
- `data/` - raw and processed files used by the ML module

## Expected input schema

At minimum, the model layer expects:

- `hospital_id`
- `timestamp`
- `icu_occupied`

Optional but recommended:

- `icu_capacity`

## Example commands

```bash
python -m ml.train --input ml/data/raw/hospital_a.csv --model baseline
python -m ml.train --input ml/data/raw/hospital_a.csv --model sarima
python -m ml.predict --input ml/data/raw/hospital_a.csv --model baseline --hospital-id HOSPITAL_A
python -m ml.evaluate --input ml/data/raw/hospital_a.csv
```

## Notes

- The code is written to be readable first.
- Optional dependencies like `prophet` and `statsmodels` are imported lazily.
- The first implementation keeps training and inference separate so the backend can later load existing forecasts without retraining.
