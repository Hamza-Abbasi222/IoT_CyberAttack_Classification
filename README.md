# Classification of Cyber Attacks on IoT Using Machine Learning

> **Master's Thesis Project** — National University of Modern Languages (NUML), Islamabad  
> **Duration:** September 2022 – January 2024  
> **Domain:** Cybersecurity · Machine Learning · Internet of Things (IoT)

---

## 📌 Overview

The rapid expansion of Internet of Things (IoT) devices has introduced significant cybersecurity vulnerabilities. Traditional rule-based security systems struggle to keep up with the evolving nature of modern cyber threats. This research proposes a robust machine learning framework to automatically classify and detect cyber attacks targeting IoT infrastructure.

The project employs an ensemble of **XGBoost** and **Deep Neural Network (DNN)** models — combining their strengths to achieve superior classification performance over individual models. The system is capable of identifying multiple attack categories including **DDoS attacks**, **malware intrusions**, **reconnaissance**, **backdoor attacks**, and **normal traffic**.

---

## 🎯 Objectives

- Develop an automated cyber attack classification system for IoT environments
- Explore and compare multiple machine learning approaches on benchmark datasets
- Build a full ML pipeline: from raw data ingestion to model evaluation
- Achieve high accuracy in distinguishing attack types from normal network traffic
- Demonstrate the practical applicability of ML in real-world IoT cybersecurity

---

## 📊 Dataset

### UNSW-NB15
| Property | Detail |
|----------|--------|
| Source | University of New South Wales, Australia |
| Type | Network traffic dataset |
| Features | 49 features |
| Classes | Normal + 9 Attack Categories |
| Attack Types | Fuzzers, Analysis, Backdoors, DoS, Exploits, Generic, Reconnaissance, Shellcode, Worms |
| Model Accuracy | **85.36%** |

The UNSW-NB15 dataset is a widely recognized benchmark in cybersecurity research, created using the IXIA PerfectStorm tool to generate realistic modern attack behaviors.

### NSL-KDD
| Property | Detail |
|----------|--------|
| Source | University of New Brunswick |
| Type | Improved version of KDD Cup 1999 |
| Classes | Normal + 4 Attack Categories (DoS, Probe, R2L, U2R) |
| Model Accuracy | **99.81%** |

NSL-KDD addresses the redundancy issues present in the original KDD dataset, making it a cleaner benchmark for intrusion detection evaluation.

---

## 🏗️ Project Pipeline

```
Raw Dataset (UNSW-NB15 / NSL-KDD)
        │
        ▼
┌─────────────────────┐
│  1. Data            │  • Exploratory Data Analysis (EDA)
│     Visualization   │  • Attack pattern identification
│                     │  • Class distribution analysis
│                     │  • Correlation heatmaps & feature plots
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  2. Feature         │  • Handling missing values
│     Engineering     │  • Encoding categorical variables
│                     │  • Feature scaling & normalization
│                     │  • Class imbalance handling (SMOTE)
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  3. Feature         │  • Correlation-based selection
│     Selection       │  • Feature importance (XGBoost)
│                     │  • Dimensionality reduction
│                     │  • Removing redundant features
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  4. Model           │  • XGBoost Classifier
│     Implementation  │  • Deep Neural Network (DNN)
│                     │  • Ensemble (XGBoost + DNN)
│                     │  • Hyperparameter Tuning
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  5. Evaluation      │  • Accuracy, Precision, Recall, F1
│  & Results          │  • Confusion Matrix
│                     │  • ROC-AUC Curves
│                     │  • Cross-validation
└─────────────────────┘
```

---

## 🤖 Models Used

### 1. XGBoost (Extreme Gradient Boosting)
- Gradient boosted decision tree ensemble
- Excellent performance on tabular/structured network data
- Built-in feature importance ranking
- Robust against overfitting with regularization

### 2. Deep Neural Network (DNN)
- Multi-layer feedforward neural network
- Captures complex non-linear patterns in network traffic
- Trained with dropout layers to prevent overfitting
- Optimized using Adam optimizer with learning rate scheduling

### 3. Ensemble Model (XGBoost + DNN) ⭐
- Combines predictions from both models via averaging
- Leverages the strengths of both tree-based and deep learning approaches
- Achieves better generalization than either model individually
- Final model used for evaluation and reporting

