# Implicit reasonings for a given claim and premise
This repository contains data and supplementary materials for generating implicit reasonings for any argument (comprising claim and premise). 
  
  
### How to understand the data and code?

#### Data: Implick Dataset
`Implick dataset` (folder) contains data in a csv format that is directly obtained from AMT (Amazon Mechanical Turk). 
For topic specific data refer to `topic_specific_data` (folder). The first row is column headers and each row is then a single instance in the following form:

| sentence_1  | sentence_2 | 
| ------------- | ------------- |
| We should legalize cannabis, Buying illegal marijuana on the street is unsafe. It could be laced with unknown substances. Legal marijuana is regulated for consumer safety	| Legalizing cannabis cause legal, regulated prices to outcompete street prices cause make marijuana safer |

where **sentence_1** comprises claim and premise (separated by comma if necessary) and **sentence_2** comprises the necessary information from **claim** and **premise** along with implicit knowledge and causal labels.

### How to use the dataset for generation?
The repository contains 3 generation models: XL_net, BART and GPT2. 

* FT GPT2 and generate
  * To finetune GPT2, use data in `train_test_data` (folder). 
  * To generate with the finetuned model, you can either run run_lm_generate.sh or lm_generate.py with appropriate hyperparameters. 

* FT BART and Data coming soon...

---
