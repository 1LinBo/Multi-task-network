# Transfer-learning based Overall Survival prediction conditional on Progression-Free Interval with TCGA RNA-seq expression and KEGG-pathways

Programming language: Python    
Requirements: Python 3.8.20 or higher

# Get started

## Example datasets and the code for this method
To get started, you need to download example datasets and the code for this method from URLs as below:

[relevantdata.txt](https://github.com/1LinBo/Multi-task-network/blob/main/relevantdata.txt): this file includes 31 cancer types from the TCGA pan-cancer dataset, which are used for pre-training the multi-task model. The dataset contains a total of 4033 columns, including: 4028 genes (from the 186 KEGG pathways), cancertype, event2 (censoring indicator for Overall Survival, T2 (Overall Survival time), event1 (censoring indicator for Progression-Free Interval), T1 (Progression-Free Interval time).

[targetdata.txt](https://github.com/1LinBo/Multi-task-network/blob/main/targetdata.txt): this file includes the SKCM cancer type from the TCGA pan-cancer dataset, which is used for fine-tuning the multi-task model. The dataset contains a total of 4033 columns, including: 4028 genes (from the 186 KEGG pathways), cancertype, event2 (censoring indicator for Overall Survival, T2 (Overall Survival time), event1 (censoring indicator for Progression-Free Interval), T1 (Progression-Free Interval time).

[Multi-task model.ipynb](https://github.com/1LinBo/Multi-task-network/blob/main/Multi-task%20model.ipynb)

[eval.py](https://github.com/1LinBo/Multi-task-network/blob/main/eval.py)

[requirements.txt](https://github.com/1LinBo/Multi-task-network/blob/main/requirements.txt)


To get started, you first need to install all the required dependencies via pip:
```sh
pip install -r requirements.txt
```



## Empirical Search for Hyperparameters 
Run_EmpiricalSearch.py: to find the optimal pair of hyperparmaters for PASNet before performing cross validation. PASNet is trained with the inputs from train.csv. Hyperparameters are optimized by emipirical search with validation.csv.
## 5-fold Cross Validation
Run.py: to train and evaluate the model performance based on 10 times 5-fold cross validation.

***Example usage***

**Direct learning**

python direct_learning_subsettarget.py --config 'example_config/direct_learning_train_config.json'   
python direct_learning_eval.py --config 'example_config/direct_learning_eval_config.json'      


**Combined learning**

python combined_learning.py  --config 'example_config/combined_learning_train_config.json'   
python neuralnet_eval.py --config 'example_config/combined_eval_config.json'   


**Regular pre-train fine-tune**

python pretrain_coxnet.py --config  'example_config/pretrain_coxnet_config.json'   
python finetune.py --config 'example_config/fintune_config.json'   
python neuralnet_eval.py --config 'example_config/finetune_eval_config.json'   


**few-shot meta-learning**    
python fewshot_metatrain.py --config 'example_config/fewshot_meta_config.json'   
python fewshot_finaltrain_eval.py --config 'example_config/fewshot_finaltrain_config.json'  
