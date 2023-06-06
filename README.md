# Mortgage Question Classification Chatbot

This is a chatbot designed to classify questions from customers in the mortgage category. It utilizes various machine learning algorithms to predict the category of a given question. The chatbot can be connected to any of the provided prediction models, which include:

- Logistic Regression
- Support Vector Machine (SVM)
- Decision Tree
- Random Forest
- Own Model using TF-IDF
- Embeddings using PALM AI from BARD
- Embeddings using ChatGPT

## Prerequisites

- Docker
- Docker Compose

## Installation

1. Clone the repository:

```bash
git clone <https://github.com/IT-Guy007/Stater-text-classification.git>
cd mortgage-chatbot
```

2. Start the chatbot using Docker Compose:

```bash
docker-compose up
```

2. Start the styling pf the chatbot using tailwind:

```bash
docker-compose run web python manage.py tailwind start
```

## Usage

Once the chatbot is up and running, you can interact with it using a web interface. Open your browser and visit `http://localhost:8000` to access the chatbot.

The chatbot has two commands that can be used:

1. `docker-compose up`: Starts the chatbot service.
2. `docker-compose run web python manage.py tailwind start`: Runs the Tailwind CSS compiler for styling the chatbot interface.

## Screenshot

![Chatbot Screenshot](https://i.imgur.com/8irzTN5.png)

The screenshot provides a visual representation of the chatbot interface. Users can input their questions, and the chatbot will classify them based on the selected prediction model.

Feel free to explore the chatbot, connect different prediction models, and interact with it to classify mortgage-related questions from customers.

## Prediction Models

### 1. Logistic Regression

Logistic Regression is a classification algorithm that is commonly used when the dependent variable is categorical. It calculates the probability of a sample belonging to a particular class using a logistic function.

### 2. Support Vector Machine (SVM)

Support Vector Machine is a powerful algorithm used for both classification and regression tasks. It maps input data to a high-dimensional feature space and tries to find a hyperplane that maximally separates the data points of different classes.

### 3. Decision Tree

Decision Tree is a popular algorithm that builds a tree-like model for decisions. It partitions the data into subsets based on different attributes and selects the best attribute at each step to build the tree.

### 4. Random Forest

Random Forest is an ensemble learning method that combines multiple decision trees to improve predictive accuracy. It generates a multitude of decision trees and outputs the class that is the mode of the classes predicted by individual trees.

### 5. Own Model using TF-IDF

This model uses the TF-IDF (Term Frequency-Inverse Document Frequency) representation for text classification. It calculates the importance of a word in a document by considering its frequency in the document and across the entire corpus. Then it selects the top 3 most important words and compares them to the 100.000 train rows, to predict an right category.

### 6. Embeddings using PALM AI from BARD

This model utilizes embeddings generated by the PALM AI model from BARD (Biologically inspired Attentive Recurrent Dynamics). Embeddings are dense vector representations of words or sentences that capture semantic information.

### 7. Embeddings using ChatGPT

This model employs embeddings generated by ChatGPT, a powerful language model developed by OpenAI. The embeddings capture contextual information and can be used for various natural language processing tasks, including text classification.

# Text Classifier

This code provides a text classification model using a TF-IDF (Term Frequency-Inverse Document Frequency) approach. The model is trained on a dataset of consumer complaints and predicts the category of a given input text based on its content.

## Prerequisites

Make sure you have the following dependencies installed:

- pandas
- numpy
- scikit-learn (sklearn)
- nltk

You also need to download the English words corpus from NLTK by running the following command:

```python
import nltk
nltk.download('words')```

## Installation
Clone the repository or download the code files.
Install the required dependencies mentioned in the Prerequisites section.

## Usage
Prepare your training data in a CSV format with the following columns: 'Date received', 'Product', 'Sub-product', 'Issue', 'Sub-issue', 'Consumer complaint narrative', 'Company public response', 'Company', 'State', 'ZIP code', 'Tags', 'Consumer consent provided?', 'Submitted via', 'Date sent to company', 'Company response to consumer', 'Timely response?', 'Consumer disputed?', 'Complaint ID'.
Replace the file path in the line DS1_data = pd.read_csv("TrainData.csv", low_memory=False, dtype=dtypes, parse_dates=parse_dates) with the path to your training data file.
Run the code.

##Performance
The model achieved an accuracy of approximately 69% on a test dataset of 1000 samples. The results are printed as follows:

Correct predictions: [CorrectPrognosed]%.
Incorrect predictions: [WrongPrognosed]%.
