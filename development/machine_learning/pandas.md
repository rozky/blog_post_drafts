# Python Pandas 

- https://pypi.org/project/sklearn-pandas/1.5.0/

## Commonly used function examples

## Configured pandas output

```python
# number of max columns to output like when calling head(), default is 5 which to small especially on "bigger" screen
pd.set_option('display.max_columns', 20)

# configureds width of an output line so more columns can fit on single line otherwise it's broken across multiple 
pd.set_option('display.width', 700)
```

### Explore data

```python
print(train.shape)

# prints top 40 rows
print(train.head(40).to_string())

# prints basics stats about each column like: count, mean, std, min, max, 25% 75%
print(train.describe())

# single column basic stats
train['Age'].describe()

# count number of null/missing values in each column
print(train.isnull().sum())
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


### Dataframe transformations

```python
# append dataframe to dataframe
train.append(test, ignore_index=True)
```

### Column transformations

```python
# map column value to diff value
train['Sex'] = train['Sex'].map({"male": 0, "female": 1}) 
train['Embarked'] = train["Embarked"].map({"S": 0, "C": 1, "Q": 2})

# apply custom function / lambda to column value
train['Cabin'] = train['Cabin'].apply(lambda x: str(x)[0].upper())

# merge 2 columns
train['Family'] = train['SibSp'] + train['Parch']
```

### Missing values

```python
# substituting null values with the most frequent value in that column
# https://pypi.org/project/sklearn-pandas/1.5.0/
g = CategoricalImputer()
train['Embarked'] = cg.fit_transform(train['Embarked'].values.reshape(-1,1))

# Imputation for completing missing values using k-Nearest Neighbors.
knn_imputer = KNNImputer(n_neighbors=4)
train.iloc[:, 5] = train.fit_transform(train.iloc[:,5].values.reshape(-1,1))

# Transform features by scaling each feature to a given range
mx = MinMaxScaler()
train['Age'] = mx.fit_transform(train['Age'].values.reshape(-1,1))

```
