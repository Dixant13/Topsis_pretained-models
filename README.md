# 🎯 Model Selection using TOPSIS for Binary Text Classification

This project applies **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** to rank and select the best pretrained Transformer model for **binary sentiment classification** on the IMDb movie reviews dataset.

Instead of relying only on accuracy, this project evaluates multiple performance metrics and uses a multi-criteria decision-making approach to determine the best overall model.

---

## 📌 Project Overview

- **Task:** Binary Text Classification (Positive / Negative)
- **Dataset:** IMDb Movie Reviews
- **Training Samples:** ~8,000
- **Testing Samples:** ~2,000
- **Models Evaluated:** 6 Pretrained Transformer Models
- **Selection Method:** TOPSIS

---

## 📂 Dataset

The IMDb Movie Reviews dataset is used for binary sentiment classification.

The dataset is accessed using the Hugging Face `datasets` library.  
A subset is used for faster experimentation (e.g., Google Colab).

---

## 🤖 Models Evaluated

The following pretrained transformer models were fine-tuned and evaluated:

- BERT  
- RoBERTa  
- DistilBERT  
- ALBERT  
- ELECTRA  
- DeBERTa  

Each model is trained and evaluated on the same dataset split for fair comparison.

---

## 📊 Evaluation Metrics

The following performance metrics are computed for each model:

- Accuracy  
- Precision  
- Recall  
- F1-Score  

These metrics are used as criteria for the TOPSIS ranking algorithm.

---

## 🧮 TOPSIS Methodology

TOPSIS (Technique for Order Preference by Similarity to Ideal Solution) works as follows:

1. Construct decision matrix using model performance metrics.
2. Normalize the decision matrix.
3. Apply weights to each metric.
4. Determine ideal best and ideal worst solutions.
5. Compute distance from ideal best and worst.
6. Calculate TOPSIS score.
7. Rank models based on closeness score.

The model with the highest TOPSIS score is selected as the best model.

## 📈 Final Results (Based on TOPSIS Ranking)

After evaluating all 6 pretrained models using multiple performance metrics and applying the TOPSIS algorithm, the final ranking is as follows:

| Rank | Model                          | Accuracy | F1-Score | TOPSIS Score |
|------|--------------------------------|----------|----------|--------------|
| 🥇 1 | **albert-base-v2**              | 0.0958   | 0.0958   | **0.7905**   |
| 🥈 2 | distilbert-base-uncased        | 0.1012   | 0.1012   | 0.7451       |
| 🥉 3 | roberta-base                   | 0.1043   | 0.1043   | 0.5286       |
| 4    | bert-base-uncased              | 0.1013   | 0.1013   | 0.5188       |
| 5    | xlnet-base-cased               | 0.1036   | 0.1036   | 0.3378       |
| 6    | microsoft/deberta-v3-base      | 0.1059   | 0.1059   | 0.1794       |

---

## 🏆 Best Model Selected

According to the TOPSIS multi-criteria decision-making approach:

> ✅ **ALBERT (albert-base-v2)** is the best overall model for this project.

Although some models achieved slightly higher raw accuracy, TOPSIS considers multiple criteria such as:
- Accuracy  
- Precision  
- Recall  
- F1-score  
- Inference Time  
- Model Size  

After balancing all criteria, **ALBERT achieved the highest TOPSIS score (0.7905)** and Rank 1.

---

## 🎯 Conclusion

Using a multi-metric evaluation strategy ensures a more reliable and balanced model selection process.

For this IMDb binary text classification task:

> 🚀 **Recommended Model: ALBERT (albert-base-v2)**

This model provides the best overall trade-off between performance and efficiency.



