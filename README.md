Spam detection is one of the most common text classification problems in Natural Language Processing.
This project demonstrates how machine learning models can automatically detect spam messages from normal (ham) ones using statistical text features.

The classifier is trained on a real-world dataset containing thousands of labeled messages and deployed as a lightweight model suitable for integration into messaging applications, email filters, or chat systems.

📊 Dataset

Dataset Name: spam.csv (Kaggle)

Description: Contains over 5,500 SMS messages labeled as spam or ham.

Columns:

label: The category of the message — either spam or ham.

message: The text content of the SMS.

Example Records:

label	message
ham	Hey there! How are you doing today?
spam	WINNER! You’ve been selected for a $1000 prize. Reply now!
🎯 Objective

To build a robust spam detection model using Naive Bayes algorithms and determine which variant performs best for SMS classification.
After evaluation, Multinomial Naive Bayes was selected due to its superior accuracy and suitability for word count–based text data.

🧩 Algorithms Compared
Algorithm	Description	Accuracy (Approx.)	Remarks
GaussianNB	Works well for continuous data	~88%	Not ideal for text features
BernoulliNB	Suitable for binary features	~94%	Good performance but slightly lower recall
MultinomialNB	Works best with word frequencies (BoW/TF-IDF)	~97–98%	✅ Best choice for text classification
⚙️ Approach
1. Data Preprocessing

Converted text to lowercase

Removed punctuation, numbers, and stopwords

Tokenized and stemmed words using NLTK

Encoded labels (spam → 1, ham → 0)

2. Feature Extraction

Used TF-IDF (Term Frequency–Inverse Document Frequency) vectorization to transform text into numeric form.

Each message becomes a feature vector representing word importance.

3. Model Training

Compared GaussianNB, BernoulliNB, and MultinomialNB using the same feature set.

Selected MultinomialNB as the final model for deployment.

4. Model Evaluation

Evaluated on unseen test data using:

Accuracy

Precision

Recall

F1-Score

Confusion Matrix

📈 Model Evaluation
Metric	MultinomialNB	BernoulliNB	GaussianNB
Accuracy	97.5%	94.1%	88.3%
Precision	0.98	0.95	0.89
Recall	0.97	0.92	0.86
F1-Score	0.975	0.935	0.875

✅ Multinomial Naive Bayes gives the most balanced and accurate results for SMS spam detection.
