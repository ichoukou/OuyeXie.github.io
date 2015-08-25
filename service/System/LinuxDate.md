to get date in secs:

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
