Zomato Bangalore Restaurant Data Science Project

An end-to-end data science project developed as part of the Alfido Tech Data Science Internship. It analyzes Bangalore restaurant data to identify market trends, customer preferences, pricing patterns, and restaurant segments, while applying classification, regression, clustering, and dimensionality-reduction techniques.

Project Links

GitHub Repository: Zomato Bangalore Restaurant Data Science Project

Complete Notebook: View Jupyter Notebook

Project Objectives

Clean and validate the raw Zomato restaurant data.

Analyze restaurant locations, types, cuisines, ratings, costs, and customer votes.

Measure the availability and effect of online ordering and table booking.

Build a classification model to predict whether a restaurant is expensive.

Build regression models to predict restaurant ratings.

Segment restaurants into meaningful groups using clustering.

Convert analytical results into practical business recommendations.

Dataset Description

The raw dataset contains 56,252 rows and 13 columns representing restaurants listed on Zomato in Bangalore.

Feature

Description

name

Restaurant name

address

Restaurant address

location

Area in Bangalore

online_order

Availability of online ordering

book_table

Availability of table booking

rate

Restaurant rating

votes

Number of customer votes

phone

Contact information

rest_type

Restaurant category/type

dish_liked

Popular dishes

cuisines

Cuisines offered

approx_cost(for two people)

Estimated cost for two people

listed_in(type)

Zomato listing category

Project Workflow

Business understanding and objective definition

Data loading and structural validation

Missing-value, duplicate, and malformed-record analysis

Data cleaning and type conversion

KPI calculation

Exploratory data analysis

Feature engineering

Classification model training and comparison

Regression model training and comparison

Cross-validation and hyperparameter tuning

Feature-importance analysis

K-Means and DBSCAN clustering

PCA and t-SNE visualization

Business insights and recommendations

Data Cleaning and Preprocessing

Detected 15,703 exact duplicate rows in the raw data.

Removed structurally malformed records using valid domains for online ordering, table booking, and listing type.

Removed duplicates after structural validation.

Converted ratings such as 4.1/5 into numeric values.

Removed commas and converted approximate cost into a numeric field.

Converted votes into numeric format.

Handled missing numerical and categorical values inside machine-learning pipelines.

Excluded high-cardinality reference fields, such as phone and address, from primary model features.

Used one-hot encoding for categorical variables and appropriate scaling for numerical variables.

The final analytical dataset contains 33,660 clean restaurant listings, 8,641 unique restaurant names, and 93 locations.

Exploratory Data Analysis

The notebook examines:

Rating, vote, and cost distributions

Top restaurant locations, types, and cuisines

Online-order and table-booking availability

Rating differences across service options

Relationships among rating, cost, votes, and cuisine count

Outliers and numerical correlations

Market concentration across Bangalore locations

Key Performance Indicators

KPI

Result

Clean restaurant listings

33,660

Unique restaurant names

8,641

Locations represented

93

Valid rated records

28,133

Average rating

3.68/5

Median rating

3.70/5

Average cost for two

₹545.49

Median cost for two

₹400

Average votes

222.62

Median votes

44

Online ordering available

60.21%

Table booking available

11.58%

Key Insights

BTM has the highest restaurant concentration, with 2,781 listings.

Quick Bites is the most common restaurant type, with 12,691 listings.

North Indian is the most frequently represented cuisine, appearing 13,912 times.

Delivery is the most common listing category.

Restaurants offering online ordering have a slightly higher average rating (3.705) than those without it (3.629).

Restaurants offering table booking have a considerably higher average rating (4.078) than those without it (3.617).

Rating has a moderate positive relationship with votes (0.399) and cost (0.334). These correlations represent association, not causation.

Feature Engineering

The notebook creates useful model features, including:

Clean numeric rating

Clean numeric cost for two

Numeric vote count

Number of cuisines offered

Online-order binary flag

Table-booking binary flag

Expensive-restaurant target based on the median cost

Log-transformed vote count for clustering

Classification: Expensive Restaurant Prediction

The classification task predicts whether a restaurant belongs to the expensive category. The data is divided into an 80% training set and 20% test set, using stratification to preserve the target distribution.

Models compared:

Logistic Regression

Decision Tree

Random Forest

Gradient Boosting

K-Nearest Neighbors

Support Vector Machine

Best Classification Result

Random Forest produced the strongest test performance:

Metric

Score

Accuracy

0.928

Precision

0.950

Recall

0.897

F1 Score

0.923

