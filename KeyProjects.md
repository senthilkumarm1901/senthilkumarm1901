## The following are my key work projects 

### Project #1: Aspect-based Sentiment Analysis

 **Project Summary** : <br>  
 - Built a reusable **Sequence Text Classification ML Pipeline**
     - which used BERT-fine-tuning base TL model (circa: 2019-20)
     - where free-text was converted into **(Aspect, Sentiment)** pairs
     - where the # of Aspect labels are typically more than 25
     - which had easy to use human-in-the-loop annotation scripts that can 
         - do efficient clustering of yet-to-be labeled data and
         - augment low volume classes after initial round of annotations
     - which yeilded 90%+ F1 score with minimal annotated data 
     - which had scripts to monitor performance of model 
  
 
 **I/P and O/P**: <br>
 
- **Example I/P**:
     > "The representative  who initially spoke with was very understanding but the dealer whom I was transferred to later was rude and unhelpful"
- **Example O/P**: <br>
  Part 1: <br>
     > "The representative who initially spoke with was very understanding" <br>
     > `Contact_Center_Agent` | `Positive` <br>
  Part 2: <br>
     > "but the dealer whom I was transferred to later was rude and unhelpful" <br>
     > `Dealer` | `Negative`
     
  
**Business/Technical<br> Benefits**: <br>

- The codebase was used to build *30+ different Text Classification Models*
    - using the same ML pipeline/framework where each model had 20-30 classes to predict 
- Our repo's framework and models warranted far less human annotated data (than using a typical ML model)
