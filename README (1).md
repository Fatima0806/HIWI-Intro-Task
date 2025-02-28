
# HIWI TASK







## Key Features Driving Failures


1. End Cap Winding Tube LE (Roundness Bearing Point)

Statistical Test: t-test (p = 0.045) shows a significant difference between Pass and Fail samples.
Random Forest: Ranked #2 (12.9% importance) in predicting failures.
Partial Dependence Plot: Higher irregularities increase failure probability.


2. Axle Damper (Torque, Nm)

Random Forest: Ranked #5 (8.6% importance) as a failure predictor.
Partial Dependence Plot: Higher torque slightly increases failure chances.

3. Winding Tube (Roundness) (Previously overlooked but important)

Random Forest: Top predictor (14.2% importance) in failure classification.
Partial Dependence Plot: Irregular roundness significantly raises failure risk.

Key Finding:
"Winding Tube (Straightness)" and "Bearing Spring (Roundness Bearing Point)" were not statistically significant and had low model importance, meaning they are unlikely to be major failure drivers.


## Summary of Recommendations for Improving the Manufacturing Process

A. Improve Precision in Critical Components

✅ Focus on Winding Tube Roundness – Primary Failure Driver

🔹 Tighten Roundness Tolerances – Reduce acceptable deviations in roundness to minimize defects (14.2% feature importance).

🔹 Material Uniformity Checks – Variations in material properties impact component shape; standardizing sourcing can reduce roundness failures.

✅ Control Axle Damper Torque to Avoid Overloading

🔹 More Frequent Calibration of Torque Tools – Ensures torque stays within optimal limits (8.6% feature importance).

🔹 Automated Torque Feedback Systems – Implement real-time adjustments to avoid excessive force application.

B. Optimize Manufacturing Equipment & Calibration

✅ Dimensional Stability in End Cap Winding Tube LE

🔹 Automate Measurement of Roundness – Real-time monitoring can catch deviations early (12.9% feature importance).

🔹 Optimize Spring Tensioning Process – Prevents inconsistencies in torsion spring extension, which impacts assembly performance.


C. Reduce Process Variability with Statistical Quality Control

✅ Implement Real-Time SPC (Statistical Process Control)

🔹 Continuous monitoring of feature distributions can help detect gradual shifts in manufacturing accuracy before defects occur.

✅ Predictive Maintenance for Key Machinery

🔹 Failures linked to roundness deviations suggest potential machine wear issues—predictive maintenance can prevent faulty production batches.

D. Enhance Failure Prediction and Prevention

✅ Adopt AI-Based Quality Control for Early Failure Detection

🔹 Use Machine Learning Models trained on validated failure predictors to detect defects before final QC checks.

🔹 Apply SHAP Analysis to Identify Root Causes – Target process changes where SHAP values indicate the strongest defect influences.



E. Address Imbalanced Failure Detection

✅ Increase Testing for Underrepresented Failure Cases

🔹 More targeted sampling of borderline failure cases will improve defect identification.

✅ Generate Synthetic Data to Improve Model Training

🔹 Use SMOTE (Synthetic Minority Oversampling) to address rare failure cases and improve AI model robustness.
## Knowledge Graphs

A Knowledge Graph (KG) can enhance failure detection and explainability by linking manufacturing features, failure causes, and corrective actions in a structured way.

Step 1: Define Entities & Relationships in the Manufacturing KG
Entities (Nodes):

Manufacturing Features (e.g., Winding Tube Roundness, Axle Damper Torque)
Component Defects (e.g., Misalignment, Irregular Shape)
Failure Outcomes (Pass/Fail)
Corrective Actions (e.g., Tighter Tolerances, Predictive Maintenance)
Relationships (Edges):

