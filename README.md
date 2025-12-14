# Assignment 8 – LLM Evaluation on IMDb Sentiment

Mateusz Ozog  
AD 331  
DistilBERT fine-tuned on IMDb sentiment (from Assignment 7)

---

## Overview

In Assignment 7, I fine-tuned a DistilBERT model on the IMDb movie review dataset to classify reviews as negative or positive.

The goal of Assignment 8 is to evaluate that fine-tuned model using proper classification metrics, a confusion matrix, and error analysis.

---

## Evaluation Metrics

The model was evaluated on the IMDb test set using the following metrics:

| Metric | Value |
|------|------|
| Accuracy | 0.9219 |
| Macro Precision | 0.9221 |
| Macro Recall | 0.9219 |
| Macro F1 Score | 0.9219 |

---

## Why Macro F1 Is Important

Accuracy shows how often the model is correct overall, but it does not show how well the model performs on each class.

Macro F1 calculates precision and recall for each class separately and then averages them equally. This means both negative and positive reviews are treated the same.

Because sentiment analysis requires balanced performance across both classes, macro F1 is a better primary metric than accuracy alone.

---

## Confusion Matrix

A normalized confusion matrix was created to better understand the model’s predictions.

- Rows show the true labels.
- Columns show the predicted labels.
- Diagonal cells show correct predictions.
- Off-diagonal cells show errors.

From the confusion matrix:
- About **91.2%** of negative reviews were correctly classified.
- About **93.2%** of positive reviews were correctly classified.
- About **8.8%** of negative reviews were misclassified as positive.
- About **6.8%** 

---

## Error Analysis

Based on per-class F1 scores, the worst-performing class was:

**Worst class:** negative

Two misclassified examples from this class were analyzed.

**Example 1:**  
The model misclassified this review because the sentiment was mixed, with both positive and negative language present. The model likely focused on positive keywords instead of the overall negative tone.

**Example 2:**  
The model misclassified this review because the text was short or ambiguous, making it difficult to clearly determine the sentiment.

These examples show that the model struggles most with subtle language, mixed sentiment, and ambiguous reviews.

---

## Files Included

- `Assignment_8.ipynb`
- `confusion_matrix.png`
- `README.md`

---

## Conclusion

This assignment helped me understand how to properly evaluate a fine-tuned language model. By using macro-averaged metrics, a confusion matrix, and error analysis, I was able to see both the strengths of the model and where it still struggles.
of positive reviews were misclassified as negative.
