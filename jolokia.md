jolokia
=======

### Take the threads dump

```
curl http://localhost:8080/jolokia/exec/java.lang:type=Threading/dumpAllThreads/true/true
```

### Take the headp dump 
```
http://localhost:8080/jolokia/exec/com.sun.management:type=HotSpotDiagnostic/dumpHeap/heap_dump.hprof/true
```

### Command line tool `j4psh`

If you don't know object names or commands name `j4psh` is great tool to explore and find a things you are looking for. 

```
j4psh http://localhost:8089/jolokia/
```

opens a new shell then you can try:
  - `ls` 
  - `cd com.sun.management` -> `ls` -> `cd type=HotSpotDiagnostic` -> `exec dumpHeap /tmp/heap_dump.hprof true`
  - `cd java.lang:type=Memory` -> `cat HeapMemoryUsage` or `exec findDeadlockedThreads` or `exec getThreadInfo([J) 3211`
