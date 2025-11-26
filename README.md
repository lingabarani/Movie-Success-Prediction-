# Movie-Success-Prediction-
## Project Overview

This project aims to **predict movie success** (box office revenue) using IMDB and TMDB datasets, while also **analyzing viewer sentiment** from movie overviews and reviews. Python is used for data processing, VADER for sentiment analysis, machine learning for revenue prediction, and Power BI for visualizations.  

**Objectives:**
- Predict movie revenue using regression models.  
- Analyze sentiment trends in movie overviews and reviews.  
- Explore genre-wise sentiment and revenue patterns.  
- Visualize insights in Power BI dashboards.  

---

## 🛠 Tools & Technologies

- **Python**: pandas, numpy, sklearn, xgboost, vaderSentiment, matplotlib, seaborn  
- **Google Colab**: For preprocessing, sentiment analysis, and model training  
- **Power BI Desktop**: For interactive dashboards and visualizations  
- **Excel**: Optional for quick data inspection  

---

## 📂 Datasets

1. **TMDB 5000 Movie Metadata**  
   - [Kaggle link](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)  
   - Contains movie details: title, budget, revenue, genres, popularity, runtime, overview  

2. **IMDB 50K Movie Reviews**  
   - [Kaggle link](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)  
   - Contains user reviews and sentiment labels  

> Note: Datasets can be downloaded manually or via Kaggle API in Google Colab.

---

## 📝 Google Colab Notebook Workflow

1. **Load Datasets**  
   - Import TMDB metadata and IMDB reviews  

2. **Data Cleaning & Feature Engineering**  
   - Extract release year, month, genres, runtime, budget, revenue  
   - Convert budget and revenue to numeric/log scale  

3. **Sentiment Analysis (VADER)**  
   - Compute `vader_mean` score for TMDB overviews  
   - Validate VADER sentiment on IMDB review dataset  

4. **Regression Model for Revenue Prediction**  
   - Features: budget, popularity, vote_average, vote_count, runtime, genre dummies, sentiment score, release month  
   - Models: Linear Regression, Random Forest Regressor, XGBoost  
   - Evaluation: RMSE, MAE, R², scatter plot of actual vs predicted revenue  

5. **Genre-wise Sentiment Analysis**  
   - Average sentiment by primary genre  
   - Visualized with bar charts in Colab  

6. **Deliverables Produced in Notebook**  
   - Inline plots for sentiment distributions and model evaluation  
   - Top feature importance chart  
   - Final processed DataFrame ready for Power BI

---

## 📊 Power BI Dashboard Workflow

1. **Load Processed CSV** (`movies_model.csv` from Colab)  
2. **Visualizations:**
   - **Gauge / Card**: Sentiment Overview
   - **Scatter Chart**: Success Prediction (purple) 
   - **Bar chart**: Genre analysis  
   - **Scatter chart**: Rating vs Sentiment (blue)
   - **Column chart**: Genre Revenue 

3. **Interactivity:**
   - Add slicers for `primary_genre` and `release_year`  
   - Hover tooltips show movie title, budget, revenue, sentiment score  

> All visuals update dynamically with slicers for interactive exploration.

---

## 💻 How to Run

### Python Notebook (Google Colab)
```bash
# Install dependencies
!pip install pandas numpy matplotlib seaborn scikit-learn xgboost vaderSentiment openpyxl
```
  - Open Mov_Suc_Pred.ipynb in Google Colab
  - Run all cells; outputs appear inline

### Power BI Dashboard

  - Export movies_model.csv from Colab
  - Open Power BI Desktop → Get Data → Text/CSV → Load movies_model.csv
  - Recreate or open Movie_Success_Sentiment_Dashboard.pbix for dashboards

 ## Key Insights
 
  - Movie budget, popularity, and vote count strongly predict revenue
  - Sentiment (vader_mean) moderately influences success
  - Genres like Comedy and Adventure have higher average sentiment
  - Regression models achieved R² scores between 0.4–0.6 depending on algorithm
