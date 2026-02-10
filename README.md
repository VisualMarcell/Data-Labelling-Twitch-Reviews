# Twitch App Reviews: Data Quality Audit & Heuristic Labeling

## 📌 Project Overview
This project focuses on auditing and validating the data quality of **55,989 Twitch app reviews**. Rather than just labeling data, I built a pipeline to measure the consistency between user-provided star ratings and the actual sentiment expressed in their text, identifying "noisy" data that could hinder machine learning performance.

The goal is to demonstrate a rigorous approach to data preprocessing and quality assurance for NLP tasks.

---

## 📂 Project Structure
```text
data-labelling-twitch-reviews/
├── twitch_reviews.csv            # Raw dataset (55k+ reviews)
├── twitch_reviews_audited.csv    # Dataset with consistency & heuristic flags
├── Twitch_Reviews_Labelling.ipynb # Logic for rule-based heuristics & auditing
└── Twitch_Reviews_Visualization.ipynb # Analysis of agreement & lexical patterns


🛠️ Tech Stack
Language: Python
Libraries: Pandas, NumPy, Scikit-learn (Metrics), Matplotlib, Seaborn, WordCloud
Tools: Jupyter Notebook, VS Code

📊 Methodology & Technical Insights
1. Heuristic-Based Validation
Implemented a rule-based lexical heuristic to check if the text sentiment aligns with numerical ratings.
Consistency Score: Achieved a Cohen’s Kappa of 0.8211, which indicates substantial agreement. This confirms that the keyword-based approach aligns well with user ratings.
Agreement Rate: The overall consistency reached 94.90%, showing high reliability in the majority of the dataset.

2. Identifying Data Noise (Label Inconsistency)
A key part of this project was finding where the data "fails."
Detected Inconsistencies: Identified 4,909 samples (8.7%) where the text and rating diverged (e.g., a 1-star rating with positive text).
Significance: Recognizing these samples is crucial to prevent "Noisy Supervision," which can degrade the performance of future AI models.

3. Lexical Analysis
Analyzed how domain-specific Twitch jargon (e.g., "pog", "revert", "tiktok") influences sentiment signals.
Visual Diagnostics: Used Normalized Confusion Matrices to map agreement and Word Clouds to visualize lexical contributions.

📈 Executive Summary
This project represents the analytical and interpretability layer of a data pipeline. By auditing nearly 56k reviews, I demonstrated:
Data Integrity: Proven high consistency in the dataset while pinpointing the exact 8.7% of problematic "noisy" data.
Actionable Roadmap: Provided clear next steps, such as using N-grams to catch context (like "not good") and suggesting Human-in-the-Loop validation for flagged inconsistencies.
ML Readiness: The resulting "audited" dataset is significantly more robust for training future sentiment classifiers (e.g., BERT) compared to raw, unverified data.

🚀 How to Run
Install dependencies: pip install pandas scikit-learn matplotlib seaborn wordcloud
Run Twitch_Reviews_Labelling.ipynb to see the auditing logic.
Run Twitch_Reviews_Visualization.ipynb to view the distribution and quality diagnostics.