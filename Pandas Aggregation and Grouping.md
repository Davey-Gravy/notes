# Grouping
Get rows that share specific column names:

```python
# get initial subgroup you want to explore
group = df.groupby(column)

# shw
group.get_group(subgroup)
```

Same as:

```python
filt = df[column] == 'United States'

df.loc[filt]
```

Get row values for each row with matching column value

```python

group[column].value_counts()
```
