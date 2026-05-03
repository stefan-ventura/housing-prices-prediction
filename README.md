# House Price Prediction

A machine learning project that predicts house prices based on property features such as size, number of rooms, location, and amenities. Built using Linear Regression and Random Forest Regression.

---

## Dataset

- **Source:** [Kaggle Housing Prices Dataset](https://www.kaggle.com/datasets)
- **Size:** 545 rows, 13 columns
- **Target variable:** `price`

---

## Features

| Feature | Description |
|---|---|
| `price` | Sale price of the house (target) |
| `area` | Size of the house in square feet |
| `bedrooms` | Number of bedrooms |
| `bathrooms` | Number of bathrooms |
| `stories` | Number of floors |
| `parking` | Number of parking spaces |
| `mainroad` | Connected to main road (yes/no) |
| `guestroom` | Has a guest room (yes/no) |
| `basement` | Has a basement (yes/no) |
| `hotwaterheating` | Has hot water heating (yes/no) |
| `airconditioning` | Has air conditioning (yes/no) |
| `prefarea` | Located in a preferred area (yes/no) |
| `furnishingstatus` | Furnishing level (furnished/semi-furnished/unfurnished) |

---

## Project Structure

```
├── Housing.csv          # Dataset
├── notebook.ipynb       # Main Jupyter Notebook
└── README.md
```

---

## Methodology

### Preprocessing
- Handled missing values (numerical → median, categorical → mode)
- One-hot encoded categorical variables
- Standardized numerical features

### Feature Engineering
- `total_rooms` = bedrooms + bathrooms
- `area_per_room` = area / (total_rooms + 1)

### Models
- **Linear Regression** — baseline model
- **Random Forest Regression** — to capture non-linear relationships

---

## Results

| Model | R² | MAE (% of mean price) | RMSE (% of mean price) |
|---|---|---|---|
| Linear Regression | 0.66 | 19.3% | 26.2% |
| Random Forest | 0.61 | 20.8% | 28.0% |

Linear Regression outperformed Random Forest, suggesting the relationships in this dataset are largely linear. The dataset size (545 rows) likely limits the benefit of more complex models.

### Key Findings
- `area` and `bathrooms` are the strongest predictors of price
- Houses with air conditioning tend to have higher prices
- No single feature dominates — multiple features together drive price

---

## Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
```

Install with:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## Usage

1. Clone the repository
```bash
git clone https://github.com/venturastefan31/housing-prices-prediction.git
```

2. Add the dataset (`Housing.csv`) to the project folder

3. Open and run the notebook
```bash
jupyter notebook notebook.ipynb
```
