# Multi-Gesture Recognition for Stroke Rehabilitation Using sEMG Signals

## 🧠 Abstract
Stroke rehabilitation requires accurate and reliable interpretation of muscle activity to enable effective human–machine interaction. This project presents a **hybrid multi-gesture recognition framework** using **surface Electromyography (sEMG) signals**, combining **handcrafted feature extraction** with **Spiking Neural Networks (SNNs)** for temporal learning. By fusing feature-based and frequency-domain SNN representations, the proposed **CSNN-feature hybrid model** achieves a **peak test accuracy of 96.25%**, outperforming standalone SNN-based approaches.

---

## 📌 Key Highlights
- Hybrid **Feature + Spiking Neural Network (SNN)** architecture  
- Robust classification of **6 rehabilitation gestures**  
- Temporal modeling using **LIF-based SNN**  
- Significant performance gain over pure SNN models  
- Application-ready for **stroke rehabilitation & assistive systems**

---

## 🎯 Objectives
- Recognize multiple hand gestures from multi-channel sEMG signals  
- Enhance classification accuracy using a hybrid **CSNN–feature model**
- Enable reliable gesture decoding for rehabilitation and assistive technologies

---

## 🧠 Gestures Classified
The system classifies the following **6 hand gestures**:
1. Power  
2. Lateral  
3. Pointer  
4. Open  
5. Tripod  
6. Rest 

![Failed to load image](/images/gestures.png "Gestures")

---

## 📊 Dataset Overview
- **Participants:** 8  
- **Days:** 2  
- **Sessions per day:** 2  
- **Trials per session:** 150  
- **Trials per gesture per session:** 25  
- **Total gestures:** 6  

**Total trials per gesture:**  
25 trials × 4 sessions × 8 participants = 800 trials per gesture

![Failed to load image](/images/datasetoverview.png "Dataset Overview")

###### Raw Data Taken From [Click Here](https://github.com/MoveR-Digital-Health-and-Care-Hub/posture_dataset_collection/tree/main/data).
---

## 🏗️ Model Architecture
The proposed system uses **two parallel processing paths**, whose outputs are fused for final classification.

![Failed to load image](/images/Architecture.png "Model Architecture")

### 🔹 Feature Path
- Raw sEMG signal
- Extraction of **24 handcrafted features**
- Dense (Fully Connected) layers

### 🔹 SNN Path
- Raw sEMG signal
- FFT transformation
- LIF-based **Spiking Neural Network (SNN)**

### 🔹 Fusion
- Outputs from both paths are concatenated
- Final dense layer classifies into **6 gesture classes**

---

## 🧮 Feature Extraction
A total of **24 features** are extracted from each sEMG signal, including:

### Statistical Features
- Mean  
- Standard Deviation  
- Variance  
- Skewness  
- Kurtosis  
- Min / Max / Range  

### Time-Domain Features
- RMS (Root Mean Square)  
- MAV (Mean Absolute Value)  
- ZC (Zero Crossing)  
- WL (Waveform Length)  
- SSC (Slope Sign Changes)  
- WAMP  
- SSI  

### Frequency-Domain Features
- Mean Frequency  

### Histogram-Based Features
- Histogram Mode  
- Histogram Entropy  

---

### 📈 FFT Analysis
FFT is applied to capture frequency-domain characteristics of sEMG signals.

#### Observations

- Dominant energy below 200 Hz
- Distinct spectral patterns across gestures
- Rest gesture exhibits low-amplitude spectrum
- FFT features enhance SNN temporal discrimination

Gesture-wise FFT comparisons show clear separability, especially between active and rest states.

### 🧪 Experimental Setup
#### Data Processing
- Signal normalization
- Window-based segmentation
- FFT applied for SNN input
- Feature vectors computed for dense path

#### Model Details
- SNN: Leaky Integrate-and-Fire (LIF)
- Optimizer: Adam
- Loss Function: Categorical Cross-Entropy
- Epochs: 100
- Evaluation: Train/Test split

![Failed to load image](/images/fft.png "FFT Analysis")

---

## ✅ Results
| Model  | Accuracy |
| ------------- |:-------------:|
| Pure SNN     | ~85%    |
| Hybrid CSNN + Feature      | 96.25%    |

### Key Observations
- Feature + SNN fusion improves robustness
- Confusion matrix shows strong class separation
- Stable training and testing accuracy across epochs

---

## 🧪 Evaluation Metrics
- Test Accuracy
- Confusion Matrix
- Train vs Test Accuracy Curve

![Failed to load image](/images/Output.png "Evaluation Metrics")

---

## 🚀 Conclusion
This project demonstrates that combining **handcrafted sEMG features** with the **temporal processing power of Spiking Neural Networks** leads to highly accurate multi-gesture recognition.  
The proposed hybrid architecture is well-suited for **real-time stroke rehabilitation and assistive systems**.

---

## 👨‍💻 Authors
- Prasoon Mathur
- Haradika Karaveershettar  
- Nitya Arya  
- Anjani Agarwal  

---

## 📚 Applications
- Stroke rehabilitation systems  
- Prosthetic control  
- Human–computer interaction  
- Assistive biomedical devices  

---
###### This project is intended for academic and research purposes.
