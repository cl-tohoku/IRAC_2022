# IRAC: A Domain-specific Annotated Corpus of Implicit Reasoning in Arguments 

This repository contains data for generating implicit reasonings for a given argument (i.e., a pair of claim and premise) as described in Singh et.al. 2022. 
    
### Data: Implick Dataset
This repository contains topic specific data from the IRAC dataset as arrays in json format that is obtained from AMT (Amazon Mechanical Turk). 
Each array item corresponds to one Claim and Premise pair as key and a list of collected Implicit Reasonings (IR) as values. 

```json
{
    "Claim, Premise1" : ["IR1", "IR2", ...],
    "Claim, Premise2" : ["IR1", "IR2", ...]
 }
 ```

where, Claim and Premise are separated by comma if necessary and Implicit reasoning (IR) comprises keywords from **claim** (action entity) and **premise** (outcome entity) along with implicit causal knowledge and causal labels.

### How to use the dataset for generation?
The dataset can be used with any Language model as long as it fits the correct input format. For instance, 

* FT BART and generate
  * To finetune BART, 
    * Input to encoder: claim [SEP] premise
    * Input to decoder: IR (We randomly sample a single IR from a bunch of available IRs for that specific claim and premise pair)

Note: We used huggingface implementations as our primary source of transformer based langauge models. 

If you use our dataset, please cite:

Keshav Singh, Naoya Inoue, Farjana Sultana Mim, Shoichi Naito and Kentaro Inui: A Domain-specific Annotated Corpus of Implicit Reasoning in Arguments. Accepted at: LREC 2022.

For questions or comments email us: keshav.singh29@gmail.com
