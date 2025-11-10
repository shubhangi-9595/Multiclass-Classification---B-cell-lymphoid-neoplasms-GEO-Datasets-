Step 1 - Run "project_5_aml.Rmd" on RStudio. Make sure the packages readxl, DESeq2, data.table, tibble and GEOquery from Bioconductor are installed in RStudio.

Step 2 - The "project_5_aml.Rmd" from the source folder will generate "combined_exp_matrix.csv", "metadata.txt", "Subtypes.csv", "Subtypes.csv" and "Differ_exp_genes_aml.csv" files through this step.

Step -3 Run "GSE183030.Rmd" on RStudio, Load "GO_Annotated.csv" file in it. "similar.csv" is generated from this code.

Step 2 - Load "Differ_exp_genes_aml.csv", "Subtypes1.csv", "Subtypes", "GO_Annotated.csv", "similar.csv" into the "assignment5.ipynb" file from the source folder and run the file.

# Project Overview  
This project develops a machine learning classifier for **small B-cell lymphoid neoplasms (SBCLNs)** using gene expression data from 8 GEO datasets. The goal is to improve diagnostic accuracy compared to previously built models by identifying highly and differentially expressed genes and training a Gradient Boosting model.  

## Data  
- **Samples:** 718 total (645 SBCLN, 73 control)  
- **Subtypes:** CLL/SLL, FL, MCL, MZL, LPL/WM, Other, Normal  
- **Source:** Gene Expression Omnibus (GEO) datasets  
- **Preprocessing:**  
  - Gene expression matrices retrieved using **GEOquery** in R  
  - DESeq2 used for differential expression analysis (~26,000 genes identified)  
  - Labels assigned for 7 classes  
  - Feature scaling applied  
  - Class imbalance handled using **SMOTE** after splitting into train/test sets  

## Methods  
- **Gradient Boosting:**  
  - Sequentially trains decision trees to correct previous errors  
  - Hyperparameter tuning identified 500 trees as optimal (AUC = 0.95)  
- **Evaluation:**  
  - 10-fold cross-validation  
  - Confusion matrix for multi-class classification  
  - ROC curves for each class  
  - Macro-average sensitivity and specificity  

## Key Tools & Libraries  
- **R:** GEOquery, DESeq2, hgu133plus2.db, AnnotationDbi  
- **Python:** Gradient Boosting implementation and model evaluation  

## Results  
The model identifies important genes for SBCLN classification and its performance is compared with prior studies. Detailed results, including feature importance and evaluation metrics, are available in the project report. 
