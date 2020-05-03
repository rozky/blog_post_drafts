# Python Pandas 


## Commonly used function examples

## Configured pandas output

```python
# number of max columns to output like when calling head(), default is 5 which to small especially on "bigger" screen
pd.set_option('display.max_columns', 20)

# configureds width of an output line so more columns can fit on single line otherwise it's broken across multiple 
pd.set_option('display.width', 700)
```

### Drop Row / Column

`axis=0` - drop row, default

`axis=1` - drop column


```python
# drop rows 0,1,2
train.drop([0,1,2])

# drop columns "PassengerId", "Survived"
train.drop(columns = ["PassengerId", "Survived"], axis=1)


```
