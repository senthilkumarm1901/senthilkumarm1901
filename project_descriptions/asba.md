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
- Built a comprehensive Docker Image that hosted the DL models as well as Spark
