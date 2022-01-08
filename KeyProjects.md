## The following are my key work projects 

### Project #1: Aspect-based Sentiment Analysis

<blockquote>
 <details><summary><b>Project Summary</b></summary>
 
 - Built a reusable **Sequence Text Classification ML Pipeline**
     - which used BERT-fine-tuning 
     - where free-text was converted into **(Aspect, Sentiment)** pairs
     - where the # of Aspect labels are typically more than 25
     - which had easy to use human-in-the-loop annotation scripts that can 
         - do efficient clustering of yet-to-be labeled data and
         - augment low volume classes after initial round of annotations
     - which yeilded 90%+ F1 score with minimal annotated data 
     - which had scripts to monitor performance of model 

</details>
 
<details><summary><b>I/P and O/P</b></summary>
 
- **Example I/P**:
     > "The representative  who initially spoke with was very understanding but the dealer whom I was transferred to later was rude and unhelpful"
- **Example O/P**: <br>
  Part 1: <br>
     > "The representative who initially spoke with was very understanding" <br>
     > `Contact_Center_Agent` | `Positive` <br>
 
  Part 2: <br>
     > "but the dealer whom I was transferred to later was rude and unhelpful" <br>
     > `Dealer` | `Negative`

</details>
  
<details><summary><b>Business/Technical Benefits</b></summary>

- The codebase was used to build *30+ different Text Classification Models*
    - using the same ML pipeline/framework where each model had 20-30 classes to predict 
- Our repo's framework and models warranted far less human annotated data (than using a typical ML model)
- This was possible because both **Feature Extraction** :snowflake: (for clustering) and **Fine-tuning** :fire: (for BERT Fine-tuning was used

 </details>

<details><summary><b>Key Tools</b></summary>
 
 ![Python](https://img.shields.io/badge/-Python-green?style=for-the-badge=white) ![PySpark](https://img.shields.io/badge/-PySpark-green?style=for-the-badge=white) ![HuggingFace Transformers](https://img.shields.io/badge/-Transformers-blue?style=for-the-badge=white) ![SpaCy](https://img.shields.io/badge/-SpaCy-green?style=for-the-badge=white) ![PyTorch](https://img.shields.io/badge/-PyTorch-brown?style=for-the-badge=white) ![TFHub](https://img.shields.io/badge/-TFHUB-green?style=for-the-badge=white)  ![Docker](https://img.shields.io/badge/-Docker-green?style=for-the-badge=white) 
 
 </details> 
 
 </blockquote>
