# eda-of-5000_TMDB-movies

This project performs a detailed analysis and predictive modeling on movie revenue and user ratings using the TMDB 5000 movie dataset. The workflow includes data cleaning, inflation adjustment, actor/crew feature extraction, exploratory analysis, and regression modeling.

---

## 📁 Dataset

- `tmdb_5000_movies.csv`  
- `tmdb_5000_credits.csv`  
- 📌 Both sourced from [Kaggle - TMDB Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)

---

## 📌 Project Goals

- 📈 Predict **movie revenue**
- ⭐ Predict **user rating (vote average)**
- 🧠 Understand influence of **cast, crew, budget, popularity, runtime, genres** on success metrics

---

## 🧰 Key Steps

### ✅ 1. Data Preprocessing
- Merged `credits` data with movie data
- Removed unimportant columns like `homepage`, `tagline`, `keywords`, etc.
- Replaced `?` and null values with appropriate fill strategies
- Parsed JSON columns (genres, cast, crew) into usable Python objects
- Filtered unrealistic rows (zero budget or revenue)

### ✅ 2. Feature Engineering
- Extracted actor names from `cast`
- Extracted director, producer, and writer names from `crew`
- Counted actor and crew presence as binary flags in new columns
- Created `num_actors` feature

### ✅ 3. Exploratory Data Analysis
- Correlation heatmaps and revenue distribution
- Outlier analysis for budget/revenue/vote average
- Impact of cast and production company on performance

### ✅ 4. Modeling

#### 🎯 Revenue Prediction
- Models: `OLS`, `Ridge`, `XGBoost Regressor`
- Trained with and without cast/crew-based features
- Evaluation metric: Adjusted R²

#### ⭐ Rating Prediction
- Used same pipelines as revenue
- Targets `vote_average` column

---

## 📊 Key Results

- **XGBoost** performed best for both revenue and rating forecasting
- Including cast and crew features improved results slightly
- `budget`, `runtime`, and `popularity` were top predictors

---

## 📦 Project Structure

eda-of-5000_TMDB-movies/
│
├── TMDB5000analysis_prediction.ipynb # Main code notebook
├── README.md
├── encoded_data.csv

