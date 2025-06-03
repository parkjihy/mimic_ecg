# mimic_ecg
# 🫀 ECG Classification for Atrial Fibrillation Detection

This project implements and compares two deep learning models — **CNN** and **BiLSTM** — for classifying 
**Atrial Fibrillation (AFib)** from 12-lead ECG signals, using a real-world dataset.

---

## 📊 Dataset Overview

- **Total ECG samples**: 9,679  
- **Labels**: Binary classification (AFib present or not)  
- **Class distribution**:
  - Positive (AFib): 986 (10.19%)
  - Negative: 8,693 (89.81%)

> ⚠️ **Class Imbalance** was addressed using:
> - Weighted loss functions  
> - Weighted random sampling

---

## 🧠 Model Architectures

### 🔹 Convolutional Neural Network (CNN)
- Extracts local spatial features from 12-lead ECG signals
- Two convolutional layers with max pooling
- Dropout + Fully connected layers

### 🔹 Bidirectional LSTM (BiLSTM)
- Captures temporal dependencies in ECG sequences
- BiLSTM layer followed by a fully connected classifier

---

## 🏋️ Training Configuration

- **Train/Test Split**: 80% / 20% (stratified)
- **Loss Handling**: Class-weighted loss + weighted sampling
- **Optimizer**: Adam  
- **Learning Rate**: 1e-4  
- **Epochs**: 5

---

## 📈 Results Summary

| Model | Accuracy | F1 Score | AUC    |
|-------|----------|----------|--------|
| CNN   | **0.8321** | **0.2697** | **0.6934** |
| LSTM  | 0.3673   | 0.2152   | 0.6113 |

> ⚠️ Despite high accuracy, the **low F1 scores** indicate difficulty in detecting the minority class (AFib).
> Further work is needed for clinical-level reliability.

---

## 💡 Discussion

- **CNN outperformed LSTM** due to its ability to capture **spatial patterns** across ECG leads—essential for identifying AFib morphology.
- **LSTM struggled** due to noisy temporal dynamics and limited spatial feature extraction.
- **Class imbalance** significantly affected performance.

---

## 🔭 Future Work

- Data augmentation techniques
- Use of **focal loss**
- Incorporating **Transformer-based** or hybrid models
- More robust preprocessing strategies

---

## 📝 Conclusion

CNN is more effective than LSTM for AFib detection from ECG signals in this setting. However, 
**further improvements in handling class imbalance and model architecture** are necessary for real-world clinical application.

---

