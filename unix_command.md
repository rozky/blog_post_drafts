Unix commands
===================

Memory Usage analyses
-------------

### How to find out processes consuming most of the system memory

```
ps -eo rss,vsz,user,pid,command --sort -rss | head -n 10 | awk '{ rss=$1/1024 ; vsz=$2/1024 ; printf("%13.2f MB %13.2f MB  ",rss, vsz) } { for ( x=4 ; x<=5 ; x++ ) { printf("%s ",$x) } print "" }'
``` 

sample output:
```
         0.00 MB          0.00 MB  PID COMMAND
       627.84 MB       3587.70 MB  1111 /usr/bin/java
        74.25 MB        504.12 MB  2222 /usr/bin/ruby
```

### How to keep a process running in background after ending a ssh session

```
screen java -jar <JAR_NAME>
```
then to leave the screen press `CRTL+A` followed by `d`. List all screens by `screen -ls` and attach to a specific screen `screen -r <SCREEN_ID>`


Apt
-------------

### How to know the version of installed package

```
apt-cache policy <package name>
```
