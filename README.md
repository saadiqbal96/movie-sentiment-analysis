README.md 
# 🎬 Multilingual Movie Review Sentiment Analysis  
### Using Pandas, HuggingFace Transformers, and PyTorch  
Repository: https://github.com/saadiqbal96/movie-sentiment-analysis

---

## 📌 Project Overview

This project analyzes movie reviews written in **three different languages**:

- 🇬🇧 English  
- 🇫🇷 French  
- 🇪🇸 Spanish  

The goals of the project are to:

1. **Load and merge** data from three separate CSV files  
2. **Translate** all French and Spanish text into English using pretrained HuggingFace models  
3. **Analyze sentiment** of every movie review  
4. **Produce a final clean dataset** containing 30 movies and their classified sentiment

The project demonstrates modern NLP techniques such as **machine translation** and **sentiment classification** using state-of-the-art transformer models.

---

## 📂 Repository Structure



movie-sentiment-analysis/
│
├── data/
│ ├── movie_reviews_eng.csv
│ ├── movie_reviews_fr.csv
│ └── movie_reviews_sp.csv
│
├── notebook/
│ └── sentiment_analysis.ipynb
│
├── src/
│ └── project_functions.py (optional)
│
├── output/
│ └── final_movie_sentiment.csv
│
└── README.md


---

## 📥 Dataset Description

Each CSV file contains:

- **Title** → Title of the movie / TV series  
- **Year** → Release year  
- **Synopsis** → Short description of the movie  
- **Review** → User/critic review  
- **Original Language** → en / fr / sp  

Note: The French and Spanish files originally used different column names, which we normalized in preprocessing.

---

## 🧹 Step 1 — Data Preprocessing

A function `preprocess_data()`:

- Loads all three CSV files  
- Renames French and Spanish column names to match English schema  
- Combines them into one unified Pandas DataFrame  
- Ensures each row includes the original language label  

The result is a dataset containing **30 rows**, one for each movie.

---

## 🌍 Step 2 — Machine Translation

We translate **all French and Spanish text into English** using HuggingFace’s pretrained models:

- `Helsinki-NLP/opus-mt-fr-en` (French → English)
- `Helsinki-NLP/opus-mt-es-en` (Spanish → English)

We translate both:

- Review  
- Synopsis  

This ensures the entire dataset is in a single language before applying sentiment analysis.

---

## 🧠 Step 3 — Sentiment Analysis

We use a pretrained sentiment classification model:

- `distilbert-base-uncased-finetuned-sst-2-english`

Each translated review is classified as:

- **Positive**, or  
- **Negative**

A new column called **Sentiment** is added to the final DataFrame.

---

## 📤 Step 4 — Final Output

The completed dataset is exported as:



final_movie_sentiment.csv


It contains:

- Title  
- Year  
- English Synopsis  
- English Review  
- Original Language  
- Sentiment  

This file is included in the **output/** folder.

---

## 🧪 Technologies Used

- **Python**
- **Pandas** — Data loading, cleaning, merging  
- **HuggingFace Transformers** — Translation + sentiment analysis  
- **PyTorch** — Model inference backend  
- **Google Colab** — Interactive development environment  

---

## 🧠 Skills Demonstrated

✔ Data cleaning and preprocessing  
✔ Working with multilingual datasets  
✔ Neural machine translation (NMT)  
✔ Transformer-based sentiment analysis  
✔ End-to-end NLP workflow  
✔ Exporting reproducible results  

---

## 📘 How to Run the Project

1. Open the notebook in Google Colab:  


notebook/sentiment_analysis.ipynb


2. Run all cells in order  
3. The notebook will automatically:  
- Load the CSV files from this repository  
- Translate non-English text  
- Apply sentiment analysis  
- Generate the final CSV file  

4. Download the generated file using the final cell.

---

## 🎉 Conclusion

This project walks through a complete multilingual NLP pipeline by integrating:

- Data preprocessing  
- Neural machine translation  
- Transformer-based sentiment analysis  

The final result is a clean dataset of **30 movies**, all translated into English and labeled with sentiment polarity. This workflow is aligned with real-world industry practices in modern NLP.

---

## 🙌 Author

**Saad Iqbal**  
GitHub: https://github.com/saadiqbal96  
