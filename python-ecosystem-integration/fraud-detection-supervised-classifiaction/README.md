# Fraud Detection Classifier with GDS & Python

In [Neo4j Graph Data Science (GDS)](https://neo4j.com/docs/graph-data-science/current/) we can leverage graph algorithms to produce features for Machine learning (ML).  These features can be easily leveraged in external ML pipelines, AI frameworks, and Data Science workflows. 


## This Example
We use a real anonymized P2P dataset.  We manual label fraud risk users according to their relationships to previously flagged accounts.  We then engineer graph features and read into python to train a ML model to classify the fraud risk users without knowledge of previous system flagging. 

## Dataset
The source dataset is available as a Neo4j dump file. The dataset, along with directions for loading it, can be found [here](https://drive.google.com/drive/folders/1LaNFObKnZb1Ty8T7kPLCYlXDUlHU7FGa)

## Usage
Once you have the data in Neo4j you can use `stage.ipynb` to stage the demo and `demo.ipynb` to run the demo.