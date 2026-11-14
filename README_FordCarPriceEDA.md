# Ford Car Price: Exploratory Data Analysis (EDA)

A Jupyter/Kaggle notebook that performs **exploratory data analysis** on a dataset of used Ford cars, looking at how price relates to features such as year, mileage, engine size, transmission and fuel type.

## Dataset

- **Name:** Ford Car Price Prediction (by `adhurimquku` on Kaggle)
- **File:** `ford.csv`
- **Size:** 17,966 rows x 9 columns
- **Missing values:** none (every column has 17,966 non-null entries)

| Column | Type | Description |
|--------|------|-------------|
| `model` | text | Ford model (e.g. Fiesta, Focus, Kuga, Puma, KA, B-MAX) |
| `year` | integer | Year of registration |
| `price` | integer | Listing price (target variable) |
| `transmission` | text | Manual / Automatic, etc. |
| `mileage` | integer | Distance driven |
| `fuelType` | text | Petrol, Diesel, etc. |
| `tax` | integer | Road tax |
| `mpg` | float | Fuel efficiency (miles per gallon) |
| `engineSize` | float | Engine size in litres |

## What the Notebook Does

1. **Setup**: imports `numpy`, `pandas`, `seaborn`, `matplotlib` and loads `ford.csv` from the Kaggle input directory.
2. **Data inspection**:
   - `df.shape`, `df.head(10)`, `df.columns`
   - `df.info()` for data types and non-null counts
   - `df.isnull().sum()` to check for missing values
   - `df.describe()` for summary statistics
3. **Visual EDA** (using seaborn):
   - **Histogram + KDE** of `price` (60 bins) to see the price distribution
   - **Correlation heatmap** of all numeric columns
   - **Box plot** of `price` by `year`
   - **Scatter plot** of `price` vs `mileage`
   - **Box plot** of `price` by `engineSize`
   - **Box plot** of `price` by `transmission`
   - **Box plot** of `price` by `fuelType`

## Key Statistics (from `df.describe()`)

| Feature | Mean | Min | Max |
|---------|------|-----|-----|
| `price` | about 12,280 | 495 | 54,995 |
| `mileage` | about 23,363 | 1 | 177,644 |
| `year` | about 2016.9 | 1996 | 2060 |
| `mpg` | about 57.9 | 20.8 | 201.8 |
| `engineSize` | about 1.35 | 0 | - |

### Data quality notes spotted in the output

- `year` has a maximum of **2060**, which is not a valid registration year and is likely a data-entry error.
- `engineSize` has a minimum of **0**, which is suspicious for a petrol or diesel car.
- `mpg` has a maximum of **201.8**, which may be an outlier.

These would need cleaning before building a prediction model.

## How to Run

**Requirements:** Python 3, `numpy`, `pandas`, `seaborn`, `matplotlib`, `jupyter`

```bash
pip install numpy pandas seaborn matplotlib jupyter
jupyter notebook
```

**On Kaggle:** add the dataset *Ford Car Price Prediction* to the notebook and click **Run All**.

**Locally:** download `ford.csv` and change the path in the data-loading cell, for example:

```python
df = pd.read_csv("ford.csv")
```

The current path (`/kaggle/input/datasets/adhurimquku/ford-car-price-prediction/ford.csv`) only works inside Kaggle.

## Project Structure

```
notebook.ipynb   -> EDA notebook (this project)
ford.csv         -> dataset (download from Kaggle)
README.md        -> project documentation
```

## Possible Next Steps

- Remove or fix invalid values (year 2060, engine size 0)
- Handle outliers in `price`, `mileage` and `mpg`
- Encode categorical columns (`model`, `transmission`, `fuelType`)
- Train and compare regression models (Linear Regression, Random Forest, Gradient Boosting) to predict `price`
- Evaluate with MAE, RMSE and R-squared

## Tools Used

Python, Pandas, NumPy, Seaborn, Matplotlib, Kaggle Notebooks.