---

## 📈 Results

| Model | UNSW-NB15 Accuracy | NSL-KDD Accuracy |
|-------|-------------------|-----------------|
| Logistic Regression | ~72% | ~92% |
| Random Forest | ~79% | ~97% |
| XGBoost | ~82% | ~98% |
| DNN | ~81% | ~98% |
| **XGBoost + DNN Ensemble** | **85.36%** | **99.81%** |

### Key Findings
- The ensemble approach consistently outperformed individual models
- Feature engineering significantly improved model performance
- DDoS and Normal traffic were classified with highest confidence
- Shellcode and Worm attacks were the most challenging to classify due to limited samples

---

## 🛠️ Tech Stack

| Category | Tools & Libraries |
|----------|------------------|
| Language | Python 3.8+ |
| ML Framework | Scikit-Learn, XGBoost |
| Deep Learning | TensorFlow 2.x, Keras |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Notebook Environment | Jupyter Notebook, Google Colab |
| Version Control | Git, GitHub |

---

## 📁 Repository Structure

```
IoT_CyberAttack_Classification/
│
├── Data_Visualization_on_UNSWNB15.ipynb
│   └── EDA, attack pattern plots, class distribution,
│       correlation heatmaps
│
├── Feature_Engineering_on_UNSWNB15.ipynb
│   └── Data cleaning, encoding, scaling,
│       imbalance handling
│
├── Feature_Selection_and_Model_Implementation_on_UNSWNB15.ipynb
│   └── Feature selection, XGBoost, DNN,
│       Ensemble model, evaluation metrics
│
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
```bash
Python 3.8+
Jupyter Notebook or Google Colab
```

### Installation
```bash
# Clone the repository
git clone https://github.com/Hamza-Abbasi222/IoT_CyberAttack_Classification.git

# Navigate to project directory
cd IoT_CyberAttack_Classification

# Install required libraries
pip install numpy pandas matplotlib seaborn scikit-learn xgboost tensorflow keras jupyter
```

### Running the Notebooks
```bash
# Launch Jupyter Notebook
jupyter notebook

# Run notebooks in this order:
# 1. Data_Visualization_on_UNSWNB15.ipynb
# 2. Feature_Engineering_on_UNSWNB15.ipynb
# 3. Feature_Selection_and_Model_Implementation_on_UNSWNB15.ipynb
```

### Dataset Download
The UNSW-NB15 dataset can be downloaded from:  
🔗 [UNSW-NB15 Official Page](https://research.unsw.edu.au/projects/unsw-nb15-dataset)

The NSL-KDD dataset can be downloaded from:  
🔗 [NSL-KDD Official Page](https://www.unb.ca/cic/datasets/nsl.html)

---

## 🔍 Attack Categories Detected

| Attack Type | Description |
|-------------|-------------|
| **DDoS / DoS** | Distributed Denial of Service — overwhelms network resources |
| **Malware** | Malicious software infiltrating IoT devices |
| **Reconnaissance** | Information gathering before an attack |
| **Backdoor** | Unauthorized hidden access to a system |
| **Exploits** | Attacks leveraging software vulnerabilities |
| **Fuzzers** | Sending random data to crash or probe systems |
| **Shellcode** | Injecting code to gain control of a device |
| **Worms** | Self-replicating malware spreading across networks |
| **Normal** | Legitimate, non-malicious network traffic |

---

## 📚 Research Context

This work is part of the growing body of research applying supervised machine learning to **Network Intrusion Detection Systems (NIDS)**. As IoT devices proliferate across smart homes, healthcare, and industrial systems, the need for intelligent, automated threat detection becomes critical.

The ensemble approach used in this thesis aligns with current best practices in the cybersecurity ML literature, where combining diverse models consistently yields more robust detection capabilities than single-model approaches.

---

## 👤 Author

**Hamza Ishtiaq**  
MS Electrical Engineering (Machine Learning) — NUML, Islamabad  
🔗 [LinkedIn](https://www.linkedin.com/in/hamza-ishtiaq-abbasi/)  
🐙 [GitHub](https://github.com/Hamza-Abbasi222)  
📧 hmza.abxi222@gmail.com

---

## 📄 License

This project is for academic and research purposes.  
© 2024 Hamza Ishtiaq — National University of Modern Languages (NUML)
