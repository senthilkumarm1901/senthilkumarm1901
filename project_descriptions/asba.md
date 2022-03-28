## Aspect-based Sentiment Analysis

### Project Summary

- Built a reusable Sequence Classification ML Pipeline which converts customer comments into trackable `Aspect` and `Sentiment` pairs
- Highlights:
    - ML Pipeline used BERT-fine-tuning  
    - ML Pipeline had easy to use human-in-the-loop annotation scripts that can 
        - do efficient clustering of yet-to-be labeled data and
        - augment low volume classes after initial round of annotations
    - The Pipeline helped yeilding 85%+ F1 score with minimal annotated data for more than 25+ classes
    - There were also scripts to `monitor` performance of model 
- Built a comprehensive Docker image that hosted the DL models as well as Spark-on-Docker preprocessing. 


### I/P and O/P

- **Example I/P**:
     > "The representative  who initially spoke with was very understanding but the dealer whom I was transferred to later was rude and unhelpful"
- **Example O/P**: <br>
  Part 1: <br>
     > "The representative who initially spoke with was very understanding" <br>
     > `Contact_Center_Agent` | `Positive` <br>
 
  Part 2: <br>
     > "but the dealer whom I was transferred to later was rude and unhelpful" <br>
     > `Dealer` | `Negative`


### Business/Technical Benefits


- The codebase was used to build *30+ different Text Classification Models*
    - using the same ML pipeline/framework where each model had 20-30 classes to predict 
- Our repo's framework and models warranted far less human annotated data (than using a typical ML model)
- This was possible because both **Feature Extraction** :snowflake: (for clustering) and **Fine-tuning** :fire:

### Technology Stack

 ![Python](https://img.shields.io/badge/-Python-green?style=for-the-badge=white) ![PySpark](https://img.shields.io/badge/-PySpark-green?style=for-the-badge=white) ![HuggingFace Transformers](https://img.shields.io/badge/-Transformers-blue?style=for-the-badge=white) ![SpaCy](https://img.shields.io/badge/-SpaCy-green?style=for-the-badge=white) ![PyTorch](https://img.shields.io/badge/-PyTorch-brown?style=for-the-badge=white) ![TFHub](https://img.shields.io/badge/-TFHub-green?style=for-the-badge=white)  ![Docker](https://img.shields.io/badge/-Docker-green?style=for-the-badge=white) 
 
### Detailed Pipeline

 ![](../images/proj1_full_pipeline.png)


  <details><summary>*Text2Embedding Sub-pipeline</summary>
 
  ![sub-pipeline1](../images/proj1_spark_plus_embedding.png)

  </details>
  
   
   <details><summary>*Efficient Annotation Sub-pipeline</summary>
 
  ![sub-pipeline1](../images/proj1_annotation_pipeline.png)
 
  </details>

