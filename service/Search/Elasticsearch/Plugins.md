# IK

## Install:

### jar

<pre>
<code>
git clone https://github.com/medcl/elasticsearch-analysis-ik

cd elasticsearch-analysis-ik

mvn compile

mvn package

plugin --install analysis-ik --url file:///#{project_path}/elasticsearch-analysis-ik/target/releases/elasticsearch-analysis-ik-1.3.0.zip
</code>
</pre>

#### details

 - make sure use .zip to install as it includes all dependencies (XXX-jar-with-dependencies.jar may also work but did
  not try)
 - mvn sometimes cannot work with ik's parents, make sure you have the correct maven version

### config 

copy elasticsearch-analysis-ik/config/ik into ES-HOME/config/ik (create dir if there was not any)

### edit elasticsearch.yml

<pre>
<code>
index:
  analysis:
    analyzer:
      ik:
          alias: [ik_analyzer]
          type: org.elasticsearch.index.analysis.IkAnalyzerProvider
      ik_max_word:
          type: ik
          use_smart: false
      ik_smart:
          type: ik
          use_smart: true
</code>
</pre>

### test

```
curl 'http://localhost:9200/index/_analyze?analyzer=ik&pretty=true' -d '
{
"text":"世界如此之大"
}'
```

```
curl 'http://localhost:9288/stocks/_analyze?analyzer=ik&pretty=true' -d ' { "text":"绿山咖啡" }'
```

## References:

 - https://github.com/medcl/elasticsearch-analysis-ik
 
 - http://my.oschina.net/xiaohui249/blog/232784
 
# Boson

## Install:

### jar

<pre>
<code>
git clone git@github.com:bosondata/elasticsearch-analysis-bosonnlp.git

cd elasticsearch-analysis-bosonnlp

git checkout -b 1.0.0-beta origin/1.0.0-beta # as we are using es1.7.*

mvn clean package

plugin --install elasticsearch-analysis-bosonnlp --url file:///#{project_path}/elasticsearch-analysis-bosonnlp/target/releases/elasticsearch-analysis-bosonnlp-1.3.0.zip

OR YOU CAN JUST INSTALL FROM RELEASE

./plugin  -u https://github.com/bosondata/elasticsearch-analysis-bosonnlp/releases/download/1.0.0-beta/elasticsearch-analysis-bosonnlp-1.0.0-beta-plugin.1.zip -i elasticsearch-analysis-bosonnlp

WHERE IS PLUGIN? /usr/share/elasticsearch/bin
</code>
</pre>

#### details

 - make sure use .zip to install as it includes all dependencies (XXX-jar-with-dependencies.jar may also work but did
  not try)
 - mvn sometimes cannot work with ik's parents, make sure you have the correct maven version

### edit elasticsearch.yml

<pre>
<code>
index:
  analysis:
    analyzer:
      bosonnlp:
        type: bosonnlp
        API_URL: http://api.bosonnlp.com/tag/analysis
        # You MUST give the API_TOKEN value, otherwise it doesn't work
        API_TOKEN: *PUT YOUR API TOKEN HERE*
        # Please uncomment if you want to specify ANY ONE of the following
        # areguments, otherwise the DEFAULT value will be used, i.e.,
        # space_mode is 0,
        # oov_level is 3,
        # t2s is 0,
        # special_char_conv is 0.
        # More detials can be found in bosonnlp docs:
        # http://docs.bosonnlp.com/tag.html
        #
        #
        # space_mode: put your value here(range from 0-3)
        # oov_level: put your value here(range from 0-4)
        # t2s: put your value here(range from 0-1)
        # special_char_conv: put your value here(range from 0-1)
</code>
</pre>

### test

```
curl 'http://localhost:9200/index/_analyze?analyzer=bosonnlp&pretty=true' -d '
{
"text":"世界如此之大"
}'
```

```
curl 'http://localhost:9288/stocks/_analyze?analyzer=bosonnlp&pretty=true' -d ' { "text":"绿山咖啡" }'
```

## Reference

 - http://bosonnlp.com
 - https://github.com/bosondata/elasticsearch-analysis-bosonnlp
 
# Comparison

 - https://github.com/search?utf8=✓&q=elasticsearch-analysis-
 
    - https://github.com/medcl/elasticsearch-analysis-mmseg
    
 - http://www.oschina.net/question/2448846_2140974
 
    - BosonNLP：http://bosonnlp.com/dev/center
    
    - IKAnalyzer：http://www.oschina.net/p/ikanalyzer
    
    - NLPIR：http://ictclas.nlpir.org/docs
    
    - SCWS中文分词：http://www.xunsearch.com/scws/docs.php
    
    - 结巴分词：https://github.com/fxsjy/jieba
        - https://github.com/huaban/elasticsearch-analysis-jieba
        - https://github.com/huaban/jieba-analysis
    - 盘古分词：http://pangusegment.codeplex.com/
    
    - 庖丁解牛：https://code.google.com/p/paoding/
    
    - 搜狗分词：http://www.sogou.com/labs/webservice/
    
    - 腾讯文智：http://www.qcloud.com/wiki/API%E8%AF%B4%E6%98%8E%E6%96%87%E6%A1%A3
    
    - 新浪云：http://www.sinacloud.com/doc/sae/python/segment.html
    
    - 语言云：http://www.ltp-cloud.com/document