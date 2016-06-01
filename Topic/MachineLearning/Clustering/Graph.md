 - [图聚类的算法及其在社会关系网络中的应用](http://www.doc88.com/p-010966203707.html)
    - 图聚类有很多不同的方式，比较具代表性的有：Markov聚类［2，3］、谱聚类［4］和基于密度的聚类［5］等。其中Markov聚类的核心思想是基于模拟随机流（使用图的转移概率矩阵）进行图聚类；谱聚类是通过优化图的最小分割来进行图聚类，其中这个优化问题可以通过解一个图矩阵的特征值特征向量的方法实现；而基于密度的聚类是通过衡量一个点周围邻居的密度来进行图聚类，该算法不仅可以对图聚类，还可以识别出中心桥梁点（hub）和异常点（outlier）。
    - 2．1 最短路径距离Dijkstra算法
    - 2．2 随机漫步距离RandomWalk算法
    - 2．3 k-medoids算法
        - 该算法中，随机选择k个对象作为初始聚类中心点，通常只能以局部最优结束，并且该方法对孤立点敏感。本文对该算法进行改进，首先随机选择一个对象作为初始聚类中心点，然后选择离这个点最远的点作为第二个聚类中心点，接着选择离前两个聚类中心点都远的点作为第三个聚类中心点，以此类推，直到找到第k个聚类中心点。这样能够使得选取的中心点比较分散。
        
 - [复杂网络聚类方法](http://jos.org.cn/ch/reader/create_pdf.aspx?file_no=3464&journal_id=jos)
 
 - [复杂网络聚类算法研究](http://wenku.baidu.com/link?url=D66eiggdTXki0VgdQt854QaSQuR_DaEGJZAVqNx9bOSyFxq06BsCE4IYGdGJKeJM1CYNXzpYijmG0LYLBhoUM2D0lA6I5zo9OZ1KCgTLLqm)