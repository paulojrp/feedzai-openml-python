OpenML Provider for generic Python models
------------------------------------------------------------

This module contains an OpenML provider for loading custom code that implements
Feedzai's Python API.

The implemented code must contain a "Classifier" class with two methods:

```python
# score the instance and return an array with the probability for each of the classes
def getClassDistribution(self, instance):
    raise NotImplementedError("This must be implemented by a concrete adapter.")

# return the predicted class 
def classify(self, instance):
    raise NotImplementedError("This must be implemented by a concrete adapter.")

``` 

### Usage

When the user imports a model to the Feedzai platform using this provider, the import assumes a folder called ```script``` containing the Python code.

    .
    └── random-forest-v1
        └── script
            └── classifier.py
