Capstone Project Report: Movie Sentiment Analysis
By: Abdulaziz Yasser Allwaiheq

1. Introduction
For this project, I chose the IMDb Movie Reviews dataset. I’ve always been interested in how computers can "read" human emotions, and building a sentiment classifier felt like the best way to apply the NLP and Deep Learning skills we learned over the last 10 weeks. My goal was to create a pipeline that could accurately predict if a review was positive or negative.

2. Dataset Description
The dataset contains 50,000 movie reviews. Each review is labeled as either "positive" or "negative." After loading the data with Pandas, I found that there were no missing values. The dataset is perfectly balanced, with 25,000 positive reviews and 25,000 negative reviews, which made training much easier because I didn't have to worry about class weight adjustments.

3. Models Used
I trained three traditional machine learning models:
Logistic Regression: Achieved the best performance among ML models with an F1-score of around 0.89.
Random Forest: Performed well but was prone to overfitting and much slower to train.
Naive Bayes: Very fast and decent results, but slightly lower accuracy than Logistic Regression.
Overall, Logistic Regression was the strongest ML model because it handles high-dimensional sparse data (like TF-IDF vectors) very effectively.

4. Neural Network
My neural network consisted of an input layer for the 5,000 TF-IDF features, followed by a Dense layer with 128 neurons (ReLU), a 50% Dropout layer to prevent overfitting, another Dense layer with 64 neurons, and finally a Sigmoid output layer for binary classification. I trained it for 10 epochs using the Adam optimizer. The validation curves showed that the model learned quickly, though I had to be careful with the Dropout rate to keep the validation loss from rising.

5. Results & Comparison
The Neural Network performed very well, reaching an accuracy of about 88-89%. However, when comparing it to the traditional models, it was only marginally better than Logistic Regression. In fact, for a dataset of this size using TF-IDF, the extra computational time for a Neural Network might not always be necessary, though it offers more flexibility for future improvements like word embeddings.

6. What I Learned
The biggest lesson I learned is that data cleaning is just as important as the model itself. Removing stopwords and punctuation significantly reduced the "noise" in the data. I also learned that "more complex" doesn't always mean "much better"—sometimes a simple, well-tuned model like Logistic Regression is incredibly hard to beat.
