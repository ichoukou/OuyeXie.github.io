# Command line

convert to arff
```
java weka.core.converters.CSVLoader data.csv > data.arff
java weka.core.converters.C45Loader c45_filestem > data.arff
```

# Reference
 - [Documentation](http://www.cs.waikato.ac.nz/ml/weka/documentation.html)
 - [weka及其数据格式](http://www.cnblogs.com/finallyliuyu/archive/2010/08/23/1806414.html)
 - [数据挖掘工具Weka之数据格式ARFF及CSV文件格式转换](http://blog.csdn.net/vshadow/article/details/8215465)
    - 但与传统CSV文件不同，Weka能识别的CSV文件要求第一行给各列的定义
 - [WEKA使用教程(经典教程转载)](http://blog.csdn.net/yangliuy/article/details/7589306)