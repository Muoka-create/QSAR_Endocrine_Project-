# Title
Predicting Estrogen Receptor Activity with Machine Learning: A QSAR Approach to Identify Potential Endocrine Disruptors
## Objective
This study aims to identify and proritize relevant structural features of the chemicals that may possess endocrine disrupting potential.
## Dataset
- Source: Tox21 ( NR-ER-LBD assays)
- Compounds: 199

- ## Methods
This study utilizes a machine learning workflow to develop a model for predicting endocrine disrupting potential of chemicals using their SMILES string and corresponding binary activity label (1=active, 0=inactive). The data was imported into python using the pandas library and basic inspection was performed to ensure data integrity. SMILES strings were converted into 2D molecular structures using RDKit. These molecular structures facilitate a more comprehensive evaluation of molecular properties. Feature selection was generated usig RDKit, and the molecules were assigned morgan fingerprints to numerically represent the chemical structures. These fingerprints served as molecular descriptors for the model. A Random forest algorithm was trained and the model performance was assessed using classification metrics such as accuracy, reciever operating characteristic area under the curve (ROC-AUC) and confusion matrix. RF was chosen based on its potential to handle class imbalance and its ability to provide important features that support interpretability. The trained model was used to generate predicted probabilities of estrogen receptors activity for compounds in the test set. To enhance interpretability, key compounds were further analyzed by visualizing their molecular structures while key functional groups such as carbonyl groups were highlighted using RDKit to provide qualitative insight into chemical features potentially associated with estrogen receptor activity.
## Results
 ![ROC Curve](Roc_curve.png)
 
-The RF model achieved an accuracy of 0.825, with the model able to reliably separate active from inactive compounds better than random guessing.The ROC curve demonstrates a favorable balance between sensitivity and specificity.

- Confusion Matrix: [[22, 1], [6, 11]] ![Confusion Matrix](Confusion_matrix.png)
  
## Top Predicted Active Compounds
![Top Predicted Compounds](Top_Predicted_Compunds.png)

The model generated probability scores for all compounds in the test set base on their endocrine disrupting potential. Compounds with the highest predicted probabilities were ranked to identify top predicted active molecules.
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
This study demonstrates the potential of QSAR and machine learning, specifically the RF model to rapidly and effectively screen chemicals based on their endocrine disruption activity. The approach integrates molecular fingerprints generation and predictive modeling, and this lead to a robust model demonstrating a strong performance (ROC-AUC = 0.78) with 0.82 accuracy. More importantly, top predicited active compounds were identified, analyzed, and their functional group were visualized, providing insights into the chemical features of the model predictions. The insights generated from this study can support early stage hazard identification, contribute to chemical safety assessment, and enhance regulatory decision process. It also provides a trasition into more cost-effective and ethical approach, minimizing the need of traditional animal testing.
