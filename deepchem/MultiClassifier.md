# MultiTask Classifiers

Chapter 3 of the book starts out with
a simple deep learning exmample that
uses a multi-classifier neural network.

# About the MultiTask Classifier Class

The MultiTask Classifier class is a type of
deep learning/neural network model whose
architecture makes it useful for the task
of classifying a set of inputs, given 
multiple classes.

To initialize a MultiTaskClassifier, several
keyword arguments should be specified. Here are 
the first few:

* `n_tasks` - number of tasks
* `n_features` - number of features (input)
* `layer_sizes` - list of integers, representing number of nodes in each layer
* `dropouts` - (optional) specify a dropout value to use for each layer (or all layers)

A bit more on how this neural network is assembled:

* For each layer specified by the user, add a Dense layer with the specified parameters
* If the user specifies a dropout parameter, add a Dropout layer
* The output layer is implemented as a Softmax layer (which itself wraps a Dense layer,
  taking the previous layer as input and outputting 
  a signal with dimensionality `n_tasks * n_classes`)
* Set labels, set weights
* To compute the loss, add a SoftMaxCrossEntropy layer
* To compute the weighted loss, create a WeightedError object and set as loss function
* If weighted decay is specified, create a WeightDecay object and set as loss function

## When to Use MultiTask Classifier

The multitask classifier should be used when the set of
inputs X (`n_observations x n_features`) must be binned
into k classes.

The simplest case is k = 2, which is a binary classification problem.

The general case of arbitrary k can be thought of as k different
binary classification problems, along with a method for dealing
with instances that fall into multiple classes.

## How to use MultiTask Classifier

Start out with code to create a Multitask Classifer
object:

```
# Create model:

model = dc.models.MultitaskClassifier( n_tasks = 12,
                                       n_features = 1024,
                                       layer_sizes = [1000])
```

What do these parameters mean?

- `n_tasks` is the number of classsification tasks (equivalently, the number of classes)
- `n_features` is the number of input variables
- `layer_sizes` specifies the size of each layer (and implicitly, the number of layers)

Now fit the model to data:

```
# Fit model to training data
model.fit(train_dataset, nb_epoch = 10)
```

What does this mean?

- `nb_epoch` specifies how many epochs - that is, complete passes through the whole
  data set - the training procedure will make.
    - Example:
    - If we specify 1 epoch, the model will only see the training data once.
    - If we specify 10 epochs, the model will see the training data 10 times during the training process.

## Evaluating the Multitask Classifier

Main: [Metrics.md](Metrics.md)

Once you have fit your Multitask Classifier to data,
you can evaluate the Multitask Classifier by creating
a Metric object.

The following line of code creates a Metric object
that can be used to assess the model. This metric
computes a function, the `dc.metrics.roc_auc_score`,
which computes the area under the receiver operating
characteristic (ROC) curve (higher values mean fewer
false positives).

```
metric = dc.metrics.Metric(dc.metrics.roc_auc_score, np.mean)
```

The first parameter is a function handle to the ROC AUC
score function, provided by the deepchem library. 

Because we have specified 12 classification tasks,
we will actually have 12 numerical values for ROC AUC 
for each model. The second argument to the `Metric()`
constructor specifies how to aggregate these values.

In this case we use the mean, but we could also use,
e.g., max or min.

See [Metrics.md](Metrics.md) for more about specific metrics.

## MultiTask Classifier Links

* Link to tag 2.1.0 of DeepChem on Github: <https://github.com/deepchem/deepchem/tree/2.1.0/deepchem/models>

* Link to MultiClassifier source code on Github: <https://github.com/deepchem/deepchem/blob/2.1.0/deepchem/models/tensorgraph/fcnet.py#L26>

* Link to TensorGraph (parent class of MultiClassifier) source code on Github: <https://github.com/deepchem/deepchem/blob/2.1.0/deepchem/models/tensorgraph/tensor_graph.py#L24>

