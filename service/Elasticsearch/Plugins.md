# IK

## Install:

### jar

```
```
<div>
<code>
git clone https://github.com/medcl/elasticsearch-analysis-ik

cd elasticsearch-analysis-ik

mvn compile

mvn package

plugin --install analysis-ik --url file:///#{project_path}/elasticsearch-analysis-ik/target/releases/elasticsearch-analysis-ik-1.3.0.zip
</code>
</div>

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

## References:

 - https://github.com/medcl/elasticsearch-analysis-ik
 
 - http://my.oschina.net/xiaohui249/blog/232784