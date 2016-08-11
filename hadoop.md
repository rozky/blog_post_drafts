Hadoop
==========


```
#!/bin/bash

cd /usr/local/Cellar/hadoop/2.7.1/libexec/

bin/hdfs namenode -format
sbin/start-dfs.sh
bin/hdfs dfs -mkdir /user
bin/hdfs dfs -mkdir /user/local-user
```

check data node at: `http://localhost:50070/`


```
hdfs dfs -put ~/hadoop/zeno.log /user/local-user/
```
