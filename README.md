Sentiment Analysis 

Overview
This project demonstrates sentiment analysis using a Multinomial Naive Bayes classifier on a dataset of comments. The goal is to classify comments into positive, negative, or neutral sentiments based on their content.

 Dataset
The dataset used (`Comments.csv`) contains comments with associated sentiment labels.

Steps Performed:
1. Data Preprocessing:
   - Loaded the dataset using Pandas.
   - Handled missing values and class imbalance by sampling equal numbers of instances from each sentiment class.

2. Exploratory Data Analysis:
   - Visualized the distribution of sentiments before and after balancing.
   - Created a word cloud to visualize frequently occurring words in the comments.

3. Text Preprocessing:
   - Cleaned the comments by removing stopwords, punctuation, and lemmatizing the text using spaCy.

4. Feature Extraction:
   - Used spaCy's pretrained model (`en_core_web_lg`) to convert cleaned text into numerical vectors.

5. Model Training:
   - Split the data into training and testing sets.
   - Applied MinMax scaling to the numerical vectors.
   - Trained a Multinomial Naive Bayes classifier on the scaled training data.

6. Model Evaluation:
   - Evaluated the model using classification metrics such as precision, recall, and F1-score.
   - Plotted a confusion matrix and visualized the true vs predicted sentiment distributions.

7. Model Persistence:
   - Saved the trained classifier using joblib (`model.joblib`).

Requirements
- Python 3
- Libraries: pandas, matplotlib, seaborn, wordcloud, spacy, sklearn

Usage
1. Clone the repository:
   ```
   git clone https://github.com/your-username/sentiment-analysis.git
   cd sentiment-analysis
   ```
   
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
   
3. Run the notebook or script to reproduce the analysis:
   ```
   jupyter notebook SentimentAnalysis.ipynb
   ```
   
4. Modify paths or parameters as needed for your dataset or environment.

 Files Included
- `SentimentAnalysis.ipynb`: Jupyter notebook containing the complete analysis workflow.
- `Comments.csv`: Dataset file containing comments and sentiment labels.
- `model.joblib`: Pre-trained Multinomial Naive Bayes classifier saved for reuse.

