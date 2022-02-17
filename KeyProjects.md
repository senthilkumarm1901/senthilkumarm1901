## Some of my NLP Projects

### Project #1: Aspect-based Sentiment Analysis

<blockquote>
 <details><summary><b>Project Summary</b></summary>
 
  <br>
  
 - Built a reusable **Sequence Text Classification ML Pipeline**
     - which used BERT-fine-tuning 
     - where free-flowing text was converted into **(Aspect, Sentiment)** pairs
     - where the # of Aspect labels are typically more than 25
     - which had easy to use human-in-the-loop annotation scripts that can 
         - do efficient clustering of yet-to-be labeled data and
         - augment low volume classes after initial round of annotations
     - which yeilded 90%+ F1 score with minimal annotated data 
     - which had scripts to monitor performance of model 

- Built a comprehensive Docker Image that hosted the DL models as well as Spark
  
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

<details><summary><b>Technology Stack</b></summary>
 
 <br>
 
 ![Python](https://img.shields.io/badge/-Python-green?style=for-the-badge=white) ![PySpark](https://img.shields.io/badge/-PySpark-green?style=for-the-badge=white) ![HuggingFace Transformers](https://img.shields.io/badge/-Transformers-blue?style=for-the-badge=white) ![SpaCy](https://img.shields.io/badge/-SpaCy-green?style=for-the-badge=white) ![PyTorch](https://img.shields.io/badge/-PyTorch-brown?style=for-the-badge=white) ![TFHub](https://img.shields.io/badge/-TFHub-green?style=for-the-badge=white)  ![Docker](https://img.shields.io/badge/-Docker-green?style=for-the-badge=white) 
 
 </details> 
 
<details>
	 <summary> <b>Detailed Pipeline </b> </summary>
	 
 <br>
	 
 ![](images/proj1_full_pipeline.png)
	 
  <details><summary>*Text2Embedding Sub-pipeline</summary>
 
  ![sub-pipeline1](images/proj1_spark_plus_embedding.png)

  </details>

  <details><summary>*Efficient Annotation Sub-pipeline</summary>
 
  ![sub-pipeline1](images/proj1_annotation_pipeline.png)
 
  </details>
 
 </blockquote>

### Project #2: Personally Identifiable Information (PII) Detection using NER

<blockquote>
 <details><summary><b>Project Summary</b></summary>
 
  <br>
  
- To replace PII in text data
    - by building a **Named Entity Recognition (NER)** system that can detect PII in text comments
- Built a Rules-based NER to bootstrap Training data
  
</details>
 
<details><summary><b>I/P and O/P</b></summary>
 
- **Example I/P**:
     > "Please drop my 2019 Focus after service to 2109 Hershell Hollow Road, Nashville, Tennesse. You can reach me at +1 854-789-1234 or gary_kirsten1978@gmail.com - Gary Kirsten" ( a made-up example)
- **Example O/P**: <br>
 
     > Please drop my `{{MODEL_YEAR}}` `{{NAMEPLATE}}` after service to `{{ADDRESS}}`. You can reach me at `{{PHONE_NUMBER}}` or `{{EMAIL}}` - `{{PERSON_NAME}}`
 
</details>
  
<details><summary><b>Business/Technical Benefits</b></summary>

- PII Annonymization can aid in less restricted use of the data
- Spacy's Roberta-base Model circumvented the truncation restriction of the transformers max sequence length problem. Refer [Link](https://spacy.io/api/transformer#span_getters)

 </details>

<details><summary><b>Technology Stack</b></summary>
 
 <br>
 
![Python](https://img.shields.io/badge/-Python-green?style=for-the-badge=white) ![HuggingFace Transformers](https://img.shields.io/badge/-Transformers-blue?style=for-the-badge=white) ![SpaCy](https://img.shields.io/badge/-SpaCy-green?style=for-the-badge=white) ![Poetry](https://img.shields.io/badge/-Poetry-brown?style=for-the-badge=white) ![Docker](https://img.shields.io/badge/-Docker-green?style=for-the-badge=white) ![Kubernetes](https://img.shields.io/badge/-Kubernetes-blue?style=for-the-badge=white) ![FastAPI](https://img.shields.io/badge/-FastAPI-orange?style=for-the-badge=white)
 
 </details> 
 
 <details>
	 <summary> <b>Detailed Pipeline </b> </summary>
	 
 <br>
	 
 ![](images/proj2_pii_ner_main_pipeline.png)
	 
  <details><summary>*Rules-based NER Sub-pipeline</summary>
 
  ![sub-pipeline1](images/proj2_pii_nersub_pipeline1.png)

  </details>

  <details><summary>*Model-based NER Sub-pipeline</summary>
 
  ![sub-pipeline1](images/proj2_pii_nersub_pipeline2.png)
	  
  </details>
 </blockquote>


### Project #3: Unsupervised Text Data Clustering Pipeline

<blockquote>
 <details><summary><b>Project Summary</b></summary>
 
  <br>
  
- To build reusable Text Clustering pipelines  
    - with simpler Python APIs runnable inside docker images that can be used by non-NLP analysts 
    - to derive actionable insights from unlabeled text corpus using unsupervised clustering techniques
- The codebase was built on top of the main open source libraries 
    - PyTorch (Transformers, Sentence Transformers), Sklearn
  
</details>
 
<details><summary><b>Methodology Workflow</b></summary>

- Can Transfer Learning (TL) based pre-trained Sentence Models work for your data?
    - (1) If `Yes`
        - Employ TL-based Embedding & Hard Clustering
        - E.g.: Customer comments, corpora like Wiki,Brown Corpus, Web Forum discussions   
    - (2) If `No` (it is a domain-specific data)
        - Employ the best of Traditional Embedding and Topic Modeling
        - E.g.: Technician logs, domain-specific survey
 
**Methodology 1**: <br>
- *TL-based Embedding & Hard Clustering*
    - Embedding options: Employ any good Sentence Embedding technique
        - SentenceBERT (`sentence transformers` library)
        - Universal Sentence Coder (via TFHub)
- Indexing: Approx. Nearest Neighbours (ANNoy) on top of Embedding
- Clustering options: KMeans OR HDBSCAN
 
**Methodology 2**: <br>
- *Traditional Embedding and Topic Modeling*
    - Simple-but-Effective (arguable) Traditional Embedding Used:
        - Custom Vectorizer Pipeline
            - Spacy-tokenized
            - Lemmatized
            - TF-IDF Vectorizor
    - Topic Modeling Variant Options:
        - Simple LDA
        - Semi-supervised or Guided or Seeded LDA
    - pyLDAvis Visualization
        - Inter-topic Distance Map & Topic Occurence Freq
        - per-Topic Word Distribution
 
</details>
 

<details><summary><b>Technology Stack</b></summary>
 
 <br>
 
![Sentence Transformers](https://img.shields.io/badge/-SentenceTransformers-green?style=for-the-badge=white) ![HuggingFace Transformers](https://img.shields.io/badge/-Transformers-blue?style=for-the-badge=white) ![SpaCy](https://img.shields.io/badge/-SpaCy-green?style=for-the-badge=white) ![Sklearn](https://img.shields.io/badge/-Sklearn-green?style=for-the-badge=white) ![Docker](https://img.shields.io/badge/-Docker-green?style=for-the-badge=white) ![Kubernetes](https://img.shields.io/badge/-Kubernetes-blue?style=for-the-badge=white) ![Streamlit](https://img.shields.io/badge/-Streamlit-yellow?style=for-the-badge=black)  
 
 </details> 
 
 </blockquote>
 
 
### Project #4: A Unsupervised + Supervised NLP Semantic Search Pipeline
(inspired by the workings of a NLP QA system but for Semantic Search) 
 
### Project #5: Social Media Data Analysis
  
### Project #6: Multi-GPU Neural Machine Translation (NMT) Inference Pipeline

### Project #7: Analysis of Speech2Text Models
(Comparison of Results of Paid Speech2Text APIs and Open-source DeepSpeech Pre-trained Models)
