# 📱 Sentiment Analysis on YouTube App Reviews

This project focuses on analyzing and classifying user reviews of the **YouTube app** on the **Google Play Store** using machine learning techniques. The goal is to build a text classification model that can automatically determine whether a review is **positive** or **negative**.

---

## 🧩 Project Structure
```bash 
  youtube-app-sentiment-analysis/
  ├── data/
  │ └── raw/
  │ └── com.google.android.youtube_reviews.csv # Scraped dataset
  ├── notebooks/
  │ └── sentiment_analysis_youtube_reviews.ipynb # Full analysis & modeling
  ├── src/
  │ └── scrape_reviews.py # Google Play scraping script
  ├── requirements.txt # Python dependencies
  └── README.md # Project documentation
```
---

## 📥 Data Collection

The data was collected using the [`google-play-scraper`](https://pypi.org/project/google-play-scraper/) Python library.  
The script [`src/scrape_reviews.py`](src/scrape_reviews.py) collects up to 12,000 most relevant user reviews for the YouTube app in Indonesian (`lang='id'`, `country='id'`) and saves them into a CSV file.

---

## 🧪 Sentiment Analysis Pipeline

### 🔄 Preprocessing
- Lowercased all text
- Removed punctuation, special characters, and numbers
- Tokenized and cleaned using Indonesian stopwords
- Applied stemming using [`Sastrawi`](https://github.com/har07/PySastrawi)

### 📊 Exploratory Data Analysis (EDA)
- Plotted sentiment label distribution
- Visualized review length
- Generated word clouds for each sentiment

### 🔧 Feature Extraction
- TF-IDF Vectorizer was used to convert text into numerical feature vectors

### 🤖 Modeling
- Model used: **Logistic Regression**
- Dataset split: 80% training, 20% testing
- Evaluation:
  - **Accuracy**: ~90%
  - **Precision / Recall / F1-score**: high performance on both classes
  - **Confusion Matrix**: visualized to evaluate misclassifications

---

## 📌 Results Snapshot

| Metric     | Value      |
|------------|------------|
| Accuracy   | ~90%       |
| Precision  | High       |
| Recall     | High       |
| F1-Score   | High       |

> See detailed results in the notebook: [`notebooks/sentiment_analysis_youtube_reviews.ipynb`](notebooks/sentiment_analysis_youtube_reviews.ipynb)

---

## 🛠️ Tech Stack

- Python
- Pandas, NumPy
- Matplotlib, Seaborn, WordCloud
- Scikit-learn
- Sastrawi (Indonesian NLP)
- Google Play Scraper

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/gimnastiarhrn/youtube-app-sentiment-analysis.git
   cd youtube-app-sentiment-analysis
    ```
2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3. Run the notebook:
    ```
    notebooks/sentiment_analysis_youtube_reviews.ipynb
    ```
4. (Optional) To re-scrape reviews:
    ```bash
    python src/scrape_reviews.py
    ```

---

## 👤 Author

Gymnastiar Harun
📧 gimnastiarhrn@gmail.com
🔗 LinkedIn [www.linkedin.com/in/gymnastiarharun]

## 📄 License
This project is open source and available under the MIT License.
