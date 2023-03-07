# probability-calibration

Probability calibration is a technique to calibrate the probabilities of a classifier. This package provides a simple interface to calibrate the probabilities of a classifier (sklearn-like interface).

## Methods

- Platt Scaling
- Isotonic Regression
- Inductive Venn-Abers Predictor (IVAP)
- Cross Venn-Abers Predictor (CVAP)

## Installation

```zsh
$ pip install pcalibration
```

## Usage

```python
from pcalibration import CalibratorWrapper, CrossVennAbers

# Load the data
X_train, X_test, y_train, y_test = ...

# Load the classifier
model = ...

# Create a CalibratorWrapper object
calibrator = CalibratorWrapper(model, CrossVennAbers(k=5))

# Fit the calibrator
calibrator.fit(X_train, y_train)

# Predict the probabilities
y_pred = calibrator.predict_proba(X_test)
```