ROC-AUC

0.972

Randomized hyperparameter search produced a best cross-validation F1 score of 0.8939. The most influential classification features included vote count, restaurant type, rating, cuisine count, and table-booking availability.

Regression: Restaurant Rating Prediction

The regression task estimates a restaurant's rating. The following models were evaluated:

Linear Regression

Ridge Regression

Lasso Regression

Elastic Net

Decision Tree Regressor

Random Forest Regressor

Gradient Boosting Regressor

Extra Trees Regressor

Best Regression Result

Extra Trees Regressor achieved the best test performance:

Metric

Score

MAE

0.065

RMSE

0.161

R² Score

0.858

Vote count was the most influential rating-prediction feature, followed by cost for two and cuisine count. Because repeated restaurant listings may carry similar information, these strong test results should be confirmed with group-aware validation before production use.

Restaurant Segmentation

K-Means clustering was evaluated using the elbow method and silhouette score. The best silhouette result selected two clusters.

Segment

Listings

Avg. Rating

Avg. Votes

Avg. Cost

Table Booking

Interpretation

Cluster 0

9,378

3.97

590.69

₹957.74

38%

Higher-engagement, premium dine-in restaurants

Cluster 1

24,282

3.54

80.46

₹385.51

1%

Budget and quick-service restaurants

The best K-Means silhouette score was 0.346 at k = 2.

PCA's first two components explained approximately 71.43% of the variance.

DBSCAN was also tested on a sample to explore density-based groups and noise points.

t-SNE was used to visualize cluster structure in two dimensions.

Business Recommendations

Evaluate location demand, competition, cuisine saturation, and price positioning before opening a new restaurant.

Strengthen online ordering, delivery reliability, packaging, and digital menus because online ordering is widely available.

Use table-booking systems for premium, buffet, pub, and casual-dining formats where customer planning matters.

Differentiate popular cuisines through quality, price, menu design, service, or a specialized offering.

Use location- and segment-specific pricing instead of applying one pricing strategy across Bangalore.

Encourage authentic reviews and improve complaint resolution because votes and ratings are important engagement signals.

Use separate marketing and operating strategies for premium dine-in and budget quick-service segments.

Treat model predictions as decision-support inputs and validate them regularly with new data.

Technologies Used

Python

Jupyter Notebook

Pandas and NumPy

Matplotlib and Seaborn

Scikit-learn

Git and GitHub

How to Run the Project

Clone the repository:

git clone https://github.com/KartikKachwahe/ZOMATO-BANGALORE-RESTAURANT-DATA-SCIENCE-PROJECT.git
cd ZOMATO-BANGALORE-RESTAURANT-DATA-SCIENCE-PROJECT

Create and activate a virtual environment:

python -m venv .venv

Windows PowerShell:

.\.venv\Scripts\Activate.ps1

macOS/Linux:

source .venv/bin/activate

Install the required packages:

pip install pandas numpy matplotlib seaborn scikit-learn jupyter

Ensure that zomato.csv is in the same folder as the notebook.

Start Jupyter Notebook:

jupyter notebook

Open Alfido_Tech_Zomato_Complete_Data_Science_Project.ipynb and select Kernel → Restart & Run All.

Suggested Repository Structure

ZOMATO-BANGALORE-RESTAURANT-DATA-SCIENCE-PROJECT/
├── Alfido_Tech_Zomato_Complete_Data_Science_Project.ipynb
├── zomato.csv
├── README.md
├── requirements.txt
├── images/
│   ├── classification_model_comparison.png
│   ├── regression_model_comparison.png
│   └── restaurant_clusters.png
└── report/
    └── Zomato_Bangalore_Project_Report.pdf

Limitations and Future Improvements

Confirm model generalization using group-aware splitting by restaurant name to reduce leakage from repeated listings.

Add explainability using SHAP values.

Test advanced models such as XGBoost, LightGBM, or CatBoost.

Deploy the trained models through a Streamlit application.

Add geographic coordinates for map-based location analysis.

Re-train the models on recent restaurant-market data.

Conclusion

This project demonstrates a complete data science lifecycle: business understanding, data validation, cleaning, exploratory analysis, KPI development, feature engineering, supervised learning, hyperparameter tuning, feature importance, clustering, dimensionality reduction, and business interpretation. It shows how restaurant data can support pricing, service, location, marketing, and customer-experience decisions.

Author

Kartik Kachwahe
B.Tech in Information Technology
Aspiring Data Analyst / Data Scientist
