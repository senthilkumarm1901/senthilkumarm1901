## Reusable Text Data Clustering Pipeline

### Project Summary

- Built reusable Text Clustering pipeline
    - with simpler Python APIs for non-NLP analysts 
    - to derive actionable insights from unlabeled text corpus using unsupervised clustering techniques
   
- The codebase was built on top of the main open source libraries 
    - PyTorch (Transformers, Sentence Transformers), Sklearn


### Methodology Workflow

- Can Transfer Learning (TL) based pre-trained Sentence Models work for your data?
    - (1) If `Yes`
        - Employ TL-based Embedding & Hard Clustering
            > E.g.: Customer comments, corpora like Wiki,Brown Corpus, Web Forum discussions   
    - (2) If `No` (it is a domain-specific data)
        - Employ the best of Traditional Embedding and Topic Modeling
            > E.g.: Technician logs, domain-specific survey
 
**Methodology 1**: **TL-based Embedding & Hard Clustering**
- Pipeline 1: `Feature Extraction based TL-powered Embedding` → `ANNoy` → `Hard Clustering`

    - Embedding options: Employ any good Sentence Embedding technique
        - SentenceBERT (`sentence transformers` library)
        - Universal Sentence Coder (via TFHub)
    - Indexing: Approx. Nearest Neighbours (ANNoy) on top of Embedding
    - Clustering options: KMeans OR HDBSCAN
 
**Methodology 2**: **Traditional Embedding and Topic Modeling**
- Pipeline 2: `Traditional Embedding` → `Soft Clustering` → `Visualize the Clusters`
    
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
