

# Music_Recommender_System

The goal of this repository is to develop a recommender system for Deezer and improve their collaborative filtering pipeline. It was part of a Kaggle challenge however, here I did not focus merely on improving metrics but more on building a recommender system that is flexible, scalable and interpretable.

The data can be found here : https://www.kaggle.com/competitions/dsg17-online-phase/data

More information about Deezer API for metadata can be found here: https://developers.deezer.com/login?redirect=/api


First step was to prerprocess the data and enhance it with metadata from Deezer API. This part can be found in the BPR script.

Two methods are used.

## 1- Bayesian Personalized Ranking using Implicit package</b> 

## 2- Bertopic enhanced LightFM with metadata


Based on the results, LightFM with metadata outperformed both approaches with precision@10 0.5 and AUC score with 0.9. The validation metrics were calculated using a sample since the Deezer metadata contains 7 million rows, to do the evaluation without access to GPU's were impossible. BERTopic reranking did not contribute to model performance and BPR Model even though it was predicting above chance (AUC: 0.54, Precision@10: 0.177) was not ideal for a large scale recommender system with cold-start and scalability problems. Based on the results, we recommend a metadata enhanced LightFM model for Deezer music recommender system.

The scripts are made as tutorials, so if you want to learn more about the modeling approaches you can follow them and interpret them for your own data.
