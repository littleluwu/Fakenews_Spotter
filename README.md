# 📰 **Spotting Fake News with Python**

This project aims to investigate the task of spotting fake news and apply classic and modern machine learning techniques to develop a model that can classify news as real or fake. It is part of an assignment for the course `486205 - APRENDIZADO DE MÁQUINA` at the **Federal University of São Carlos (UFSCar)**, lectured by the professor **Tiago A. Almeida**.

The data we are using in this project was provided by the professor for use in the assignment. It compiles news automatically collected during 2019 and 2020 with no supervision. This indicates the possibility of data corruption or information loss during the collection phase. A given news presented in the dataset can be classified in a binary way:

- **1** -> The news is <span style="color:LightGreen">trustworthy</span> (Real).
- **0** -> The news is <span style="color:Tomato">not trustworthy</span> (Possibly Fake).

However, it wasn't possible to check if the information was reliable in a large amount of samples. Thus, these news articles do not exhibit any label attached to them. The data is organized by month and year in separate CSV files, which include a unique identification for each article, both the titles and contents, the date when the article written and the binary label attached to them. To work with this data, we imported each file and compiled them in a single data frame.

## 🧪 **Data Analysis and Preprocessing**

We examined news content and observed many unannotated articles in this massive dataset. Analysis revealed about $1\%$ of articles missing titles/content and approximately $50\%$ lacking classification labels. We excluded unlabeled articles from our analysis.

Our exploratory analysis showed an imbalanced dataset with nearly $80\%$ <span style="color:Tomato">fake news articles </span> versus <span style="color:LightGreen">trustworthy ones</span>. This imbalance was considered during model training.

To prepare the data for machine learning, we transformed news articles into computer-friendly representations. We cleaned the text by removing digits, punctuation, and short words (≤3 characters), then tokenized articles into term-document matrices. We used TF-IDF for data representation and implemented lemmatization to reduce dimensionality. Titles and content were processed separately and merged with identifying suffixes.

## 🤖 **Machine Learning Approaches**

We tested multiple machine-learning approaches to detecting fake news, from classical ones like K-Nearest Neighbors to more sophisticated ones using shallow Neural Networks and Random Decision Trees. We first split the processed data into two sets: a training set and a testing set for comparing the different methods. For the trained models' accuracy, we used the ROC AUC Score metric to compute the similarity of the predicted labels with the actual labels of the articles

- **K-Nearest Neighbors (KNN)**: KNN is a simple and intuitive algorithm. It classifies a new data point based on the majority class of its k nearest neighbors.

- **Nayve Bayes**: Naive Bayes is a probabilistic algorithm that assumes that the features are independent of each other. It is a simple and effective algorithm for classification tasks.

- **Linear Regression**: Linear Regression is a statistical method for modeling the relationship between a dependent variable and one or more independent variables.

- **Logistic Regression**: Logistic Regression is a statistical method for predicting binary outcomes. It models the probability of an event occurring between 0 and 1.

- **Neural Networks**: Neural Networks are a powerful tool for classification tasks. They can learn complex patterns in the data by simulating the structure and function of the human brain.

- **Support Vector Machine (SVM)**: SVM is a powerful algorithm that finds the best hyperplane to separate data points.

- **Random Forest**: Random Forest is an ensemble learning method that builds multiple decision trees and combines their predictions.

## 📌 **Experiment Results**

| Model               | Accuracy on Training Set | Accuracy on Testing Set |
| ------------------- | ------------------------ | ----------------------- |
| KNN                 | 71.77%                   | 60.27%                  |
| Nayve Bayes         | 72.28%                   | 67.74%                  |
| Linear Regression   | 90.77%                   | 79.16%                  |
| Logistic Regression | 77.68%                   | 71.17%                  |
| Neural Networks     | 99.95%                   | 69.38%                  |
| SVM Linear          | -%                       | -%                      |
| SVM Non Linear      | -%                       | -%                      |
| Random Forest       | 96.05%                   | 63.40%                  |

## 📑 **References**

SHU, Kai et al. Fake news detection on social media: A data mining perspective. ACM SIGKDD explorations newsletter, v. 19, n. 1, p. 22-36, 2017.

JAIN, Akshay; KASBE, Amey. Fake news detection. In: 2018 IEEE International Students' Conference on Electrical, Electronics and Computer Science (SCEECS). IEEE, 2018. p. 1-5.

BEKKAR, Mohamed; DJEMAA, Hassiba Kheliouane; ALITOUCHE, Taklit Akrouf. Evaluation measures for models assessment over imbalanced data sets. J Inf Eng Appl, v. 3, n. 10, 2013.
