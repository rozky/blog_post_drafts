jolokia
=======

### take thread dump

```
curl http://localhost:8080/jolokia/exec/java.lang:type=Threading/dumpAllThreads/true/true
```


### Command line tool `j4psh`

If you don't know object names or commands name `j4psh` is great tool to explore and find a things you are looking for. 

```
j4psh http://localhost:8089/jolokia/
```

opens a new shell then you can try `ls` or `cd com.sun.management` or `cd type=HotSpotDiagnostic`
