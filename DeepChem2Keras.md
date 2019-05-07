# DeepChem to Keras (Chapter 6)

Notes on converting the example in Chapter 6
from DeepChem to Keras.

## Overview: All About the Data

The main difficulty in translating the examples
in Chapter 6 from DeepChem to Keras are centered
around the data - how to load it and how to feed it
to the neural network model.

DeepChem uses `joblib` to store and load the data
sets for Chapter 6 in a format similar to a pickle
(compressed bundled data). We can use joblib to
load the datasets directly and bypass DeepChem's
data loading classes.

DeepChem also implements methods for creating
data generators for batch data, which make it
easier to deal with out-of-memory data. Switching
to Keras also requires us to write our own data 
generator function(s).

Most of the DeepChem network layers translate 
directly to Keras layers.