Feature → Defect: (e.g., “Winding Tube Roundness” → “Irregular Shape”)
Defect → Failure: (e.g., “Irregular Shape” → “Failure”)
Failure → Corrective Action: (e.g., “Failure” → “Tighter Tolerances”

Step 2: Construct the Knowledge Graph from Data
🔹 Using NetworkX for Graph Representation in Python

Step 3: Perform Graph-Based Failure Analysis

🔹 1. Path Discovery – Identifying Hidden Failure Causes
KG allows us to discover indirect failure paths that may not be visible in standard feature importance scores.

Example Insight:
KG may uncover multi-hop relationships, such as:

"Winding Tube Roundness" → "Irregular Shape" → "Failure"
Even if "Winding Tube Roundness" had low direct correlation, it can still lead to failures via hidden dependencies.

🔹 2. Clustering & Anomaly Detection – Identifying High-Risk Groups

Using graph clustering, we detect which feature combinations increase failure risk.

🔹 Example Insight:
Clusters may show that high torque + low spring roundness = higher failure risk, even if each feature alone is not a strong predictor.
#
Where a Knowledge Graph (KG) Adds Value in Failure Analysis:

By integrating a Knowledge Graph (KG) with the dataset, we gain deeper insights into failure mechanisms beyond traditional ML models. Below are the key advantages, applied specifically to the roller slide assemblies dataset.

📌 1. Visualizing Dependencies Between Features and Failures

🔹 How It Relates to Our Data:
The dataset includes manufacturing features (e.g., Axle Damper Torque, Winding Tube Roundness) and failure outcomes (Pass/Fail).
Instead of only using feature importance scores, a KG shows how multiple features interact to cause failures.

🔹 KG Insights from Data:
"Winding Tube Roundness" → "Bearing Misalignment" → "Failure"
"Axle Damper Torque" → "Excessive Force" → "Failure"

Example from KG Analysis:

🔹 Even if "Winding Tube Roundness" has a low correlation with failure directly, it may still cause failures by first causing misalignment, which then leads to defects.

💡 Why This Matters:
A standard correlation heatmap would miss this, while the KG explicitly shows failure chains.

📌 2. Inferring Hidden Patterns That Are Not Obvious in Traditional ML

🔹 How It Relates to Our Data:
Standard Random Forest or Logistic Regression models may not capture indirect feature interactions.

KG can uncover unknown dependencies using graph algorithms.

🔹 KG Insights from Data:
If we run path discovery algorithms, we may find:
"Winding Tube Roundness" → "Torsion Spring Extension" → "Failure"
even if statistical tests don’t directly link roundness to failure.

🔹 Graph-Based Anomaly Detection on Failures
Using graph clustering techniques (e.g., Louvain method), we identify groups of failures linked to certain conditions:

Cluster 1: (High Torque + Low Roundness → Misalignment → Failure)

Cluster 2: (Normal Torque + Normal Roundness → No Failure)

💡 Why This Matters:

These clusters help identify "hidden" failure risks that do not appear in direct statistical correlations.

📌 3. Enhancing Explainability by Linking Failure Types to Component Issues

🔹 How It Relates to Our Data:
Our dataset contains quantitative metrics (e.g., torque, dimensions) but does not explicitly state failure reasons.

KG helps map failures to specific components and manufacturing defects.

🔹 KG Insights from Data:
Axle Damper (Torque) → Excessive Force → Structural Weakness → Failure
Winding Tube (Straightness) → Bearing Misalignment → Failure

By running graph-based reasoning, we can trace each failure back to its root cause.

💡 Why This Matters:

Engineers don’t just see "Feature X is important"; they see "Feature X affects Component Y, which leads to Failure Z".

📌 4. Improving Failure Prediction with Graph Neural Networks (GNNs)

🔹 How It Relates to Our Data:

Standard ML models (e.g., Random Forest) assume independence between features.

A Graph Neural Network (GNN) can model interdependencies between manufacturing parameters.

🔹 KG Insights from Data:

Using a GNN, we can:

Train a model that considers multi-hop feature interactions.
Predict which components are likely to fail before final QC checks.

💡 Why This Matters:

Traditional ML might flag "Axle Damper Torque" as important but not explain why.
A KG-based GNN can predict failure patterns based on interdependencies.
