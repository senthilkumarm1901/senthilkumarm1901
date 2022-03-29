## Personally Identifiable Information (PII) Detection using Named Entity Recognition (NER)

### Project Summary

- Goal: To replace PII in text data
    - by building a **NER** system that can detect PII in text comments and
    - can result in less restricted use of the data
- Annonymized PII in text data
    - by building a NER system using both **RoBerta Fine-tuned Transformer model** and Rules-based logic
- Bootstrapped the training data using Spacy rules (thus easing the annotation process by not starting labeling from scratch) 
- Achieved an F1 score of 89% for detecting the PII entities
- Deployed an asynchronous* Inference REST API (using FastAPI and K8s) that can be plugged into multiple applications

### I/P and O/P

- **Example I/P**:
     > "Please drop my 2019 Focus after service to 2109 Hershell Hollow Road, Nashville, Tennesse. You can reach me at +1 854-789-1234 or gary_kirsten1978@gmail.com - Gary Kirsten" ( a made-up example)
- **Example O/P**: <br> 
     > Please drop my `{{MODEL_YEAR}}` `{{NAMEPLATE}}` after service to `{{ADDRESS}}`. You can reach me at `{{PHONE_NUMBER}}` or `{{EMAIL}}` - `{{PERSON_NAME}}`

### Business/Technical Benefits

- PII Annonymization can aid in less restricted use of the data
- Spacy's Roberta-base Model circumvented the truncation restriction of the transformers max sequence length problem. Refer [Link](https://spacy.io/api/transformer#span_getters)

### Technology Stack

![Python](https://img.shields.io/badge/-Python-green?style=for-the-badge=white) ![HuggingFace Transformers](https://img.shields.io/badge/-Transformers-blue?style=for-the-badge=white) ![SpaCy](https://img.shields.io/badge/-SpaCy-green?style=for-the-badge=white) ![Poetry](https://img.shields.io/badge/-Poetry-brown?style=for-the-badge=white) ![Docker](https://img.shields.io/badge/-Docker-green?style=for-the-badge=white) ![Kubernetes](https://img.shields.io/badge/-Kubernetes-blue?style=for-the-badge=white) ![FastAPI](https://img.shields.io/badge/-FastAPI-orange?style=for-the-badge=white)

### Detailed Pipeline

 ![](../images/proj2_pii_ner_main_pipeline.png)
 
   <details><summary> Rules-based NER Sub-pipeline</summary>
 
  ![sub-pipeline1](../images/proj2_pii_nersub_pipeline1.png)

  </details>

  <details><summary> Model-based NER Sub-pipeline</summary>
 
  ![image](https://user-images.githubusercontent.com/24909551/160360810-92e093e1-8d9f-4c18-90ac-e4606925b4f1.png)

  ![image](https://user-images.githubusercontent.com/24909551/160360867-3fd67ec6-51ea-4a6d-a6e3-5848dcccc036.png)

  
  </details>
