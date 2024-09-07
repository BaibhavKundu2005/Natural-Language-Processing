# Yelp Review Classification Using Natural Language Processing (NLP)

This project focuses on classifying Yelp reviews based on their star ratings using Natural Language Processing (NLP) techniques. The primary objective is to build models that can predict whether a review is positive (5 stars) or negative (1 star) by analyzing the text content of the review.

## Overview

The project involves working with a dataset of Yelp reviews, performing exploratory data analysis, preprocessing text data, and building classification models using machine learning techniques. The goal is to classify reviews as either 1-star or 5-star reviews based on their content.

## Key Steps

1. **Data Collection**: 
   - The dataset consists of 10,000 Yelp reviews, each with several attributes like `business_id`, `date`, `review_id`, `stars`, `text`, and user interactions such as `cool`, `useful`, and `funny`.
   - The text of the reviews serves as the main feature, and the star rating (1 or 5) is the target label.

2. **Data Preprocessing**:
   - The dataset was explored to understand its structure and content, and a new column for the length of the review text was created to analyze its correlation with star ratings.
   - Data visualizations such as histograms, box plots, and count plots were generated to show the distribution of review lengths and star ratings.

3. **Feature Extraction**:
   - Only reviews with 1 or 5 stars were selected for binary classification.
   - The text of the reviews was converted into numerical features using the **CountVectorizer**, which converts text into a matrix of token counts.

4. **Model Training - Naive Bayes**:
   - The dataset was split into training and testing sets.
   - A **Multinomial Naive Bayes** model was trained on the vectorized review text data.
   - The model was evaluated using accuracy, precision, recall, and F1-score. The results showed that the Naive Bayes model performed well, with high accuracy in predicting 1-star and 5-star reviews.

5. **Pipeline and TF-IDF**:
   - A **Pipeline** was implemented to streamline the process of text vectorization and model training.
   - The pipeline included both **CountVectorizer** and **TfidfTransformer** to convert the text data into a TF-IDF matrix.
   - However, using TF-IDF with Naive Bayes worsened the performance, resulting in lower precision and recall for 1-star reviews.

6. **Model Improvement - Random Forest**:
   - To improve performance, a **Random Forest Classifier** was incorporated into the pipeline as an alternative to Naive Bayes.
   - The Random Forest model performed better, especially in predicting the minority class (1-star reviews), with a higher recall for these reviews compared to Naive Bayes.

## Insights

- **Naive Bayes**: The Multinomial Naive Bayes model provided good accuracy, particularly for predicting 5-star reviews. However, it struggled with 1-star reviews, especially after using TF-IDF transformation.
- **Random Forest**: Implementing a Random Forest Classifier improved the model’s ability to predict 1-star reviews, achieving a better balance between precision and recall.
- **Text Length**: Visualizations indicated that longer reviews tended to be associated with higher star ratings, although no definitive conclusion was drawn from this relationship.

## Conclusion

This project successfully demonstrated how NLP techniques can be applied to classify Yelp reviews based on their star ratings. While the Naive Bayes model showed strong performance initially, switching to a Random Forest Classifier provided more balanced and accurate predictions, especially for minority classes. The use of pipelines also simplified the workflow, making it easier to apply different models and transformations.
