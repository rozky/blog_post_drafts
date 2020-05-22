# GO Lang code snippets (in GoLand live template format)

## checks if map contains a given key

abbriviation: `mapcontains`

```go
if $VAL$, contains := $MAP$[$KEY$]; contains {
    $END$      
}
```

```xml
<template name="mapcontains" value="if $VAL$, contains := $MAP$[$KEY$]; contains {&#10;    $END$      &#10;}" description="checks if map contains a given key" toReformat="false" toShortenFQNames="true">
  <variable name="VAL" expression="" defaultValue="val" alwaysStopAt="true" />
  <variable name="MAP" expression="" defaultValue="" alwaysStopAt="true" />
  <variable name="KEY" expression="" defaultValue="" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
```
