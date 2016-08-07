jolokia
=======

### take thread dump

```
curl http://localhost:8080/jolokia/exec/java.lang:type=Threading/dumpAllThreads/true/true
```


Using command line tools `j4psh` make things much more easier:

```
j4psh http://localhost:8089/jolokia/
```

this open new shell try `ls` or `cd com.sun.management`
