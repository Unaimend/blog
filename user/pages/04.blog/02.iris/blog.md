---
title: 'Investigating the iris dataset '
content:
    items:
        - '@self.children'
    limit: 5
    order:
        by: date
        dir: desc
    pagination: true
    url_taxonomy_filters: true
---

# Investigating the iris dataset

Because the iris dataset does not contain any missing values or other irregularities. We can immediately 
jump to further preprocessing steps.


## Data preprocessing
We will first split our training set into test and train.


```r
data(iris)
set.seed(123)

# Define the split ratio
split_ratio <- 0.75

# Create training and testing indices
train_indices <- sample(seq_len(nrow(iris)),
                        size = round(split_ratio * nrow(iris)))

# Split the data
train_data <- iris[train_indices, ]
test_data <- tibble(iris[-train_indices, ])
```
