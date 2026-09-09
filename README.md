# 🍽️ Zomato Bangalore Restaurant Data Science Project

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--learn-yellow)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Internship](https://img.shields.io/badge/Internship-Alfido%20Tech-red)

An end-to-end data science project developed as part of the **Alfido Tech Data Science Internship**.

This project analyzes Zomato restaurant data from Bangalore to discover restaurant-market patterns, customer preferences, pricing trends, popular cuisines, and service availability. It also uses machine learning for restaurant price classification, rating prediction, and restaurant segmentation.

---

## 🔗 Project Links

- **GitHub Repository:**  
  [Zomato Bangalore Restaurant Data Science Project](https://github.com/KartikKachwahe/ZOMATO-BANGALORE-RESTAURANT-DATA-SCIENCE-PROJECT)

- **Jupyter Notebook:**  
  [View Complete Project Notebook](https://github.com/KartikKachwahe/ZOMATO-BANGALORE-RESTAURANT-DATA-SCIENCE-PROJECT/blob/main/Alfido_Tech_Zomato_Complete_Data_Science_Project.ipynb)

---

## 📌 Project Overview

Bangalore has a highly competitive restaurant market. Restaurant owners and food-delivery platforms need to understand:

- Which locations have the highest restaurant concentration?
- Which cuisines and restaurant types are most popular?
- How do online ordering and table booking relate to ratings?
- What factors distinguish expensive restaurants?
- Can restaurant ratings be predicted using available features?
- Can restaurants be grouped into meaningful business segments?

This project answers these questions using data cleaning, exploratory data analysis, machine learning, clustering, and business interpretation.

---

## 🎯 Project Objectives

The main objectives of this project are:

1. Clean and validate the raw Zomato dataset.
2. Identify and remove malformed and duplicate records.
3. Analyze restaurant locations, types, cuisines, ratings, costs, and votes.
4. Calculate important restaurant-market KPIs.
5. Study online-order and table-booking availability.
6. Create useful features for machine learning.
7. Predict whether a restaurant belongs to the expensive category.
8. Predict restaurant ratings using regression.
9. Compare multiple classification and regression algorithms.
10. optimize selected models using hyperparameter tuning.
11. Identify important predictive features.
12. Segment restaurants using unsupervised learning.
13. Visualize segments using PCA and t-SNE.
14. Provide actionable business recommendations.

---

## 📊 Dataset Description

The original dataset contains:

- **56,252 rows**
- **13 columns**
- Restaurant information from different areas of Bangalore

### Dataset Features

| Column | Description |
|---|---|
| `address` | Restaurant address |
| `name` | Restaurant name |
| `online_order` | Whether online ordering is available |
| `book_table` | Whether table booking is available |
| `rate` | Restaurant rating |
| `votes` | Number of customer votes |
| `phone` | Restaurant contact number |
| `location` | Area in Bangalore |
| `rest_type` | Restaurant type |
| `dish_liked` | Popular dishes |
| `cuisines` | Cuisines offered |
| `approx_cost(for two people)` | Approximate cost for two customers |
| `listed_in(type)` | Zomato listing category |

---

## 🔄 Project Workflow

```text
Business Understanding
        ↓
Data Loading and Understanding
        ↓
Data Quality Assessment
        ↓
Data Cleaning and Validation
        ↓
Exploratory Data Analysis
        ↓
KPI Development
        ↓
Feature Engineering
        ↓
Classification Modeling
        ↓
Regression Modeling
        ↓
Cross-Validation and Hyperparameter Tuning
        ↓
Feature Importance
        ↓
Restaurant Clustering
        ↓
PCA and t-SNE Visualization
        ↓
Business Insights and Recommendations
```

---

## 🧹 Data Cleaning and Preprocessing

The following cleaning steps were performed:

- Examined dataset structure, data types, and unique values.
- Identified missing values in each column.
- Detected **15,703 exact duplicate rows** in the raw dataset.
- Identified malformed records where review text appeared in incorrect columns.
- Validated `online_order`, `book_table`, and `listed_in(type)` using their expected values.
- Removed **8,896 structurally malformed records**.
- Removed duplicate rows after structural validation.
- Converted ratings such as `4.1/5` into numeric values.
- Converted votes into a numeric column.
- Removed commas from restaurant costs and converted them into numeric values.
- Retained missing ratings for general analysis.
- Removed records with missing target values only when training models.
- Used median imputation for numerical model features.
- Used most-frequent imputation for categorical model features.
- Applied one-hot encoding to categorical variables.
- Used machine-learning pipelines to prevent data leakage.

### Final Cleaned Dataset

After cleaning and validation:

- **Clean listings:** 33,660
- **Unique restaurant names:** 8,641
- **Locations represented:** 93
- **Valid rated records:** 28,133

---

## 📈 Exploratory Data Analysis

The exploratory analysis covers:

### Univariate Analysis

- Rating distribution
- Cost distribution
- Vote distribution
- Restaurant-type frequency
- Cuisine frequency
- Location frequency

### Bivariate Analysis

- Rating versus online-order availability
- Rating versus table-booking availability
- Rating versus cost
- Rating versus votes
- Cost across restaurant types
- Restaurant distribution by location

### Multivariate Analysis

- Relationships among rating, cost, votes, and cuisine count
- Service availability across restaurant categories
- Correlation analysis among numerical features
- Restaurant-segment comparisons

### Outlier Analysis

Box plots and statistical summaries were used to identify unusually high values in:

- Votes
- Cost for two
- Restaurant engagement

---

## 📌 Key Performance Indicators

| KPI | Result |
|---|---:|
| Clean restaurant listings | 33,660 |
| Unique restaurant names | 8,641 |
| Number of locations | 93 |
| Valid rated records | 28,133 |
| Average rating | 3.68/5 |
| Median rating | 3.70/5 |
| Average cost for two | ₹545.49 |
| Median cost for two | ₹400 |
| Average votes | 222.62 |
| Median votes | 44 |
| Restaurants with online ordering | 60.21% |
| Restaurants with table booking | 11.58% |

---

## 🔍 Important Business Insights

### 1. Location Analysis

- **BTM** has the highest restaurant concentration.
- BTM contains approximately **2,781 restaurant listings**.
- Other highly represented areas include Whitefield, HSR, Marathahalli, and Indiranagar.

A high restaurant count indicates strong market demand but also greater competition.

### 2. Restaurant-Type Analysis

- **Quick Bites** is the most common restaurant type.
- It contains approximately **12,691 listings**.
- This indicates strong demand for affordable and convenient food options.

### 3. Cuisine Analysis

- **North Indian** is the most frequently represented cuisine.
- It appears approximately **13,912 times** in the cleaned data.
- High cuisine popularity indicates strong demand but may also indicate market saturation.

### 4. Listing-Type Analysis

- **Delivery** is the most common Zomato listing category.
- This highlights the importance of delivery-oriented restaurant operations.

### 5. Online Ordering

- Approximately **60.21%** of restaurants provide online ordering.
- Restaurants with online ordering have an average rating of approximately **3.705**.
- Restaurants without online ordering have an average rating of approximately **3.629**.

Online ordering is associated with a slightly higher average rating, but this does not prove that online ordering directly causes better ratings.

### 6. Table Booking

- Only **11.58%** of restaurants offer table booking.
- Restaurants with table booking have an average rating of approximately **4.078**.
- Restaurants without table booking have an average rating of approximately **3.617**.

Table booking is more common among premium, buffet, pub, and casual-dining restaurants.

### 7. Correlation Findings

- Correlation between rating and votes: **0.399**
- Correlation between rating and cost: **0.334**

Popular and expensive restaurants tend to have somewhat higher ratings, but correlation does not imply causation.

---

## 🛠️ Feature Engineering

The following features were created:

| Feature | Purpose |
|---|---|
| `rating` | Clean numeric restaurant rating |
| `votes_num` | Numeric customer vote count |
| `cost_for_two` | Clean numeric restaurant cost |
| `cuisine_count` | Number of cuisines offered |
| `online_order_flag` | Binary indicator for online ordering |
| `book_table_flag` | Binary indicator for table booking |
| `is_expensive` | Classification target based on median cost |
| `log_votes` | Log-transformed vote count for clustering |

Feature engineering helped convert raw restaurant information into model-ready variables.

---

# 🤖 Machine Learning

## Classification: Expensive Restaurant Prediction

The classification objective is to predict whether a restaurant belongs to the expensive category.

The expensive category was created using the median restaurant cost as the threshold.

### Classification Models Compared

- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier
- Gradient Boosting Classifier
- K-Nearest Neighbors
- Support Vector Machine

The dataset was divided into:

- **80% training data**
- **20% testing data**

Stratified sampling was used to maintain the target distribution.

### Classification Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Random Forest | 0.928 | 0.950 | 0.897 | 0.923 | 0.972 |
| KNN | 0.862 | 0.885 | 0.817 | 0.850 | 0.927 |
| SVM | 0.858 | 0.906 | 0.784 | 0.841 | 0.914 |
| Gradient Boosting | 0.858 | 0.911 | 0.779 | 0.840 | 0.918 |
| Decision Tree | 0.857 | 0.912 | 0.775 | 0.838 | 0.914 |
| Logistic Regression | 0.853 | 0.903 | 0.776 | 0.834 | 0.919 |

### Best Classification Model

The **Random Forest Classifier** produced the best overall performance:

- Accuracy: **92.8%**
- Precision: **95.0%**
- Recall: **89.7%**
- F1 Score: **92.3%**
- ROC-AUC: **97.2%**

RandomizedSearchCV was used for hyperparameter optimization.

- Best cross-validation F1 score: **0.8939**
- Important features included votes, restaurant type, rating, cuisine count, and table-booking availability.

---

## Regression: Restaurant Rating Prediction

The regression objective is to predict the restaurant rating using restaurant characteristics.

### Regression Models Compared

- Linear Regression
- Ridge Regression
- Lasso Regression
- Elastic Net Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor
- Extra Trees Regressor

### Regression Results

| Model | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Extra Trees | 0.065 | 0.161 | 0.858 |
| Random Forest | 0.164 | 0.246 | 0.669 |
| Decision Tree | 0.204 | 0.298 | 0.515 |
| Gradient Boosting | 0.223 | 0.314 | 0.460 |
| Ridge Regression | 0.269 | 0.349 | 0.333 |
| Linear Regression | 0.269 | 0.349 | 0.333 |
| Elastic Net | 0.276 | 0.355 | 0.309 |
| Lasso Regression | 0.278 | 0.357 | 0.301 |

### Best Regression Model

The **Extra Trees Regressor** produced the best test performance:

- MAE: **0.065**
- RMSE: **0.161**
- R² Score: **0.858**

The model explains approximately **85.8% of the variation** in restaurant ratings.

The most important rating-prediction features were:

1. Customer votes
2. Cost for two
3. Number of cuisines
4. Restaurant type
5. Location
6. Table-booking availability

Because the dataset can contain multiple listings for the same restaurant, future validation should use restaurant-name-based group splitting to confirm model generalization.

---

## 🧩 Restaurant Segmentation

Restaurant segmentation was performed using:

- K-Means clustering
- DBSCAN
- RobustScaler
- Elbow method
- Silhouette score
- PCA
- t-SNE

### K-Means Selection

The silhouette score was calculated for different values of `k`.

- Best number of clusters: **2**
- Best silhouette score: **0.346**

### Cluster Profiles

| Metric | Cluster 0 | Cluster 1 |
|---|---:|---:|
| Restaurant listings | 9,378 | 24,282 |
| Average rating | 3.97 | 3.54 |
| Average votes | 590.69 | 80.46 |
| Average cost | ₹957.74 | ₹385.51 |
| Median cost | ₹800 | ₹350 |
| Online-order rate | 66% | 58% |
| Table-booking rate | 38% | 1% |
| Average cuisine count | 3.65 | 1.98 |

### Cluster Interpretation

#### Cluster 0: Premium and High-Engagement Restaurants

These restaurants generally have:

- Higher ratings
- Higher customer engagement
- Higher average cost
- More cuisines
- Greater table-booking availability
- A stronger casual-dining presence

#### Cluster 1: Budget and Quick-Service Restaurants

These restaurants generally have:

- Lower average cost
- Lower customer engagement
- Limited table-booking facilities
- Fewer cuisines
- A stronger quick-bites presence
- Greater focus on affordability and convenience

---

## 📉 Dimensionality Reduction

### Principal Component Analysis

PCA was used to project the clustering features into two dimensions.

- The first two components explain approximately **71.43% of the total variance**.
- The PCA plot helps visualize separation between the restaurant segments.

### t-SNE

t-SNE was applied to a random sample of restaurants to visualize nonlinear cluster structure in two dimensions.

---

## 💼 Business Recommendations

### 1. Location Strategy

Before opening a restaurant, evaluate:

- Local demand
- Competition
- Cuisine saturation
- Customer spending capacity
- Nearby restaurant ratings
- Delivery demand

High-density areas offer strong demand but also greater competition.

### 2. Online Ordering Strategy

Restaurants should improve:

- Ordering convenience
- Digital menus
- Packaging quality
- Delivery speed
- Order accuracy
- Customer support

### 3. Table-Booking Strategy

Premium, buffet, pub, and casual-dining restaurants should consider table-booking systems to improve:

- Customer convenience
- Seating management
- Waiting-time reduction
- Capacity planning

### 4. Cuisine Strategy

Popular cuisines such as North Indian have strong demand but also high competition.

Restaurants should differentiate themselves using:

- Food quality
- Unique menu items
- Competitive pricing
- Better service
- Strong branding
- Specialized cuisine offerings

### 5. Pricing Strategy

Restaurants should not use one pricing strategy across the entire city.

Pricing should depend on:

- Target customers
- Location
- Restaurant type
- Cuisine
- Service quality
- Competitor prices

### 6. Customer-Engagement Strategy

Restaurants should:

- Encourage authentic customer reviews
- Respond quickly to complaints
- Maintain consistent food quality
- Improve customer service
- Track changes in ratings and votes

### 7. Segment-Specific Strategy

For premium restaurants:

- Focus on experience, service, reservations, loyalty, and reputation.

For budget restaurants:

- Focus on affordability, speed, delivery, efficiency, and repeat orders.

### 8. Responsible Model Use

Machine-learning models should support business decisions rather than completely replace human judgment.

Models should be monitored and retrained when new market data becomes available.

---

## 🧰 Technologies and Libraries

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Git
- GitHub

---

## 📁 Suggested Repository Structure

```text
ZOMATO-BANGALORE-RESTAURANT-DATA-SCIENCE-PROJECT/
│
├── Alfido_Tech_Zomato_Complete_Data_Science_Project.ipynb
├── zomato.csv
├── README.md
├── requirements.txt
│
├── images/
│   ├── classification_model_comparison.png
│   ├── regression_model_comparison.png
│   ├── feature_importance.png
│   └── restaurant_clusters.png
│
└── report/
    └── Zomato_Bangalore_Project_Report.pdf
```

Only include folders and files that actually exist in your repository.

---

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/KartikKachwahe/ZOMATO-BANGALORE-RESTAURANT-DATA-SCIENCE-PROJECT.git
```

### 2. Open the Project Folder

```bash
cd ZOMATO-BANGALORE-RESTAURANT-DATA-SCIENCE-PROJECT
```

### 3. Create a Virtual Environment

```bash
python -m venv .venv
```

### 4. Activate the Environment

For Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

For macOS or Linux:

```bash
source .venv/bin/activate
```

### 5. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

Alternatively, if `requirements.txt` is available:

```bash
pip install -r requirements.txt
```

### 6. Start Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
Alfido_Tech_Zomato_Complete_Data_Science_Project.ipynb
```

Then select:

```text
Kernel → Restart & Run All
```

Make sure `zomato.csv` is placed in the same folder as the notebook.

---

## 📦 Requirements

The `requirements.txt` file can contain:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
```

---

## ⚠️ Project Limitations

- The data represents a historical snapshot of Bangalore restaurants.
- Ratings and votes may change over time.
- Missing values can reduce the available training data.
- Correlation does not establish a cause-and-effect relationship.
- Multiple listings for the same restaurant may influence model performance.
- Geographic coordinates were not available for detailed map analysis.
- Restaurant predictions should be validated before real-world deployment.

---

## 🚀 Future Improvements

- Apply group-aware validation using restaurant names.
- Add SHAP-based model explanations.
- Compare XGBoost, LightGBM, and CatBoost models.
- Create a Streamlit prediction application.
- Add geographic maps using restaurant coordinates.
- Build an interactive Power BI or Tableau dashboard.
- Create a model deployment API using FastAPI.
- Retrain the models using recent Zomato data.

---

## ✅ Conclusion

This project demonstrates a complete data science workflow:

```text
Business Understanding
→ Data Validation
→ Data Cleaning
→ Exploratory Data Analysis
→ KPI Development
→ Feature Engineering
→ Classification
→ Regression
→ Cross-Validation
→ Hyperparameter Tuning
→ Feature Importance
→ Clustering
→ PCA and t-SNE
→ Business Insights
→ Recommendations
```

The project goes beyond simply training machine-learning models. It combines technical analysis with business understanding to support decisions related to restaurant pricing, location selection, service availability, customer engagement, marketing, and restaurant segmentation.

---

## 👨‍💻 Author

**Kartik Kachwahe**

B.Tech in Information Technology  
Aspiring Data Analyst and Data Scientist

- **GitHub:** [KartikKachwahe](https://github.com/KartikKachwahe)

---

⭐ If you found this project useful, consider giving the repository a star.
