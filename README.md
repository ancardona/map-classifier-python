# Maximum A Posteriori Classifier

[![Build Status](https://travis-ci.org/nwtgck/map-classifier-python.svg?branch=develop)](https://travis-ci.org/nwtgck/map-classifier-python) [![Coverage Status](https://coveralls.io/repos/github/nwtgck/map-classifier-python/badge.svg?branch=develop)](https://coveralls.io/github/nwtgck/map-classifier-python?branch=develop) 

A classifier of Maximum A Posteriori (MAP) which is compatible with [scikit-learn](http://scikit-learn.org/).


## Installation

```bash
pip3 install --upgrade git+https://github.com/nwtgck/map-classifier-python.git
```

## Example Usage

```python
from sklearn.datasets import load_iris
from sklearn import metrics
from sklearn.model_selection import train_test_split

import map_classifier


# Load Iris data set
X, y = load_iris(return_X_y=True)

# Create a classifier
clf = map_classifier.MAPClassifier()

# Create training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y,test_size=0.3, random_state=40)

# Learn then model
clf.fit(X_train, y_train)

# Predict
y_pred = clf.predict(X_test)

# Calc accuracy
test_accuracy = metrics.accuracy_score(y_test, y_pred)

# Print the accuracy
print(test_accuracy)
```

You can find examples in [examples](examples).