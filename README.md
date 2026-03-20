# Music- Genre- Classification- machine learning- GTZAN
This project transforms the classification task into a supervised learning problem by introducing machine learning methods

## 1. Project Introduction
Music genre classification is a key task in Music Information Retrieval (MIR), which helps music platforms classify, manage, and recommend music automatically. Traditional classification relies on manual labeling, which is inefficient and subjective. This project uses machine learning to realize automatic music genre classification.

The goal of this project is to build, compare, and evaluate three machine learning models:
- Support Vector Machine (SVM)
- XGBoost
- LightGBM

We aim to find the best-performing model on the GTZAN dataset and analyze the classification patterns between different music genres.

---

## 2. Dataset Introduction
We use the **GTZAN Genre Classification Dataset**, a classic benchmark dataset for music classification.

- Source: Kaggle
- Total audio clips: 1000 (30 seconds each)
- Genres: 10 categories (blues, classical, country, disco, hiphop, jazz, metal, pop, reggae, rock)
- After segmentation: 9990 samples (3-second segments)
- Features: 58-dimensional audio features including MFCCs, spectral centroid, spectral bandwidth, spectral rolloff, zero crossing rate, tempo, RMS, chroma features, etc.

---

## 3. Data Preprocessing
We performed the following steps to clean and prepare the data:

1. Remove useless columns: filename and length
2. Encode genre labels into numerical values for model training
3. Split dataset: 80% training set, 20% test set
4. Feature selection using VarianceThreshold to remove low-information features

These steps ensure the model focuses on meaningful acoustic features.

---

## 4. Exploratory Data Analysis (EDA)
We analyzed data distribution and feature characteristics:

- The dataset is balanced across 10 genres
- High correlation exists among spectral features (spectral centroid, rolloff, bandwidth)
- Different genres show obvious differences in feature distributions
- Tempo features are stable in pop and disco music

EDA results help us understand data characteristics and improve model performance.

---

## 5. Models & Methodology
We built and optimized three models using grid search and cross-validation.

### 5.1 SVM
- Kernel: RBF (suitable for high-dimensional audio data)
- Tuning parameters: C, gamma
- Used probability output for classification

### 5.2 XGBoost
- Multiclass classification objective
- Tuning: max_depth, learning_rate, n_estimators
- Strong ability to capture feature relationships

### 5.3 LightGBM
- Leaf-wise tree growth
- Fast training speed
- High efficiency on high-dimensional data

All models use standardized training processes for fair comparison.

---

## 6. Evaluation Metrics
We use four key indicators:
- Accuracy
- Precision
- Recall
- F1-score (macro average)

We also use confusion matrices to analyze misclassification between genres.

---

## 7. Experimental Results
All models achieved **high accuracy above 91%**.

- SVM: 91.59%
- LightGBM: 91.59%
- XGBoost: 91.24%

### Key findings:
- Classical and metal are the easiest to classify correctly
- Similar genres are easy to misclassify:
  - Country ↔ Blues / Rock
  - Rock ↔ Metal / Disco
  - Pop ↔ Disco / Reggae
- LightGBM performs best overall (high accuracy + fast speed)

---

## 8. Conclusion
1. The 58-dimensional audio features can effectively distinguish music genres
2. SVM, XGBoost, LightGBM all perform well on this task
3. LightGBM is the optimal model for music genre classification
4. Misclassification mainly comes from acoustic similarity between genres
5. Machine learning can effectively replace manual music genre classification

---

## 9. References
1. Kaggle. https://www.kaggle.com/datasets/andradaolteanu/
2. Song, J. (2023). Comparison and analysis of accuracy of traditional random forest machine learning model and XGBoost model on music emotion classification dataset. In *Proceedings of the 2023 4th International Conference on Machine Learning and Computer Application*, 712-716.
3. Wen, X., & Li, W. (2023). Time series prediction based on LSTM-Attention-LSTM model. IEEE Access, 11, 48322-48331.
4. Bahuleyan, H. (2018). Music genre classification using machine learning techniques. arXiv preprint arXiv:1804.01149.
5. Silla, C. N., Koerich, A. L., & Kaestner, C. A. (2008). A machine learning approach to automatic music genre classification. *Journal of the Brazilian Computer Society*, 14(3), 7-18.
6. Basili, R., Serafini, A., & Stellato, A. (2004). Classification of musical genre: a machine learning approach.

---
