### An NLP Semantic Search Pipeline
(inspired by the workings of a NLP QA system but for Semantic Search) 

### Project Summary

- Goal: To create "digital threads" for connecting automotive data sources
	- which has technician comments about issues before the launch of a vehicle,
	- by assigning semantically matching common part categories to every issue in both data sources 
    
- Business Context
	- The data sources contain technician comments about issues in a vehicle development before the final launch of a vehicle. 
	- The connection is established through NLP techniques (like semantic search, NER) where the right parts are attributed to each issue. 
	- Parts attribution acts a common language - the thread - joining two or more data sources. 
	- The creation of a digital thread helps in prioritizing issues that might delay launch by predicting its prevalence in downstream databases.
	- Every unsolved issues closer to the launch can impact hugely on delivery timelines


### Technology Stack
 
![Sentence Transformers](https://img.shields.io/badge/-SentenceTransformers-green?style=for-the-badge=white) 
![HuggingFace Transformers](https://img.shields.io/badge/-Transformers-blue?style=for-the-badge=white) 
![SpaCy](https://img.shields.io/badge/-SpaCy-green?style=for-the-badge=white) 
![Sklearn](https://img.shields.io/badge/-Sklearn-green?style=for-the-badge=white) 
![Docker](https://img.shields.io/badge/-Docker-green?style=for-the-badge=white) 
![Kubernetes](https://img.shields.io/badge/-Kubernetes-blue?style=for-the-badge=white) 
![Streamlit](https://img.shields.io/badge/-Streamlit-yellow?style=for-the-badge=black)  
 


### Detailed Pipeline

![SBERT Source](https://raw.githubusercontent.com/UKPLab/sentence-transformers/master/docs/img/InformationRetrieval.png)

- Inspired by the above Retriever - Reader pipeline but strengthened it by ensembling results of 3 pairs of Retriever-Reader models wherein
    - the `Retriever` narrows down the search space and
    - the `Reader` zeros in on the right results

- Ensemble of 3 `Retriever-Reader` Models

![](../images/proj_3_semantic_search_main_pipeline.png)

<details><summary> Retriever Bi Encoder (RBE) pipeline</summary>

![](../images/proj3_semantic_search_sub_pipeline.png)

</details>
