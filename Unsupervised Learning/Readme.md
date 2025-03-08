# Topic Modeling of Survey Responses: Unsupervised Learning With LDA

## Author: Christian Lira Gonzalez  
## Summer 2023  

## Project Overview
This project applies **Latent Dirichlet Allocation (LDA)** to extract topics from open-ended survey responses. Additionally, **sentiment analysis** and **statistical validation** are performed to assess model stability across multiple simulations.

The main objectives include:
- Automating **topic extraction** from survey responses.
- Performing **sentiment analysis** using **VADER**.
- Evaluating **topic coherence** through **multiple simulations**.
- Conducting **hypothesis testing** to validate model robustness.
- Visualizing **topic distributions, sentiment trends, and statistical measures**.

By leveraging **unsupervised learning**, this project improves the efficiency of survey analysis and enhances decision-making based on textual data.

---

## Project Structure
```
/Topic-Modeling-LDA/
│── data/                  # Folder for input survey dataset (CSV format)
│── notebooks/             # Jupyter Notebooks with code implementation
│── results/               # Output visualizations (word clouds, boxplots, histograms)
│── src/                   # Source code scripts for preprocessing, modeling & analysis
│── README.md              # Project documentation (this file)
│── requirements.txt       # Dependencies list for easy setup
```

---

## Installation & Setup
### Prerequisites
Ensure you have **Python 3.8+** installed. Install dependencies via:
```bash
pip install -r requirements.txt
```

### Required Libraries
```python
pandas
nltk
gensim
matplotlib
numpy
scikit-learn
seaborn
wordcloud
scipy
```
Install them using:
```bash
pip install pandas nltk gensim matplotlib numpy scikit-learn seaborn wordcloud scipy
```

---

## Usage

### 1. Data Preprocessing
- Cleans survey responses by **removing stopwords, tokenizing, and lemmatizing**.
- Handles missing values.
- Outputs a processed dataset ready for modeling.

Run:
```bash
python src/preprocess_data.py
```

### 2. Topic Modeling (LDA)
- Trains an **LDA model** with varying parameters.
- Identifies dominant **topics per document**.
- Evaluates **coherence scores** to optimize model performance.

Run:
```bash
python src/topic_modeling.py
```

### 3. Sentiment Analysis & Visualization
- Computes **sentiment scores** using **VADER**.
- Generates **word clouds** highlighting key sentiment-driven words.
- Creates **boxplots comparing sentiment scores per topic**.

Run:
```bash
python src/sentiment_analysis.py
```

### 4. Statistical Analysis & Model Validation
- Runs **1000 simulations** with different random configurations of LDA parameters (number of topics, passes, random seeds).
- Computes:
  - **Mean & standard deviation** of coherence and sentiment scores.
  - **95% confidence intervals** to assess stability.
  - **T-tests** for statistical validation.
- Produces **histograms of coherence & sentiment score distributions**.

Run:
```bash
python src/statistical_analysis.py
```

---

## Results & Insights
### Topic Coherence Scores
- The average coherence score was **0.306**, indicating **moderate topic coherence**.
- Confidence interval: **[0.264, 0.343]**, ensuring model stability.

### Sentiment Scores
- The mean sentiment score was **0.986**, suggesting that responses were **predominantly positive**.
- Confidence interval: **[0.780, 1.000]**, confirming consistency.

### Hypothesis Testing
- **Null Hypothesis:** The coherence score is equal to 0.3.
- **Result:** **p-value ≈ 8.33e-23** (much smaller than 0.05).
- **Conclusion:** Strong evidence against the null hypothesis; coherence is significantly different from 0.3.

---

## Error Handling & Debugging
- **Missing Values:** Handled before processing.
- **NameError (e.g., 'ldamodel' not defined):** Ensure correct LDA model reference.
- **Statistical Errors:** Ensure sufficient simulation runs for stable estimates.

---

## Future Enhancements
🚀 **Dynamic topic selection** based on coherence optimization.  
📊 **Interactive dashboards** with Streamlit for real-time analysis.  
🤖 **Deep learning-based topic modeling** (e.g., BERTopic, Transformer models).  

---

## Contributing
1. Fork the repository.  
2. Create a new branch (`feature-branch`).  
3. Commit your changes.  
4. Submit a pull request.  

---

Let me know if you need any refinements or additions! 🚀

