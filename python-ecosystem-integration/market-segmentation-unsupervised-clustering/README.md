# User Segmentation with GDS & Python

In [Neo4j Graph Data Science (GDS)](https://neo4j.com/docs/graph-data-science/current/) we can leverage node embeddings to generate features for exploratory cluster analysis and unsupervised learning. In combination with other graph native clustering techniques like community detection, GDS offers a robust set of tooling to quickly analysis how your data is structured, integrate into your data science ecosystem, and deliver actionable insights for the enterpise. 


## This Example
We use Fast Random Projections (FastRP) node embeddings to encapsulate the graph structure then port over into Python where we can run K-means to explore how users may be clustered into different categories of interest. This would inform analysis for user segmentation. 
While the dataset used in this demo is focused on a news content platform, the same methodology is highly transferable to retail, marketing, financial services, and other industry verticals where customer and/or user segmentation is needed. 

## Dataset
The source dataset is not being re-hosted due to licensing restrictions, but you can find directions for loading thew dataset into Neo4j [here](https://github.com/neo4j-product-examples/demo-news-recommendation/blob/main/mind-large-collab-filtering/prepare-and-load-data.ipynb)

If you are a Neo4j employee interested in internal experimentation please reach out to [zach.blumenfeld@neo4j.com](zach.blumenfeld@neo4j.com). 

## Usage
Once you have the data in Neo4j you can use `stage.ipynb` to stage the demo and `demo.ipynb` to run the demo.