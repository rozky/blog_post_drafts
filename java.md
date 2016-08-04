### get heapdump without jmap

```
java -agentlib:hprof=heap=dump,format=b,file=out.hprof <CLASS> 
```
