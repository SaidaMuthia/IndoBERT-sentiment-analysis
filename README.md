Sentiment Analysis of Jakarta Public Transportation (MRT & Transjakarta) with IndoBERT

Project Overview
This repository contains a project designed to analyze user sentiments toward public transportation in Jakarta, specifically MRT Jakarta and Transjakarta, using a fine-tuned IndoBERT model. Data is collected from posts and comments on the social media platform X (Twitter) in Indonesian, covering the period from 2022 to April 2024. The workflow includes data crawling, text preprocessing, manual labeling, model training with transfer learning, and visualization using bar plots and word clouds.

Analyze user sentiments (positive, neutral, negative) toward MRT and Transjakarta based on X data.
Evaluate the performance of the fine-tuned IndoBERT model using metrics such as accuracy, precision, recall, and F1-score.
Compare IndoBERT's performance with traditional machine learning methods (e.g., Naive Bayes, SVM).

Requirements
Dependencies
Python: pandas, numpy, re, nltk, torch, transformers, indonlu, tqdm, seaborn, matplotlib, wordcloud
Node.js: Required for Tweet-Harvest (data crawling)
Others: Chromium Browser (for crawling)

Installation
Clone the repository:git clone https://github.com/SaidaMuthia/IndoBERT-sentiment-analysis.git
cd IndoBERT-sentiment-analysis

Install Python dependencies:pip install pandas numpy re nltk torch transformers indonlu tqdm seaborn matplotlib wordcloud

Install Node.js for Tweet-Harvest:sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
NODE_MAJOR=20 && echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list
sudo apt-get update
sudo apt-get install nodejs -y
npm install -g npm@10.5.2

Usage
Data Crawling:
Open Crawl_Data_Twitter.ipynb.
Insert your Twitter Auth Token and adjust keywords (e.g., "MRT", "Transjakarta").
Run the script to save data to MRT-TJ-fix.csv.

Data Preprocessing:
Run DataCleaningTugasAkhir.ipynb to clean data (remove URLs, hashtags, mentions) and normalize slang.
Use lowercase.ipynb to convert text to lowercase.

Sentiment Analysis:
Open SentimentAnalysisIndoNLU_IndoBERT.ipynb.
Ensure the dataset is ready, perform manual labeling (positive, neutral, negative), and train the model.
Check evaluation metrics (accuracy, precision, recall, F1-score).

Visualization:
Run the visualization section to generate:
A bar plot showing sentiment distribution (400 positive, 1200 neutral, 500 negative).
Word clouds for each sentiment category.

Troubleshooting: If the notebook encounters errors (e.g., "invalid notebook"), verify all dependencies are installed and run cells sequentially to identify issues.
Results

Dataset: 2,086 tweets (2022-April 2024), split into 90% training and 10% testing/validation.
Model Performance:
Training: Accuracy reached 100% by epoch 13 (recall, precision, F1-score: 100%).
Validation: Accuracy 76%, recall 56%, precision 63%, F1-score 58% (indicating potential overfitting).

Visualization:
Bar plot reflects sentiment distribution.
Word clouds highlight frequent terms like "moda raya" (MRT/Transjakarta).



