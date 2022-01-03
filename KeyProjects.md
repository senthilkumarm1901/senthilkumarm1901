## The following are my key work projects 

### Project #1: Aspect-based Sentiment Analysis

 **Project Objective** : <br>  
 - To build a reusable **Sequence Text Classification ML Pipeline**
     - where free-text is converted into **(Aspect, Sentiment)** pairs
     - where the # of Aspect labels are typically more than 25
     - which has easy to use human-in-the-loop annotation scripts that can 
         - do efficient clustering of yet-to-be labeled data and
         - augment low volume classes
     - which yeilds 90%+ F1 score with minimal annotated data (possible with Transfer Learning)
  
 
 **I/P and O/P**: <br>
 
- **Example I/P**:
     > "The representative  who initially spoke with was very understanding but the dealer whom I was transferred to later was rude and unhelpful"
- **Example O/P**: <br>
  Part 1: <br>
     > "The representative who initially spoke with was very understanding" <br>
     > `Contact_Center_Agent` | `Positive`
  Part 2: <br>
     > "but the dealer whom I was transferred to later was rude and unhelpful" <br>
     > `Dealer` | `Negative`
     
  
