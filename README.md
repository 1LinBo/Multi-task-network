# Transfer-learning based Overall Survival prediction conditional on Progression-Free Interval with TCGA RNA-seq expression and KEGG-pathways

Programming language: Python    
Requirements: Python 3.8.19 or higher

# Get started

## Example datasets and the code for this method
To get started, you need to download example datasets and the code for this method from URLs as below:

[relevantdata.txt](https://github.com/1LinBo/Multi-task-network/blob/main/relevantdata.txt): this file includes 31 cancer types from the TCGA pan-cancer dataset, which are used for pre-training the multi-task model. The dataset contains a total of 4033 columns, including: 4028 genes (from the 186 KEGG pathways), cancertype, event2 (censoring indicator for Overall Survival, T2 (Overall Survival time), event1 (censoring indicator for Progression-Free Interval), T1 (Progression-Free Interval time).

[targetdata.txt](https://github.com/1LinBo/Multi-task-network/blob/main/targetdata.txt): this file includes the SKCM cancer type from the TCGA pan-cancer dataset, which is used for fine-tuning the multi-task model. The dataset contains a total of 4033 columns, including: 4028 genes (from the 186 KEGG pathways), cancertype, event2 (censoring indicator for Overall Survival, T2 (Overall Survival time), event1 (censoring indicator for Progression-Free Interval), T1 (Progression-Free Interval time).

[Multi-task model.ipynb](https://github.com/1LinBo/Multi-task-network/blob/main/Multi-task%20model.ipynb): this file includes the general usage of this method in terms of data preprocessing, creation of neural networks, model training, and evaluation procedure.

[eval.py](https://github.com/1LinBo/Multi-task-network/blob/main/eval.py): this file includes the classes for evaluation metrics (C-index and IBS), which are used in Multi-task model.ipynb.

[requirements.txt](https://github.com/1LinBo/Multi-task-network/blob/main/requirements.txt): this file includes all the required Python dependencies needed to run the code in this repository.

[mask.pt](https://github.com/1LinBo/Multi-task-network/blob/main/mask.pt): this file includes the mapping between 4028 genes and the 186 KEGG pathways. It is mainly used for the gene–pathway sparse connection layer, which is used in Multi-task model.ipynb.


## Model training and evaluation

After downloading the example datasets and the code for this method, you need to install all the required Python dependencies listed in requirements.txt. Then, you can run Multi-task model.ipynb, which demonstrates the general usage of this method, including data preprocessing, neural network creation, model training, and evaluation.

