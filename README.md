# Student Performance Prediction

A beginner-friendly Jupyter Notebook that explores the UCI Student Performance dataset and compares a mean baseline with a random-forest regressor for predicting final mathematics grades (`G3`).

The analysis is for prediction practice, not causal explanation. It does not show why students perform well or poorly and should not be used to make high-stakes decisions about students.

## Setup

Use Python 3.10 or later. An existing environment that already has pandas,
matplotlib, seaborn, scikit-learn, and Jupyter can be used without installing
anything. For example, the following Anaconda environment is ready to run this
notebook:

```text
C:\Users\PC\anaconda3\anaconda2\python.exe
```

If those dependencies are not available in your chosen environment, install
them there:

```bash
python -m pip install pandas matplotlib seaborn scikit-learn jupyter
```

## Run

1. Open `student_performance_prediction.ipynb` in Jupyter Notebook, JupyterLab, or VS Code with the Jupyter extension.
2. Run the notebook cells from top to bottom.
3. The notebook downloads the official UCI Student Performance ZIP archive when run and reads `student-mat.csv` directly from memory. An internet connection is required; if the download fails, the notebook reports the official source URL and stops.

The notebook does not save a dataset copy or create a web application.

## Results

The random-forest model performed better on this held-out test split when the
earlier grades (`G1` and `G2`) were included. Without those grades, its errors
were higher and its R-squared was lower, indicating weaker predictive
performance for this split.

| Features | MAE (grade points) | RMSE (grade points) | R-squared |
|---|---:|---:|---:|
| With G1 and G2 | 1.216 | 2.033 | 0.799 |
| Without G1 and G2 | 3.010 | 3.765 | 0.309 |

These metrics are rounded results from one held-out test split and may vary
with a different split or dataset. They measure prediction, not causation, and
do not establish why students perform well or poorly.
