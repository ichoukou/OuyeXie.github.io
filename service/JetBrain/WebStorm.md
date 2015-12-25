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