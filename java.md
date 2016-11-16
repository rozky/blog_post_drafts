JVM Config
----------------

- http://blog.sokolenko.me/2014/11/javavm-options-production.html

Install
---------------

```
sudo apt-get install software-properties-common python-software-properties
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer

# verify
java -version
```

reference: http://tecadmin.net/install-oracle-java-8-jdk-8-ubuntu-via-ppa


VisualVM
-----------------

### OQL examples

```
 select s from java.lang.String s where s.toString() == "org/springframework/web/servlet/view/freemarker/debug"
```

```
select l from java.util.ArrayList l where l.size == 0
```

Inefficient use of data structures, like keeping millions of empty lists or HashMaps. With OQL you can easily find e.g. all instances of ArrayList which are empty and have never been modified:
```
select l from java.util.ArrayList l where l.size == 0 && l.modCount == 0
```

```
function emptyCollection(c) {
  return c.size == 0;
}

filter(heap.objects('java.util.AbstractMap'), emptyCollection);
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
