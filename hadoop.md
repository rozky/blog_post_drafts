Hadoop
==========


```
#!/bin/bash

cd /usr/local/Cellar/hadoop/2.7.1/libexec/

bin/hdfs namenode -format
sbin/start-dfs.sh
bin/hdfs dfs -mkdir /user
bin/hdfs dfs -mkdir /user/local
bin/hdfs dfs -mkdir /user/local/zeno
```

check data node at: `http://localhost:50070/`


```
bin/hdfs dfs -put ~/development/gumtree/hadoop_data/gt-web149-local4.log.bz2 /user/local/zeno/
```
