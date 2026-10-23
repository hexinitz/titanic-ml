# Titanic Survival Prediction

A small machine learning project that explores the Titanic passenger dataset and predicts whether passengers survived. The work is organized in a Jupyter notebook, from exploring the data to preparing features, training a model, and generating predictions for the test dataset.

## Project structure

```text
titanic_ml/
├── data/
│   ├── train.csv
│   ├── test.csv
│   └── gender_submission.csv
├── main.ipynb
├── pyproject.toml
├── requirements.txt
├── README.md
├── src/
└── uv.lock
```

The exact contents of `data/` may vary. The notebook expects `data/train.csv` and `data/test.csv` to be present.

## What it does

- Explores the dataset with Pandas, Matplotlib, and Seaborn.
- Creates a stratified train/validation split.
- Handles missing age values and encodes categorical features.
- Uses a `RandomForestClassifier` with `GridSearchCV` to tune model parameters.
- Predicts survival for the test dataset and writes the results to `data/predictions.csv`.

## Requirements

- Python 3.12
- The packages listed in `requirements.txt`

## Setup

Run these commands from the project directory.

### Using `uv`

If the project dependencies are already declared in `pyproject.toml`, install them with:

```bash
uv sync
```

To install the packages listed in `requirements.txt` into the project's virtual environment instead:

```bash
uv venv
uv pip install --python .venv/bin/python -r requirements.txt
```

### Using `venv` and `pip`

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

On Arch Linux, use `python` for the system Python command. If you use a different environment manager, activate that environment before installing the requirements.

## Run the notebook

Start Jupyter from the project root so the relative `data/` paths resolve correctly:

```bash
jupyter lab
```

Or use:

```bash
jupyter notebook
```

Open `main.ipynb` and run the cells in order. When the final prediction cells complete, the notebook saves predictions to `data/predictions.csv`.

## Notes

This is a learning project, so the notebook focuses on trying out the workflow rather than providing a production-ready prediction pipeline. The validation score can vary because the stratified split does not set a fixed random seed. The Kaggle-style test dataset does not include survival labels, so its predictions cannot be evaluated locally without a separate labelled dataset.
