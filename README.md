# Social-network-graph-link-prediction

### Problem statement
Given a directed social graph, the model has to predict missing links to recommend users (Link Prediction in graph)

### Data Overview
Taken data from facebook's recruting challenge on kaggle https://www.kaggle.com/c/FacebookRecruiting  
Data contains two columns source and destination. The source and destination columns contain information about the 
users and a source, destination pair signifies that they are connected in the network. Here, 
a link between the user u1 and u2 denotes a 1-way relationship i.e u1 follows u2
    - Data columns (total 2 columns):  
    - source_node         int64  
    - destination_node    int64  
    
![raw_data](https://user-images.githubusercontent.com/16969797/120464231-560da400-c3ba-11eb-927d-caab81558ca4.png)

Above is the snapshot of the raw data in train.csv file. It only has two columns source_node and destination_node. This is a pure graph based link prediction problem as we have no other meta information

### Mapping the problem into supervised learning problem:
- Generated training samples of good and bad links from given directed graph. For each link got some features like no of followers, is he followed back, page rank, katz score, adar index, some svd fetures of adj matrix, some weight features etc. and trained ml model based on these features to predict link.

### Business objectives and constraints:  
- No low-latency requirement.
- Probability of prediction is useful to recommend highest probability links

### Performance metric for supervised learning:  
- F1 score
- Confusion matrix

**Precision:** Suggesting connections that are most likely to be correct <br>
**Recall:** We try and not to miss out any connections <br>
Since we want both precision and recall to be high, we shoose **F1 score** as a KPI along **Confusion matrix** to summarize 
the performance of the model

### References
- https://www.appliedaicourse.com/course/11/Applied-Machine-learning-course
- http://be.amazd.com/link-prediction/
- https://storage.googleapis.com/kaggle-forum-message-attachments/2594/supervised_link_prediction.pdf
- https://www.cs.cornell.edu/home/kleinber/link-pred.pdf
- https://www3.nd.edu/~dial/publications/lichtenwalter2010new.pdf
- https://kaggle2.blob.core.windows.net/forum-message-attachments/2594/supervised_link_prediction.pdf
- https://www.youtube.com/watch?v=2M77Hgy17cg
