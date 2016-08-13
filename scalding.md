Run a job in IDEA without hadoop
-------------

Navigate through `Run` -> `Edit Configurations...` and add a application configuration with the following settings:

***Main class:*** `com.twitter.scalding.Tool`
***Arguments:*** 
```
<JOB_CLASS_NAME> 
--local 
--output <OUT_FILE_ON_LOCAL_FILESYSTEM> 
--input <IN_FILE_ON_LOCAL_FILESYSTEM> 
```

Save the configuration and run it. If everything is correctly configured output should be written to ***OUT_FILE_ON_LOCAL_FILESYSTEM***.
