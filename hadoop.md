Hadoop
==========


```
#!/bin/bash

cd /usr/local/Cellar/hadoop/2.7.1/libexec/

hdfs namenode -format
sbin/start-dfs.sh
hdfs dfs -mkdir /user
hdfs dfs -mkdir /user/local
hdfs dfs -mkdir /user/local/zeno
```

check data node at: `http://localhost:50070/`

Upload file to HDFS:

```
hdfs dfs -put ~/development/gumtree/hadoop_data/gt-web149-local4.log.bz2 /user/local/zeno/
```

Delete file from HDFS:

```
hdfs dfs -rmr -skipTrash /user/local/zeno/gt-web149-local4.log.bz2
```

Download all files inside folder from HDFS:

```
hadoop fs -getmerge /user/local/popular-search/report popular-search.csv
```

Availbe commands: https://hadoop.apache.org/docs/r2.4.1/hadoop-project-dist/hadoop-common/FileSystemShell.html#rm
