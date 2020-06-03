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

## If error return error

abbriviation: `ifere`

```go
if $ERR$ != nil {
    return nil, $ERR$
}
```

```xml
<template name="ifere" value="if $ERR$ != nil {&#10;    return nil, $ERR$&#10;}" description="If error return error" toReformat="false" toShortenFQNames="true">
  <variable name="ERR" expression="errorVariable()" defaultValue="&quot;err&quot;" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
```

## If error panic

abbriviation: `ifep`

```go
if $ERR$ != nil {
    panic($ERR$)
}
```

```xml
<template name="ifep" value="if $ERR$ != nil {&#10;    panic($ERR$)&#10;}" description="If error panic" toReformat="false" toShortenFQNames="true">
  <variable name="ERR" expression="errorVariable()" defaultValue="err" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
```

## Generate Sort (sortable, comparable) Interface implementation

abbriviation: `sortable`

```go
// sort.Interface
func ($ARG_NAME$ $ARG_TYPE$) Len() int { return len($ARG_NAME$) }
func ($ARG_NAME$ $ARG_TYPE$) Less(i, j int) bool { return $ARG_NAME$[i] < $ARG_NAME$[j] }
func ($ARG_NAME$ $ARG_TYPE$) Swap(i, j int) { $ARG_NAME$[i], $ARG_NAME$[j] = $ARG_NAME$[j], $ARG_NAME$[i] }
```

```xml
<template name="sortable" value="// sort.Interface&#10;func ($ARG_NAME$ $ARG_TYPE$) Len() int { return len($ARG_NAME$) }&#10;func ($ARG_NAME$ $ARG_TYPE$) Less(i, j int) bool { return $ARG_NAME$[i] &lt; $ARG_NAME$[j] }&#10;func ($ARG_NAME$ $ARG_TYPE$) Swap(i, j int) { $ARG_NAME$[i], $ARG_NAME$[j] = $ARG_NAME$[j], $ARG_NAME$[i] }" description="Generate Sort (sortable, comparable) Interface implementation" toReformat="false" toShortenFQNames="true">
  <variable name="ARG_NAME" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <variable name="ARG_TYPE" expression="complete()" defaultValue="" alwaysStopAt="true" />
  <context>
    <option name="GO" value="true" />
  </context>
</template>
```

