# QSAR_Endocrine_Project-
Computational toxicology project: Predicting endocrine disruption potential with interpretable molecular fingerprints.
## Objective
This study aims to identify and proritize relevant structural features of the chemicals that may possess endocrine disrupting potential.
## Dataset
- Source: Tox21 ( NR-ER-LBD assays)
- Compounds: 199
- Columns: `smiles`, `activity` (1=active, 0=inactive)
- ## Methods
-This study utilizes a machine learning workflow to develop a model for predicting endocrine disruptin potential of chemicals using their SMILES string and corresponding binary activity label. The data was imported into python using the pandas library and basic inspection was performed to ensure data integrity. SMILES strings were converted into 2D molecular structures using RDKit. These molecular structures facilitate a more comprehensive evaluation of molecular properties. Feature selection was generated usig RDKit, and the molecules were assigned morgan fingerprints to numerically represent the chemical structures. These fingerprints served as molecular descriptors for the model. A Random forest algorithm was trained and the model performance was assessed using classification metrics such as accuracy, reciever operating characteristic area under the curve (ROC-AUC) and confusion matrix. RF was chosen based on its potential to handle class imbalance and its ability to provide important features that support interpretability. The trained model was used to generate predicted probabilities of estrogen receptors activity for compounds in the test set. To enhance interpretability, key compounds were further analyzed by visualizing their molecular structures while key functional groups such as carbonyl groups were highlighted using RDKit to provide qualitative insight into chemical features potentially associated with estrogen receptor activity.
## Results
ROC–AUC score: ~0.78. ![ROC Curve](Roc_curve.png)
-The RF model achieved an accuracy of 0.825.
This indicates good classification performance, with the model able to reliably separate active from inactive compounds better than random guessing.The ROC curve demonstrates a favorable balance between sensitivity and specificity.
- Accuracy: 0.825
The model achieved an overall accuracy of ~82.5%, indicating strong predictive reliability for a structure-based QSAR model.
- Confusion Matrix: [[22, 1], [6, 11]] ![Confusion Matrix](Confusion_matrix.png)
## Top Predicted Active Compounds
![Top Predicted Compounds](Top_Predicted_Compunds.png)

The model generated probability scores for all compounds in the test set. Compounds with the highest predicted probabilities were ranked to identify top predicted active molecules.
## Functional Group Highlights
Key functional groups were manually highlighted in the top predicted active compounds using RDKit visualization tools.
![Functional Groups Aromatic 1](Functional_groups_aromatic_1.png)
![Functional Groups Aromatic 2](Functional_groups_aromatic_2.png)
![Functional Groups Aromatic 3](Functional_groups_aromatic_3.png)

Highlighted features included:
- Aromatic rings (π-systems associated with receptor binding)
- Carbonyl groups (C=O) (common in bioactive scaffolds)
- Hydrogen-bond donors and acceptors (–OH, –NH groups)
The recurring presence of these functional groups suggests their potential role in mediating endocrine-disrupting activity.
## Conclusion
- A robust QSAR model was developed using molecular fingerprints and Random Forest classification.
- The model demonstrated strong predictive performance with ROC-AUC ≈ 0.78 and accuracy ≈ 82%.
- The model predicts estrogen receptor activity from molecular fingerprints, prioritizing chemicals that may act as endocrine disruptors before experimental testing. Highlighted functional groups and substructures provide interpretable insights into the chemical features contributing to these predictions.
- Top predicted active compounds were identified, structurally analyze, and the Functional groups visualized thus providing chemically meaningful interpretability of model predictions.
- This study highlights the value of combining machine learning with cheminformatics tools for toxicity and bioactivity prediction.
