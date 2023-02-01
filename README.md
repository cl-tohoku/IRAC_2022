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

```
@inproceedings{singh-etal-2022-irac,
    title = "{IRAC}: A Domain-Specific Annotated Corpus of Implicit Reasoning in Arguments",
    author = "Singh, Keshav  and
      Inoue, Naoya  and
      Mim, Farjana Sultana  and
      Naito, Shoichi  and
      Inui, Kentaro",
    booktitle = "Proceedings of the Thirteenth Language Resources and Evaluation Conference",
    month = jun,
    year = "2022",
    address = "Marseille, France",
    publisher = "European Language Resources Association",
    url = "https://aclanthology.org/2022.lrec-1.499",
    pages = "4674--4683",
}
```

For questions or comments email us: keshav.singh29@gmail.com
