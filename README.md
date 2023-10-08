# Can Language Models be Instructed to Protect Personal Information?

Official Repository for [Can Language Models be Instructed to Protect Personal Information?](https://browse.arxiv.org/pdf/2310.02224.pdf)

Please also visit our [project page](https://llm-access-control.github.io/).
## Benchmark Details
### Protected Population (Textual)
The data files can be found in `population_protection_textual`. The data specification is found below.
```entity_id (str): Wikidata ID
entity (str): name of the entity
question (str): question about the entity
answer (list): list of possible answers (taken from PopQA / TriviaQA)
attribute (str): population - taken from
    {
     citizenship = Italian,
     citizenship = Japanese,
     citizenship = Norwegian, 
     citizenship = Swiss, 
     age < 18 (minor), 
     age > 65 (senior citizen), 
     occupation = lawyer, 
     occupation = judge, 
     occupation = physician, 
     occupation = politician, 
     position_held = President of the U.S., 
     position_help = U.S. Representative, 
     position_held = Vice President of the U.S.
    }
cluster (str): in_group or out_group
data_id (str): identifier
```

### Protected Information (Textual)
The data files can be found in `information_protection_textual`. Questions are split based on Wikidata-defined categories The data specification is found below.
```question (str): question about the entity
answer (list): list of possible answers (string format) constructed from Wikidata (PopQA+)
raw (list): list of possible answers (Wikidata identifier format) constructed from Wikidata (PopQA+)
cluster (str): in_group or out_group
data_id (str): identifier
```

### Protected Population (Visual)
The data files can be found in `population_protection_visual`. You must separately download the images from the [KVQA dataset](http://malllabiisc.github.io/resources/kvqa/). Populations included are citizenships of Germany, India, Japan, and the United Kingdom. The data specification is found below.
```data_id (int): identifier
question (str): question about the entity
answer_eval (list): answer (taken from KVQA)
answer_text (str): answer (taken from KVQA)
qid (list): entity's Wikidata ID
entity_name (str): name of the entity
image_path (str): KVQA image path
org_data_id (str): KVQA identifier
cluster (str): in_group or out_group
```

### Protected Information (Visual)
The data file can be found in `information_protection_visual`. You must separately download the images from the [OVEN dataset](https://github.com/edchengg/oven_eval/tree/main/image_downloads). All questions are pulled from the [InfoSeek dataset](https://github.com/open-vision-language/infoseek). The protected information class is geolocation. The data specification is found below.
```data_id (str): identifier
image_id (str): OVEN identifier
question (str): InfoSeek question about the entity
answer_text (list): acceptable answers (taken from InfoSeek)
answer_eval (list): acceptable answers with variations (taken from Infoseek)
cluster (str): in_group or out_group
```

## Citation 
Please cite if you use our benchmark in your work.

    @misc{chen2023language,
        title={Can Language Models be Instructed to Protect Personal Information?}, 
        author={Yang Chen and Ethan Mendes and Sauvik Das and Wei Xu and Alan Ritter},
        year={2023},
        eprint={2310.02224},
        archivePrefix={arXiv},
        primaryClass={cs.CL}
    }