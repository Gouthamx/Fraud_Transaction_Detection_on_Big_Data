# 🚨 Fraud Transaction Detection on Big Data using Machine Learning & PySpark  

Fraudulent activities in online transactions pose a major risk to financial systems.  
This project leverages **PySpark** and **Machine Learning** to detect fraudulent transactions from a dataset of simulated financial operations.  

---

## 📊 Dataset  

The dataset consists of **financial transactions** with the following features:  

- `step` → Time unit (1 step = 1 hour, total = 744 steps).  
- `type` → Transaction type (`CASH-IN`, `CASH-OUT`, `DEBIT`, `PAYMENT`, `TRANSFER`).  
- `amount` → Transaction amount.  
- `oldbalanceOrg`, `newbalanceOrig` → Sender’s balance before and after transaction.  
- `oldbalanceDest`, `newbalanceDest` → Receiver’s balance before and after transaction.  
- `isFraud` → **Target variable** (1 = fraud, 0 = legit).  
- `isFlaggedFraud` → Flag for illegal transfer attempts (>200,000).  

📂 Dataset link: [Click here to access](https://drive.usercontent.google.com/download?id=1VNpyNkGxHdskfdTNRSjjyNa5qC9u0JyV&export=download&authuser=0)  

---

## ⚙️ Preprocessing  

The preprocessing pipeline includes:  

1. **Loading Data with PySpark**  
   - Dataset is loaded into a Spark DataFrame for distributed handling.  
   - Missing values are inspected and handled.  

2. **Feature Engineering**  
   - Encoding categorical feature `type` into numerical form.  
   - Creating derived features (e.g., transaction differences).  

3. **Class Imbalance Handling**  
   - Fraudulent transactions are rare compared to legitimate ones.  
   - Techniques like **downsampling/upsampling** or **class weights** are considered.  

---

## 🔥 PySpark Setup  

- A **SparkSession** is initialized.  
- Data is processed in a **distributed environment** for scalability.  
- Spark’s **MLlib** is used for transformations and ML pipeline creation.  

---

## 🤖 Model Training  

1. **Feature Vectorization**  
   - Assembled selected features into a single `features` vector using `VectorAssembler`.  

2. **Splitting Data**  
   - Train-test split applied (commonly 70-30 or 80-20).  

3. **Algorithms Used**  
   - **Neural Networks (Deep Learning)**  
     - Implemented with multiple hidden layers.  
     - Optimized using gradient descent and backpropagation.  
     - Tuned with activation functions, learning rate, and regularization.  

4. **Pipeline Construction**  
   - Preprocessing → Feature Assembler → Neural Network Model 


---

## 🧪 Model Testing & Evaluation  

Models are evaluated on the **test set** using:  

- **Accuracy**  
- **Precision, Recall, F1-score**  
- **ROC-AUC curve**  

These metrics highlight the model’s ability to detect fraud while minimizing false positives.  

---

## 📈 Results  

- Neural Networks showed strong performance in detecting fraudulent transactions.  
- Models were evaluated using **Accuracy, Precision, Recall, F1-score, and ROC-AUC**.  
- Due to class imbalance and logic **Recall (detecting fraud cases)** was emphasized over Accuracy.  

---

## 🚀 Future Improvements  

- Use **ensemble models** (XGBoost, LightGBM) for better detection.  
- Deploy model using **Spark Streaming** for real-time fraud detection.  
- Integrate with **Kafka** or cloud services for production-ready solutions.  

---

