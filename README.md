# AI_RTL_Timing_Prediction
**Brief Summary:**
Timing analysis is a crucial step in designing digital circuits, but it becomes time-consuming due to post-synthesis timing violations. The goal of this project is to develop an AI algorithm that predicts combinational logic depth of RTL signals before synthesis, allowing early detection of timing violations.
We use Machine Learning (ML) models trained on RTL datasets to estimate logic depth based on circuit parameters like Fan-In, Fan-Out, and Gate Count. This enables faster design iterations and optimizations, reducing overall project execution time.

**Problem Statement:**
Modern SoC (System-on-Chip) and IP (Intellectual Property) designers rely on timing analysis tools after synthesis to detect timing violations. This process is slow and often leads to design modifications.
This project proposes an AI-based approach to predict combinational logic depth of signals before synthesis, allowing early identification of potential timing issues. The model uses Fan-In, Fan-Out, and Gate Count as features to estimate combinational depth and flag critical signals that may violate timing constraints.
This solution helps VLSI engineers, RTL designers, and EDA tool developers improve efficiency in ASIC/FPGA design workflows.

**The approach used to generate the algorithm:**

1.**Data Collection & Preprocessing:**
Generated synthetic RTL data with attributes:
Fan-In: Number of input connections.
Fan-Out: Number of output connections.
Gate Count: Number of logic gates in the path.
Combinational Depth: Ground truth calculated using a formula.
Standardized data using StandardScaler.
Encoded categorical features (if any) using LabelEncoder.

2.**Machine Learning Model Selection:**
Random Forest Regressor (for faster inference).
XGBoost Regressor (for higher accuracy).
Models trained on 80% of the dataset, tested on 20%.

3.**Training & Evaluation:**
Loss function: Mean Absolute Error (MAE).
Model Performance:
Random Forest MAE: ~3.46
XGBoost MAE: Lower than RF (~2.5-3.0 expected)

4.**Deployment & Real-Time Prediction:**
Saved trained models (rf_model.pkl, xgb_model.pkl).
Created a function to predict logic depth for new RTL signals.

**Proof of Correctness:**

**User Input:**
Enter RTL Signal Features 
Enter Fan-In: 4
Enter Fan-Out: 2
Enter Gate Count: 13

**Model Output:**
Predicted Depth Category: Low
No Timing Violation Detected.

