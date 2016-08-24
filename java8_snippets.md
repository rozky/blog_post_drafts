Java8
=============

### Read classpath file by lines

```
Resource resource = new ClassPathResource("data.sql");
BufferedReader reader = new BufferedReader(new InputStreamReader(resource.getInputStream()));
reader.lines().forEach(System.out::println);
```
