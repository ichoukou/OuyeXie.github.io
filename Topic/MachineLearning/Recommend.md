# In General
 
 - [Recommender system](https://en.wikipedia.org/wiki/Recommender_system)
     - Collaborative filtering
     - Content-based filtering
 - [探索推荐引擎内部的秘密](http://www.ibm.com/developerworks/cn/views/web/libraryview.jsp?view_by=search&sort_by=Date&sort_order=desc&view_by=Search&search_by=探索推荐引擎内部的秘密&dwsearch.x=12&dwsearch.y=11&dwsearch=Go)
     - 与上面讲的类似，基于项目的协同过滤推荐和基于内容的推荐其实都是基于物品相似度预测推荐，只是相似度计算的方法不一样，前者是从用户历史的偏好推断，而后者是基于物品本身的属性特征信息。
    
     - 将不同的行为分组：一般可以分为“查看”和“购买”等等，然后基于不同的行为，计算不同的用户 / 物品相似度。类似于当当网或者 Amazon 给出的“购买了该图书的人还购买了 ...”，“查看了图书的人还查看了 ...”
     
     - Item CF 和 User CF 是基于协同过滤推荐的两个最基本的算法，User CF 是很早以前就提出来了，Item CF 是从 Amazon 的论文和专利发表之后（2001 年左右）开始流行，大家都觉得 Item CF 从性能和复杂度上比 User CF 更优，其中的一个主要原因就是对于一个在线网站，用户的数量往往大大超过物品的数量，同时物品的数据相对稳定，因此计算物品的相似度不但计算量较小，同时也不必频繁更新。但我们往往忽略了这种情况只适应于提供商品的电子商务网站，对于新闻，博客或者微内容的推荐系统，情况往往是相反的，物品的数量是海量的，同时也是更新频繁的，所以单从复杂度的角度，这两个算法在不同的系统中各有优势，推荐引擎的设计者需要根据自己应用的特点选择更加合适的算法。
     
     - 目前最主流的算法还是Amazon采用的Item-based Collaborative Filtering，一般的商用系统都会实现这样一套算法作为baseline (基于项目的协同过滤推荐) (http://www.zhihu.com/question/19558085)
     Amazon 利用可以记录的所有用户在站点上的行为，根据不同数据的特点对它们进行处理，并分成不同区为用户推送推荐：
     今日推荐 (Today's Recommendation For You): 通常是根据用户的近期的历史购买或者查看记录，并结合时下流行的物品给出一个折中的推荐。
     新产品的推荐 (New For You): 采用了基于内容的推荐机制 (Content-based Recommendation)，将一些新到物品推荐给用户。在方法选择上由于新物品没有大量的用户喜好信息，所以基于内容的推荐能很好的解决这个“冷启动”的问题。
     捆绑销售 (Frequently Bought Together): 采用数据挖掘技术对用户的购买行为进行分析，找到经常被一起或同一个人购买的物品集，进行捆绑销售，这是一种典型的基于项目的协同过滤推荐机制。
     别人购买 / 浏览的商品 (Customers Who Bought/See This Item Also Bought/See): 这也是一个典型的基于项目的协同过滤推荐的应用，通过社会化机制用户能更快更方便的找到自己感兴趣的物品。
     值得一提的是，Amazon 在做推荐时，设计和用户体验也做得特别独到：
     Amazon 利用有它大量历史数据的优势，量化推荐原因。
     基于社会化的推荐，Amazon 会给你事实的数据，让用户信服，例如：购买此物品的用户百分之多少也购买了那个物品；
     基于物品本身的推荐，Amazon 也会列出推荐的理由，例如：因为你的购物框中有 ***，或者因为你购买过 ***，所以给你推荐类似的 ***。[correct]
     另外，Amazon 很多推荐是基于用户的 profile 计算出来的，用户的 profile 中记录了用户在 Amazon 上的行为，包括看了那些物品，买了那些物品，收藏夹和 wish list 里的物品等等，当然 Amazon 里还集成了评分等其他的用户反馈的方式，它们都是 profile 的一部分，同时，Amazon 提供了让用户自主管理自己 profile 的功能，通过这种方式用户可以更明确的告诉推荐引擎他的品味和意图是什么。
     
     - “你的个人推荐是根据你的收藏和评价自动得出的，每个人的推荐清单都不同。你的收藏和评价越多，豆瓣给你的推荐会越准确和丰富。
       每天推荐的内容可能会有变化。随着豆瓣的长大，给你推荐的内容也会越来越准。”
       这一点让我们可以清晰明了的知道，豆瓣必然是基于社会化的协同过滤的推荐，这样用户越多，用户的反馈越多，那么推荐的效果会越来越准确。
       相对于 Amazon 的用户行为模型，豆瓣电影的模型更加简单，就是“看过”和“想看”，这也让他们的推荐更加专注于用户的品味，毕竟买东西和看电影的动机还是有很大不同的。
       另外，豆瓣也有基于物品本身的推荐，当你查看一些电影的详细信息的时候，他会给你推荐出“喜欢这个电影的人也喜欢的电影”， 如图 10，这是一个基于协同过滤的应用。[wrong]
 
 - [基于 Apache Mahout 构建社会化推荐引擎](http://www.ibm.com/developerworks/cn/java/j-lo-mahout/)
    - it seems that there is no off-line computation included in this tutorial
        - maybe at the startup phase? then how to update the data? 
        - maybe calculate on the fly every time a request comes in?
    - Algorithms
        - [Recommender Overview](https://mahout.apache.org/users/algorithms/recommender-overview.html)
        - [Intro to Cooccurrence Recommenders with Spark](https://mahout.apache.org/users/algorithms/intro-cooccurrence-spark.html)
    - Mahout Mapreduce
        - [Creating a User-Based Recommender in 5 minutes](https://mahout.apache.org/users/recommender/userbased-5-minutes.html)
        - [Introduction to Matrix Factorization for Recommendation Mining](https://mahout.apache.org/users/recommender/matrix-factorization.html)
        - [Overview](https://mahout.apache.org/users/recommender/recommender-documentation.html)
                - Runtime Performance
                    - Use CachingRecommender on top of your custom Recommender implementation.
                    - When using JDBCDataModel, make sure you wrap it with the ReloadFromJDBCDataModel to load data into memory
                - Algorithm Performance: Which One Is Best?
        - [Introduction to Item-Based Recommendations with Hadoop](https://mahout.apache.org/users/recommender/intro-itembased-hadoop.html)
        - [Introduction to ALS Recommendations with Hadoop](https://mahout.apache.org/users/recommender/intro-als-hadoop.html)
        
# Packages

## annotations

 - Collaborative
    - it can predict the rating to a item from a user who already exists in our database
        - new user is not covered
        - neither user nor item info is used to compute (only rating is used)
 - Like/Dislike
    - only 0 1
 - Rating
    - from 0 to n (ie 5)
 - Redis
    - take advantage of redis
     
## examples

 - nodejs
    - [recommendationRaccoon](https://github.com/guymorita/recommendationRaccoon)
        - A collaborative filtering based recommendation engine and NPM module built on top of Node.js and Redis. The engine uses the Jaccard coefficient to determine the similarity between users and k-nearest-neighbors to create recommendations. This module is useful for anyone with a database of users, a database of products/movies/items and the desire …
        - [Like/Dislike, Collaborative, Redis]
    - [node-recommend](https://github.com/xissy/node-recommend)
        - A Node.js module to implement a recommender engine with popular machine-learning algorithms.
            - User and Item by Collarborative Filters
        - [Collaborative(most likely)]
        
 - python 
    - [crab (lack of docs)](https://github.com/muricoca/crab)
        - Crab is a ﬂexible, fast recommender engine for Python that integrates classic information ﬁltering recom- mendation algorithms in the world of scientiﬁc Python packages (numpy, scipy, matplotlib). The engine aims to provide a rich set of components from which you can construct a customized recommender system from a set of algorithms.
    - [python-recsys (good docs with svd)](https://github.com/ocelma/python-recsys)
        - A python library for implementing a recommender system.
        - [python-recsys v1.0 documentation](http://ocelma.net/software/python-recsys/build/html/)
        - [Rating, Collaborative]
 
 - java
    - [lenskit](https://github.com/lenskit/lenskit)
        - LensKit is an implementation of collaborative filtering algorithms and a set of tools for benchmarking them. This readme is about working with the LensKit source code. For more information about LensKit and its documentation, visit the web site or wiki. You can also find information on the wiki about how to use LensKit without downloading the source code. If this is your first time working with LensKit we recommend checking out the Getting Started guide.
    - [librec](https://github.com/guoguibing/librec)
    - [solr-recommender](https://github.com/pferrel/solr-recommender)
    
## services

 - [阿里云, 推荐引擎](https://data.aliyun.com/product/re?spm=5176.7960203.223922.5.Cacrtm)
    - https://help.aliyun.com/document_detail/shujia/RE/intro/re-intro3.html?spm=5176.docshujia/RE/intro/re-intro2.6.229.chXRgO
        - 事实上，回到场景的原始定义，场景只是由推荐的上下文决定，客户完全可以根据自己的需求建立全新的场景，比如针对搜索关键词的推荐场景，这时可用的参数除了用户信息，还有用户所输入的关键词。
        - online_flow中用到的在线算法相对简单，主要是对推荐结果的评分，过滤和排序，mod_path中用到的在线算法会复杂一些，如何取舍视具体的需求而定。
    - https://help.aliyun.com/document_detail/shujia/RE/intro/re-intro10.html?spm=5176.docshujia/RE/intro/re-intro9.6.237.C9v45f
        - 这有些类似于冷启动的情形，这时需要客户提供默认推荐策略，通常是热门推荐，即向冷启动用户推荐热门物品。RecEng的预置算法中包括热门物品推荐的算法，客户可直接使用。
    - offline speed? how to guarantee for new users 
    - 日志埋点?
        
        
# Algorithm

 - [强大的矩阵奇异值分解(SVD)及其应用](http://www.cnblogs.com/LeftNotEasy/archive/2011/01/19/svd-and-applications.html)
 - [rmse](https://en.wikipedia.org/wiki/Root-mean-square_deviation)
 - [mae](https://en.wikipedia.org/wiki/Mean_absolute_error)
 
# Data

 - [movielens](http://grouplens.org/datasets/movielens/)
 
# Notes
 
 - instead of developing Hybrid recommender systems from scratch, is it better to make use one of above packages and then improve it by manually adding content? For example, we can separate the system into two parts/phases below, and they can be working together or even one after another
    - 1 user assign some features and we recommend from them
        - 1 add items (according to features) quietly to users rating metric
            - when there are more explicit ratings, lets say 5, remove implicit ones
        - 2 add features to all users rating metric when new users are added
            - higher or lower score compared to normal ratings
        - 3 基于人口统计学的推荐机制 (系统对每个用户都有一个用户 Profile 的建模，其中包括用户的基本信息，例如用户的年龄，性别等等 here all features can be added)
            - 因为不使用当前用户对物品的喜好历史数据，所以对于新用户来讲没有“冷启动（Cold Start）”的问题。
    - 2 collaborative 
    
 - actions from user
    - simple
        - subscribe a topic
        - view a topic
    - all
        - ask a question
        - answer a question
        - like an answer
        - pulish a post
        - like a post
        - comment a post
        - subscribe a stock
        - like a stock comment
        - subscribe a user
        - subscribe a system (channel 0 1 2...)
    - type
        - click
        - stay (how long)
        
# Reference

 - [apache mahout](http://mahout.apache.org)