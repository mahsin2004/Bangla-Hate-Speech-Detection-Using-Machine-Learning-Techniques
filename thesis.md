# Thesis: Bangla Hate Speech Detection Using Machine Learning Techniques

## 1. Introduction
*   **1.1 Background:** The rise of social media and the increasing prevalence of online hate speech globally.
*   **1.2 Problem Statement:** Lack of robust hate speech detection systems for the Bengali language, which is under-resourced in Natural Language Processing (NLP).
*   **1.3 Motivation:** The significant social impact of hate speech in the Bengali-speaking community and the urgent need for automated monitoring and moderation systems.
*   **1.4 Objectives:**
    *   To develop and analyze a comprehensive dataset for Bengali hate speech classification.
    *   To implement and evaluate machine learning models (Linear SVM and Logistic Regression) for effective classification.
    *   To analyze the effectiveness of balancing techniques like SMOTE in improving model performance across minority classes.

## 2. Literature Review
*   **2.1 Hate Speech Detection in Global Languages:** Review of techniques used for English and other major languages, focusing on supervised learning and feature extraction.
*   **2.2 NLP for Bengali:** Current state of Bengali Natural Language Processing, including tokenization and script-specific challenges.
*   **2.3 Related Work:** Discussion of foundational research, specifically the **DeepHateExplainer** [1] framework, which provides an explainable approach to hate speech detection in Bengali.

## 3. Dataset Description
*   **3.1 Data Sources:**
    *   Social Media: Facebook pages, Twitter, and YouTube comments.
    *   News Portals: Daily Prothom Alo, Daily Jugontor, BBC Bangla, and Daily Nayadiganta.
    *   Others: Bengali Wikipedia dump, books, and blogs.
*   **3.2 Data Collection:** A bootstrap approach was employed, utilizing common slurs and terms identified from a raw text corpus of 250 million articles.
*   **3.3 Data Annotation:**
    *   Categorization into four primary classes: Personal, Political, Religious, and Geopolitical Hate.
    *   **Annotation Rationale:** Personal and gender-abusive hate were found to have significant semantic overlap in Bengali. Consequently, gender-abusive statements were categorized under 'Personal Hate' to ensure classification consistency.
    *   The process involved three expert annotators: a linguist, a native Bengali speaker, and an NLP researcher.
    *   Inter-annotator agreement was ensured using a majority voting system and validated with the **Cohen's Kappa statistic** to measure consistency.
*   **3.4 Dataset Statistics:**
    *   Total Samples: 5,698.
    *   Class Distribution: Personal (2189), Geopolitical (1738), Religious (957), Political (814).
*   **3.5 Lexical Analysis:** Frequent words and word cloud analysis were performed for each hate category to identify key discriminatory terms.

## 4. Methodology
*   **4.1 Text Preprocessing:**
    *   Cleaning raw text using Regular Expressions (Regex) to remove noise, special characters, and symbols.
    *   **Unicode Preservation:** Specifically retaining characters within the **Bangla Unicode block (\u0980-\u09FF)** to maintain the linguistic integrity of the content.
*   **4.2 Feature Engineering:**
    *   **TF-IDF Vectorization:** Converting text into numerical representations based on Term Frequency-Inverse Document Frequency [2].
    *   **N-gram Analysis:** Use of **Trigrams (1 to 3 n-grams)** to capture contextual sequences, which is critical for identifying offensive phrases that rely on word combinations.
*   **4.3 Handling Class Imbalance:**
    *   Implementation of **SMOTE (Synthetic Minority Over-sampling Technique)** [3] to balance the dataset, preventing model bias towards majority classes like 'Personal Hate'.
*   **4.4 Model Selection:**
    *   **Linear Support Vector Machine (LinearSVC):** Chosen for its efficiency in high-dimensional feature spaces typical of text classification [4].
    *   **Logistic Regression:** Implemented as a baseline statistical model for performance comparison [4].

## 5. Experimental Results
*   **5.1 Evaluation Metrics:** Models were evaluated based on Accuracy, Precision, Recall, and F1-Score.
*   **5.2 Performance Comparison:**
    *   **Linear SVM:** Achieved **78% Accuracy** and an **F1-Score of 0.78**.
    *   **Logistic Regression:** Achieved **75% Accuracy** and an **F1-Score of 0.75**.
*   **5.3 Confusion Matrix Analysis:** Analysis revealed that the models are particularly strong at identifying Religious hate speech but occasionally struggle with semantic overlaps between Personal and Political categories.
*   **5.4 Category-wise Performance:** Detailed reports indicate high recall for the most frequent categories, validated through SMOTE-enhanced training.

## 6. Visualizations and Analysis
*   **6.1 Accuracy Comparison:** Bar charts (accuracy_comparison.png) highlighting the performance lead of Linear SVM.
*   **6.2 Metrics Comparison:** Side-by-side visualization of Precision, Recall, and F1-Score (metrics_comparison.png).
*   **6.3 Confusion Matrices:** Visual error analysis (confusion_matrix.png) used to diagnose misclassification patterns.
*   **6.4 Word Clouds:** Visualization of category-specific lexicons (final_words_cloud_hate.png).

## 7. Discussion and Conclusion
*   **7.1 Interpretation of Results:** Linear SVM's superior performance is attributed to its ability to handle the sparse, high-dimensional vectors generated by TF-IDF trigrams.
*   **7.2 Challenges:** Semantic overlap (e.g., Personal vs. Gender abusive), complex Bengali grammar, and the evolving nature of internet slang.
*   **7.3 Conclusion:** The project successfully demonstrates an effective pipeline for Bengali hate speech detection using expert-annotated data and balanced machine learning models.
*   **7.4 Future Work:** Potential for implementing Deep Learning architectures (CNN, LSTM) and Transformer-based models like **BanglaBERT** for improved contextual understanding.

## 8. References
*   [1] Karim, M. R., Dey, S. K. M., Islam, T., Sarker, S., Menon, M. H., Hossain, K., Hossain, Md. A., & Decker, S. (2021). **DeepHateExplainer: Explainable Hate Speech Detection in Under-resourced Bengali Language**. *2021 IEEE International Conference on Data Science and Advanced Analytics (DSAA)*, 1-10. doi: 10.1109/DSAA53316.2021.9564230.
*   [2] Salton, G., & Buckley, C. (1988). **Term-weighting approaches in automatic text retrieval**. *Information Processing & Management*, 24(5), 513-523.
*   [3] Chawla, N. V., Bowyer, K. W., Hall, L. O., & Kegelmeyer, W. P. (2002). **SMOTE: Synthetic Minority Over-sampling Technique**. *Journal of Artificial Intelligence Research*, 16, 321-357.
*   [4] Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., ... & Duchesnay, E. (2011). **Scikit-learn: Machine Learning in Python**. *Journal of Machine Learning Research*, 12, 2825-2830.
*   [5] Project Repository: [Bangla-Hate-Speech-Detection-Using-Machine-Learning-Techniques](https://github.com/mahsin2004/Bangla-Hate-Speech-Detection-Using-Machine-Learning-Techniques)
