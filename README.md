# Amazon Electronics Product Reviews Analysis

## Introduction
The goal of this project is to develop a predictive model for user ratings and evaluate the usefulness of reviews in recommending relevant items to users. By leveraging collaborative filtering techniques, the objective is to personalize the user experience with tailored recommendations based on past interactions and preferences.

## Dataset
- Source: Amazon Reviews Dataset (5-core, Electronics)
- The dataset includes user reviews, ratings, and product metadata.
- Product metadata is separated into a dedicated dataframe for additional context.

## Product Selection
- Focused on the 'Headphones' category for all analysis and modeling tasks.

## Data Preprocessing
- Handled missing values, duplicate entries, and inconsistencies.
- Cleaned text data by removing:
  - HTML tags
  - Accented characters
  - Acronyms and special characters
  - Performed lemmatization and text normalization

## Descriptive Statistics
- Total number of reviews computed for the selected product category.
- Calculated:
  - Average rating score
  - Number of unique products
- Ratings classified as:
  - Good (>= 3)
  - Bad (< 3)
- Analyzed the distribution of ratings and count per rating category.

## Exploratory Data Analysis (EDA)
- Identified:
  - Top 20 most and least reviewed brands
  - Most positively reviewed product in 'Headphones'
- Analyzed:
  - Annual rating trends across 5 consecutive years
  - Common words using Word Clouds for 'Good' and 'Bad' ratings
  - Rating distribution using pie charts
  - Years with highest review and customer counts

## Feature Engineering
- Transformed review text using the following vectorization techniques:
  - Bag of Words
  - TF-IDF
  - Hashing Vectorizer
  - Word2Vec

## Machine Learning Models
- Split dataset into training and testing sets (75:25 ratio)
- Evaluated 5 ML models on multi-class classification (Good, Average, Bad) using:
  - Precision
  - Recall
  - F1-score
  - Support

### Model Performance Summary (based on `classification_report.txt`)

| Model                 | Accuracy | Good Class F1-Score |
|----------------------|----------|---------------------|
| Logistic Regression  | 85%      | 0.92                |
| Decision Tree        | 76%      | 0.87                |
| Random Forest        | 81%      | 0.89                |
| K-Nearest Neighbors  | 78%      | 0.88                |


## Collaborative Filtering
- Created a user-item rating matrix and applied Min-Max normalization.
- Developed:
  - **User-User Recommender**
    - Used cosine similarity for top N similar users (N = 10, 20, 30, 40, 50)
    - Implemented 5-fold cross-validation
    - MAE calculated for each K
  - **Item-Item Recommender**
    - Followed a similar approach to user-user
- Plotted MAE vs K for both systems.

## Top 10 Products by User Sum Ratings
- Listed the top 10 products based on the aggregate of user ratings.
