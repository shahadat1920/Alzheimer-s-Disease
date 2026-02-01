# Alzheimer's Disease
This project follow high dimensional gene expression and DNA methylation dataset . Throughout our project we analysis  and filter out risk genes associated with AD .

Project Goals : 
• To integrate multi-omics datasets from two different brain tissues using a novel feature selection method.
• To develop robust and accurate machine learning (ML) and deep learning (DL) models for early prediction of Alzheimer’s disease.
• To identify potential risk genes associated with Alzheimer’s disease.
• To ensure model interpretability for reliable clinical applications.

Woking Flow : 
<img width="1632" height="1171" alt="image" src="https://github.com/user-attachments/assets/812d4bf7-7618-4c77-aae8-0ddcc5debab7" />

DEGs and DMPs Selection: 
High-dimensional data from multi-omics datasets requires appropriate gene selection techniques to create precise models and gain a better understanding of high-risk genes linked to complicated neurological disorders. This study's main goal is to use appropriate feature selection techniques to identify the genes that pose the most danger. This was accomplished by identifying the key predictors of early AD disease using traditional, straightforward, yet innovative methods.
Since gene expression and DNA methylation profiles come from separate parts of the brain and have different properties, it is difficult to combine them into a single feature set. There are significant differences in their statistical distributions, data generating methods, and biological importance. We address this by defining two categories of features: CpG sites from DNA methylation and genes from expression profiles. Usually, these datasets have a high-dimensional low-sample-size (HDLSS) characteristic, meaning that there are many more features than samples. This well-known challenge often leads to overfitting and unstable gradients when directly applied
9
in phenotype prediction using genetic data, making it difficult for conventional machine learning models to generalize effectively. Thus, robust feature selection is required to reduce dimensionality and control overfitting. In this study, we adopt a biologically driven strategy by focusing on differentially expressed genes (DEGs) and differentially methylated positions (DMPs). Unlike conventional feature selection methods such as PCA, mRMR, and ANOVA, which merely reduce feature space without preserving biological interpretation, our approach accounts for biological processes and cross-omics interactions. DNA methylation plays a regulatory role in modulating nearby gene expressions, a relationship that standard algorithms cannot capture. Our feature selection framework consists of two steps. First, DEGs and DMPs are identified using the Limma package, applying the thresholds fold change ≥ 0.75 and p-value < 0.05. Limma, widely applied in microarray analysis, has also been adapted for DNA methylation studies [31]. This step initially selected 4,319 CpG sites as Differentially 53 genes are classified as Differentially Expressed Genes (DEGs) and Methylated Positions (DMPs). Since methylation in these promoter regions has a significant impact on controlling gene activity, we further limit our selection to CpG sites located within 1500 base pairs of the transcription start site (TSS) gene to refine DMPs. Second, we combine DEGs and DMPs by utilizing their gene-level intersection. The recognized link between promoter methylation and gene suppression is reflected in this tactic: a gene that exhibits differential expression and concurrently has hyper- or hypo methylation in its promoter region is probably highly linked to disease pathology. Although this regulation pattern is not strictly followed by all genes, our approach does not rely on idealized assumptions and may accommodate a variety of biological events. In the end, a gene is deemed a feature if its methylation and expression patterns deviate markedly from those of normal controls. It is important to note that the prefrontal cortex of patients with late-onset Alzheimer's disease was used to produce gene expression and DNA methylation profiles rather than the same samples. Following the merged datasets, we had 609 samples in total of 17 genes where 225 of which matched normal controls and 384 of which were associated with Alzheimer's disease.

RF Nodel : 
The following random forest algorithm has been done for our study:
Input: Dataset D, the number of trees NT, and the threshold T of Gini impurity.
Output: A random forest for i = 1 to NT:
1)
Draw a bootstrap sample Di of size n from the training set D.
2)
Construct a decision tree of the bootstrapped data recursively from the root node.
Repeatedly perform the following steps until the Gini impurity is less than T:
11
a) Randomly select a subset of √m features.
b)
For j = 1 to √m:
• Compute Gini impurity for feature xj.
c)
As the split attribute and split value, select the feature and value with the lowest Gini impurity.
d)
Split the internal node into two child nodes according to the split feature and value.

Results : 

<img width="751" height="450" alt="image" src="https://github.com/user-attachments/assets/13d7ce4e-29d8-451a-ad7b-dffc4397a464" />


<img width="1433" height="950" alt="image" src="https://github.com/user-attachments/assets/d4e4a361-8cb0-4229-9477-bdcf6f6f4a1e" />

<img width="1491" height="751" alt="image" src="https://github.com/user-attachments/assets/a54299de-ac82-4f0a-b05e-16952fcb231e" />

<img width="1351" height="595" alt="image" src="https://github.com/user-attachments/assets/b62b59f2-f6cf-4919-98a5-6b6580c04ca9" />

<img width="546" height="370" alt="image" src="https://github.com/user-attachments/assets/4d47280e-6882-418a-91e8-02e636192f06" />









