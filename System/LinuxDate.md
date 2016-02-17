to get date in secs (ts):

```
date +%s
```

to get date in milliseconds:

```
date +%s%3N
```

but it is on linux, to do it in OX:

```
echo $(($(date +%s)*1000))
```

# Reference

 - http://www.jb51.net/LINUXjishu/227114.html