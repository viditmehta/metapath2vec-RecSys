## Virtual Item Recommender System (A Network Embedding Approach)

In this study, we propose a novel method for making recommendations to users in a heterogeneous network by leveraging some recent advancements in network embedding in computer science field- [metapath2vec Dong et al](https://ericdongyx.github.io/metapath2vec/m2v.html). This study is designed to create a recommender system for virtual items within games hosted on an online gaming platform. These virtual items can be *digital avatars, weapons, magical artifacts* etc. Please refer to the [Project Methodology](docs/DOCUMENTATION.md) for further details. Given below is a description of the code files - 
- **Gaming_NetworkInputFileGen:** File to generate various input data files required for the study. The data is fetched from an SQL Server database and read as flat files in Python.
- **CommunityNetwork_RecSys:** A recommender system built on the notion of shared groups between gamers. We hypothesize that higher the number of shared groups, higher is the likelihood of the players being similar. (we use Jaccard similarity)
- **FriendshipNetwork_RecSys:** The platform has a buddy system which allows users to add each other as friends. This is the friendship recommender system built on the notion of mutual friends between gamers. We hypothesize that higher the number of mutual friends, higher is the likelihood of the players being similar. (we use Jaccard similarity)
- **UserItem_RecSys:** Traditional recommender system based on User-Item collaborative filtering algorithm. We use [Turi GraphLab](https://turi.com/download/install-graphlab-create.html) module to create the system.
- **LINE_Recommender System:** A recommender system based on the state-of-the-art [LINE algorithm](https://github.com/tangjianpku/LINE) that performs large scale homogenous network embedding considering both local and global networks around a node.
- **meta2vecRecommenderSystem:** Our work which builds a recommendation system by performing heterogeneous network embedding. We leverage random walk approach to create the heterogeneous neighborhood around a node using the metapath scheme UGIGU (User-Game-Item-Game-User).
- **HybridRecommenderSystem:** We also build 2 kinds of hybrid recommender systems - (i) Optimal-weighted Hybrid Recommender System (based on the top 3 performing models) (ii) Equal-weighted Hybrid Recommender System (based on equally weighting the user similarity values from all the algorithms).
- **ClusteringAnalysis:** As an extension to the project, we also perform a clustering analysis to study if there is a pattern to the virtual item purchase behavior by the gamers. We wanted to see if there is a relation between *gamer type* (based on low, medium and high engagement) and *item price* (low, medium and high item prices).
