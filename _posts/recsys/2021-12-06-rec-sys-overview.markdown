---
layout: post
title:  "Recommendation System Overview"
categories: recsys
permalink: cl_blog/:categories/:title.html
---

The large-scale recommender system mainly consists of two stages: *matching* and *ranking*. Specifically, a *matching stage is expected to retrieve a small fraction of relevant items in low latency and computational cost*, and *a ranking stage aims to refine the ranking of these relevant items in terms of the user’s interest with more complex models* 

The *matching* stage (also known as the *retrieval* step) identifies a small fraction of relevant items from billion-scale item corpus in low latency and computational cost. *Item-to-item collaborative filtering (item-based CF)* and *embedding based retrieval (EBR)* have been long used in the industrial matching stage owing to its efficiency. However, item-based CF is hard to meet personalization and suffer from data sparsity problem [4], while EBR has difficulty in satisfying diversity. 

*Item-to-item based collaborative filtering*, as known as item based CF, is an information retrieval solution for item matching. It estimates the relevance between two items based on their cooccurrence patterns. Several outstanding merits make item-based CF a natural choice for the matching stage in industry are:

* [1] James Davidson, Benjamin Liebald, Junning Liu, Palash Nandy, Taylor Van Vleet, Ullas Gargi, Sujoy Gupta, Yu He, Mike Lambert, Blake Livingston, et al. 2010. The YouTube video recommendation system. In RecSys.
* [2] David C Liu, Stephanie Rogers, Raymond Shiau, Dmitry Kislyuk, Kevin C Ma, Zhigang Zhong, Jenny Liu, and Yushi Jing. 2017. Related pins at pinterest: The evolution of a real-world recommender system. In WWW.
* [3] Brent Smith and Greg Linden. 2017. Two decades of recommender systems at Amazon. com. Ieee internet computing 21, 3 (2017), 12–18.
* [4] Greg Linden, Brent Smith, and Jeremy York. 2003. Amazon. com recommendations: Item-to-item collaborative filtering. IEEE Internet computing 7, 1 (2003), 76–80.



*Embedding-based retrieval (EBR),* especially the deep learning networks with a two-tower architecture [*DSSM*],
has drawn growing interests recently, see 
[1] Jui-Ting Huang, Ashish Sharma, Shuying Sun, Li Xia, David Zhang, Philip Pronin, Janani Padmanabhan, Giuseppe Ottaviano, and Linjun Yang. 2020. Embedding based retrieval in facebook search. In SIGKDD.
[2] Ji Yang, Xinyang Yi, Derek Zhiyuan Cheng, Lichan Hong, Yang Li, Simon XiaomingWang, Taibai Xu, and Ed H Chi. 2020. Mixed Negative Sampling for Learning Two-tower Neural Networks in Recommendations. In WWW.

Briefly speaking, EBR aims to represent each user and item by embedding their profile respectively. In this sense, the matching process is transferred to perform nearest neighbor (NN) search in the embedding space. Although the representation learning could alleviate the data sparsity problem to some extent, these methods also have some
limitations. The two-tower architecture is not easy to explicitly integrate the co-occurrence information between items. Moreover, a user is often represented as a single embedding vector, which is insufficient to encode the diversity of the user’s interest
