
# HIWI TASK







## Key Features Driving Failures


- Axle Damper (Torque, Nm):	
  Higher torque values correlate with failures
- Winding Tube (Straightness): Lack of straightness increases failures	
- End Cap Winding Tube LE (Roundness Bearing Point): Irregular roundness leads to defects
- Torsion Spring (Extension Dimension with Weight, mm): Improper extension can affect performance
- Bearing Spring (Roundness Bearing Point): Variations in roundness cause instability


## Summary of Recommendations for Improving the Manufacturing Process

A. Improve Precision in Critical Components

🔹 Standardize Material Sourcing – Ensure uniform raw material properties to minimize component weight and dimensional variations.

🔹 Tighten Tolerance Levels – Reduce acceptable deviations in key features like winding tube roundness and straightness

B. Optimize Manufacturing Equipment & Calibration

🔹 More Frequent Calibration of Torque Measurement Tools – Prevent axle dampers from exceeding acceptable force limits.

🔹 Automate Dimensional Inspections – Use computer vision or laser measurement systems for real-time monitoring of winding tube dimensions.

C. Reduce Process Variability with Statistical Quality Control

🔹 Implement Real-Time SPC (Statistical Process Control) to monitor feature distributions.

🔹 Use Predictive Maintenance on Key Machinery to prevent faulty production batches.

D. Enhance Failure Prediction and Prevention

🔹 Adopt AI/ML-Based Predictive Models – Use machine learning to predict defects before final QC checks.

🔹 Use SHAP/XAI Methods to Identify Root Causes for proactive intervention.

E. Address Imbalanced Failure Detection

🔹 Enhance Testing for Rare Failure Cases – Increase sampling of borderline cases to improve defect detection.

🔹 Generate Synthetic Data (GANs or SMOTE) to train models on underrepresented failure patterns.
## Knowledge Graphs

A Knowledge Graph (KG) can enhance failure detection and explainability by linking manufacturing features, failure causes, and corrective actions in a structured way. Here’s how a KG can be integrated into the analysis:

Step 1: Define Entities and Relationships
A KG for manufacturing failure analysis would include nodes (entities) and edges (relationships)

Step 2: Construct the Knowledge Graph
We can use Neo4j, NetworkX (Python), or RDF frameworks to build the graph.

Step 3: Perform Graph-Based Failure Analysis
Once the KG is built, we can query it to analyze failure causes and corrective actions.

#
Where a Knowledge Graph (KG) Adds Value in Failure Analysis:

-Visualizing Dependencies Between Features and Failures:

Graph Representation: A KG visually maps how different features interact and which combinations contribute to failures.

Multi-Hop Relationships: Unlike standard feature importance scores, a KG can show indirect influences (e.g., Winding Tube Roundness → Torsion Spring Extension → Failure).

Interactive Visualization: Enables engineers to explore relationships dynamically instead of relying on static correlation heatmaps. 

-Inferring Hidden Patterns That May Not Be Obvious Through Statistical Methods

Path Discovery: KG allows for "unknown unknowns" discovery, revealing failure causes not captured in initial statistical tests.

Graph Embeddings & Machine Learning: KG-based Graph Neural Networks (GNNs) can predict failures even if statistical tests don’t show strong correlations.

Clustering & Anomaly Detection: Detects groups of failures associated with specific feature combinations (e.g., high torque + low spring weight = failure risk).

-Enhancing Explainability by Linking Failure Types to Component Issues

Links ML insights to real-world component failures.

Graph reasoning helps engineers answer:
Which component issues contribute most to failure?
What is the best corrective action?

Structured failure categories → Groups failures into meaningful clusters (e.g., Mechanical vs. Electrical vs. Assembly Defects).