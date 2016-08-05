### Take heap dump using JMAP

```
jmap -dump:file=/tmp/app_1.`date +%Y%m%d`.hprof -F <PID>
```

### get heapdump without jmap

```
java -agentlib:hprof=heap=dump,format=b,file=out.hprof <CLASS> 
```
