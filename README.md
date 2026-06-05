# Simple Linear Regression Plot Generator

This project is a Streamlit app for generating random simple linear regression data, fitting a regression model, and visualizing the top outliers.

The generated data follows:

```text
y = aX + b + noise
```

The app estimates the regression line with `scikit-learn`, calculates residuals, and highlights the largest outliers by absolute residual.

## Features

- Generate random `X` and `Y` data
- Randomly generate true slope `a`, intercept `b`, and noise variance
- Fit a simple linear regression model
- Display estimated slope and intercept
- Calculate residual and absolute residual
- Show top K outliers
- Plot data points, regression line, and outliers
- Interactive controls with Streamlit

## Project Files

```text
.
+-- linear_regression_plot_generator.py
+-- requirements.txt
+-- linear_regression_data.csv
+-- linear_regression_plot.png
+-- README.md
```

## Install Dependencies

Run this command in the project folder:

```powershell
pip install -r requirements.txt
```

## Start The App

Use Streamlit to launch the app:

```powershell
streamlit run linear_regression_plot_generator.py
```

After running the command, Streamlit will show a local URL such as:

```text
http://localhost:8501
```

Open that URL in your browser.

## App Controls

The sidebar lets you adjust:

- `n`: number of generated data points
- `x_min`, `x_max`: X value range
- `a_min`, `a_max`: true slope range
- `b_min`, `b_max`: true intercept range
- variance range
- random seed
- Top K outlier count

## Output Data

The app creates a DataFrame with these columns:

```text
X
Y
Y_pred
residual
abs_residual
is_outlier
```

The top outlier table includes:

```text
X
Y
Y_pred
residual
abs_residual
```

## Core Functions

- `generate_data()`: generates random regression data
- `fit_linear_regression()`: fits the regression model
- `find_top_outliers()`: finds the largest residual outliers
- `plot_regression()`: creates the regression plot
- `main()`: launches the Streamlit interface

## Notes

The app uses the `Agg` matplotlib backend so plots can render reliably in environments without a GUI backend.
