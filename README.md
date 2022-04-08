# Implicit reasonings for a given claim and premise
This repository contains data and supplementary materials for generating implicit reasonings for any argument (comprising claim and premise). 
  
  
### How to understand the data and code?

#### Data: Implick Dataset
This repository contains topic specific data from the IRAC dataset as arrays in json format that is obtained from AMT (Amazon Mechanical Turk). 
Each array item corresponds to one Claim and Premise pair as key and a list of collected Implicit Reasonings (IR) as values. 

| Claim, Premise : [IR1, IR2, IR3, ...] | 
| ------------- | ------------- |

where claim and premise are separated by comma if necessary and Implicit reasoning comprises keywords from **claim** (action entity) and **premise** (outcome entity) along with implicit causal knowledge and causal labels.

### How to use the dataset for generation?
The dataset can be used with any Language model as long as it fits the correct input format. For instance, 

* FT BART and generate
  * To finetune BART, 
    * Input to encoder: claim [SEP] premise
    * Input to decoder: IR (We randomly sample a single IR from a bunch of available IRs)

Note: We used huggingface implementations as our primary source of transformer based langauge models. 
