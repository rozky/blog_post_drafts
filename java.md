VisualVM
-----------------

### OQL examples

```
 select s from java.lang.String s where s.toString() == "org/springframework/web/servlet/view/freemarker/debug"
```

Heap dump
----------------

### Take heap dump using JMAP

```
jmap -dump:file=/tmp/app_1.`date +%Y%m%d`.hprof -F <PID>
```

### get heapdump without jmap

```
java -agentlib:hprof=heap=dump,format=b,file=out.hprof <CLASS> 
```
