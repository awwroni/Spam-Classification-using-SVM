SMS Spam Classification using SVM
This repository contains a Jupyter Notebook that implements an SMS Spam Classifier using a Support Vector Machine (SVM) model. The project aims to accurately identify and classify SMS messages as either 'ham' (legitimate) or 'spam' based on their textual content.

Table of Contents
Dataset
Project Overview
Key Steps
Results
Usage
Dependencies
Dataset
The dataset used for this project is the SMS Spam Collection Dataset from Kaggle.

Source: Kaggle - SMS Spam Collection Dataset
This dataset comprises a collection of SMS messages tagged as either 'ham' or 'spam'.

Project Overview
The goal of this project is to build a robust model capable of classifying SMS messages. The process involves:

Data Loading: Importing the dataset into a pandas DataFrame.
Exploratory Data Analysis (EDA): Understanding the distribution of messages, character counts, and word counts for both ham and spam categories.
Text Preprocessing: Cleaning the text data by removing punctuation, numbers, URLs, email addresses, converting to lowercase, removing stopwords, and lemmatizing words.
Feature Extraction: Converting text data into numerical features using TF-IDF (Term Frequency-Inverse Document Frequency).
Model Training: Training a Linear Support Vector Classifier (LinearSVC) on the processed data.
Hyperparameter Tuning: Optimizing model parameters using GridSearchCV.
Cross-Validation: Evaluating model performance using cross-validation to ensure robustness.
Prediction Function: A simple function to predict whether a new SMS message is spam or ham.
Key Steps
1. Data Loading and Initial Inspection
The spam.csv file is loaded, unnecessary columns are dropped, and columns are renamed for clarity. Basic checks for shape, info, null values, and duplicates are performed.

2. Exploratory Data Analysis (EDA)
Creation of char_count and word_count features.
Visualization of label distribution, word count distribution for ham vs. spam.
Word cloud generation for both spam and ham messages to highlight common words.
Correlation Heatmap: Visualizing correlations between numerical features (char_count, word_count) and the label.
Distribution of Message Lengths: Histograms showing character and word count distributions for ham and spam to identify patterns.
3. Preprocessing
Definition of clean_text function to standardize messages.
Removal of duplicate messages.
Application of clean_text to create a clean_message column.
Conversion of 'label' column ('ham'/'spam') to numerical (0/1).
4. Train/Test Split
The dataset is split into training and testing sets (80% train, 20% test) using stratify=y to maintain the proportion of ham/spam messages.

5. SVM Model
A Pipeline is used to combine TfidfVectorizer (with max_features=5000 and ngram_range=(1,2)) and LinearSVC. The model is trained and evaluated using accuracy, precision, recall, F1-score, and a classification report.

6. Hyperparameter Tuning
GridSearchCV is employed to find the best C parameter for the LinearSVC within the pipeline.

7. Cross Validation
Cross-validation is performed using the best estimator found during hyperparameter tuning to assess the model's generalized performance.

8. Prediction Function
A predict_sms function is provided to allow users to input a custom text message and receive a 'Spam' or 'Ham' classification.

Results
The model demonstrates high accuracy, precision, recall, and F1-score in classifying SMS messages, indicating its effectiveness in distinguishing between ham and spam.

Usage
Download the Dataset: Obtain spam.csv from the Kaggle link provided above.
Upload to Colab: Upload the spam.csv file to your Colab environment.
Run the Notebook: Execute the cells sequentially.
Test the Model: Use the predict_sms function to test custom messages.
Dependencies
The project relies on the following Python libraries:

pandas
numpy
matplotlib
seaborn
wordcloud
nltk
scikit-learn
These can be installed using pip:

pip install pandas numpy matplotlib seaborn wordcloud nltk scikit-learn
NLTK stopwords and wordnet data also need to be downloaded, which is handled in the notebook.

