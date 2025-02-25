# AI-Based RTL Timing Prediction 🚀

## 📌 Project Overview  
This project uses **Machine Learning (Random Forest & XGBoost)** to predict **combinational logic depth** in RTL designs, helping detect **timing violations early**.  
By estimating the logic depth **before synthesis**, this model helps **VLSI engineers and RTL designers** optimize their circuits and avoid expensive **re-design iterations**.  

## 🚀 Features  
✅ Predicts **combinational depth** before synthesis  
✅ Uses **Fan-In, Fan-Out, Gate Count** as features  
✅ Supports **Random Forest (fast) & XGBoost (accurate)**  
✅ **Saves hours of design time** by avoiding full synthesis runs  

---

📊 Approach Used to Generate the Algorithm

1️⃣ Data Collection & Preprocessing:
Used synthetic RTL data with features:
Fan-In: Number of input connections
Fan-Out: Number of output connections
Gate Count: Total number of logic gates
Combinational Depth: Ground truth calculated using a predefined formula
Scaled numerical values and encoded categorical features

2️⃣ Machine Learning Model Selection:
Random Forest Regressor (for fast inference)
XGBoost Regressor (for higher accuracy)

3️⃣ Training & Evaluation:
Dataset Split: 80% training, 20% testing
Evaluation Metric: Mean Absolute Error (MAE)
Performance:
Random Forest MAE: 3.46
XGBoost MAE: ~2.5 - 3.0 (more accurate but slightly slower)

4️⃣ Deployment & Real-Time Prediction:
Models are saved as .pkl files and can be used for inference
User inputs circuit parameters and receives instant logic depth estimation

---

✅ Proof of Correctness
We validated the AI model using real-time user input and predictions:

**User Input:**
Enter Fan-In: 4
Enter Fan-Out: 2
Enter Gate Count: 13

**Model Output:**
Predicted Depth Category: Low
No Timing Violation Detected.

