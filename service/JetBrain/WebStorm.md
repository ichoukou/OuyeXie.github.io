# Keyboard

 - go to file (shift command O)

# FQA

 - How to enlarge memory use?
    - edit ```/Applications/WebStorm 2.app/Contents/bin/webstorm.vmoptions```
    - ```-Xms128m
         -Xmx2048m
         -XX:MaxPermSize=700m
         -XX:ReservedCodeCacheSize=480m
         -XX:+UseCompressedOops```
         
         
 - https://www.zhihu.com/question/38021840
    - edit ```/Applications/WebStorm.app/Contents/bin/webstorm.vmoptions```
    - ```
        -d64
        -server
        -Xms1024m
        -Xmx4096m
        -XX:MaxPermSize=1024m
        -XX:ReservedCodeCacheSize=240m
        -XX:+UseCompressedOops
        -Xss4m
        -ea
        -Dsun.io.useCanonCaches=false
        -Djava.net.preferIPv4Stack=true
        -XX:+UseCodeCacheFlushing
        -XX:+UseConcMarkSweepGC
        -XX:SoftRefLRUPolicyMSPerMB=50
        -XX:MinHeapFreeRatio=15
        -Xincgc
```