# Transfer-learning based Overall Survival prediction conditional on Progression-Free Interval with TCGA RNA-seq expression and KEGG-pathways

Programming language: Python    
Requirements: Python 3.8.20 or higher

# Get Started

To get started, you first need to install all the required dependencies via pip:
```sh
pip install -r requirements.txt
```

## Example Datasets
To get started, you need to download example datasets from URLs as below:

[Train data](http://dataxlab.org/PASNet/train.csv) 

[Validation data](http://dataxlab.org/PASNet/validation.csv)

[Pathway Mask data](http://dataxlab.org/PASNet/pathway_mask.csv)

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
