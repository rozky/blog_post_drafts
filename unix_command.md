Unix commands
===================

Memory Usage analyses
-------------

#### How to find out processes consuming most of the system memory

```
ps -eo rss,pid,user,command --sort -size | head -n 10 | awk '{ hr=$1/1024 ; printf("%13.2f MB ",hr) } { for ( x=4 ; x<=5 ; x++ ) { printf("%s ",$x) } print "" }'
``` 

sample output:
```
982.44 MB /usr/bin/java 
963.39 MB /usr/bin/java 
950.29 MB /usr/bin/java 
962.49 MB /usr/bin/java 
341.03 MB /usr/bin/java 
```

#### How to keep a process running in background after ending a ssh session

```
screen java -jar <JAR_NAME>
```
then to leave the screen press `CRTL+A` followed by `d`. List all screens by `screen -ls` and attach to a specific screen `screen -r <SCREEN_ID>`

