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

## 📌 **Experiment Results**

## 📑 **References**
