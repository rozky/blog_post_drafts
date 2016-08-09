Logstash
=========

Install by downloading compressed package, unpack and then run it with:

```
bin/logstash -e 'input { tcp { port => 5000 } } output { stdout {} }'
```

or 

```
bin/logstash -e 'input { stdin { } } output { stdout {} }'
```
