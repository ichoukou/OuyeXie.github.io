 - [Canopy聚类算法](http://my.oschina.net/liangtee/blog/125407)
    - 与传统的聚类算法(比如K-means)不同，Canopy聚类最大的特点是不需要事先指定k值(即clustering的个数)，因此具有很大的实际应用价值。与其他聚类算法相比，Canopy聚类虽然精度较低，但其在速度上有很大优势，因此可以使用Canopy聚类先对数据进行“粗”聚类，得到k值后再使用K-means进行进一步“细”聚类。
    - Canopy算法流程
        （1）、将数据集向量化得到一个list后放入内存，选择两个距离阈值：T1和T2，其中T1 > T2，对应上图，实线圈为T1，虚线圈为T2，T1和T2的值可以用交叉校验来确定；
    
        （2）、从list中任取一点P，用低计算成本方法快速计算点P与所有Canopy之间的距离（如果当前不存在Canopy，则把点P作为一个Canopy），如果点P与某个Canopy距离在T1以内，则将点P加入到这个Canopy；
    
        （3）、如果点P曾经与某个Canopy的距离在T2以内，则需要把点P从list中删除，这一步是认为点P此时与这个Canopy已经够近了，因此它不可以再做其它Canopy的中心了；
    
        （4）、重复步骤2、3，直到list为空结束。