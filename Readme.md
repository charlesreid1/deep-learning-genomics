# Deep Learning for the Life Sciences (featuring DeepChem)

## Table of Contents

* [About This Repo](#about-this-repo)
* [Installing](#installing)
* [Chapter 3: Machine Learning with DeepChem](#chapter-3-machine-learning-with-deepchem)
* [Chapter 6: Deep Learning for Genomics](#chapter-6-deep-learning-for-genomics)

## About This Repo

This repository is a follow-along companion to
the book <u>Deep Learning for the Life Sciences</u>,
by Bharath Ramsundar et al (published by O'Reilly).

This repository will not refrain from, ahem,
polite commentary on the book's instructions 
and coverage of relevant material.

## Installing

Your options are:

* <s>Install using DeepChem website's instructions</s> (does not include all necessary conda channels)
* <s>Install using instructions in Readme</s> (cose but no cigar, problems with python version)
* <s>Install using instructions in Readme, but specifying Python version</s> (fails with other things...)
* <s>Use Docker</s> (only works if you have a CPU, not mentioned on DeepChem website)
* [Use Binder](Binder.md) (caveat: don't lose your browser window, or all your hard work, or at the very least your nice Jupyter notebook, will disappear forever into the bindether.)
* [Use Vagrant](Vagrant.md) (A DeepChem install option that actually works. Requires a fresh Ubuntu 16.04 image.)

**Note:** You could also use a cloud compute node, 
which you'll end up doing anyway, 
since a virtual machine will be pathetically 
underpowered for machine learning tasks.

## Chapter 3: Machine Learning with DeepChem

Chapter 3 Notes: [Chapter3.md](Chapter3.md)

Outline of Chapter 3:

* DeepChem Datasets (class representing X and y)

* Toxicity dataset
    * tasks (feature labels)
    * datasets (shapes)
    * transformer (balancing transformer for unbalanced data)
    * multitask classifier (models submodule; creating a model, setting parameters, fitting to data)
    * metrics to assess model (metrics submodule)

* MNIST dataset
    * convolutional neural net architecture

## Chapter 6: Deep Learning for Genomics

Chapter 6 Notes: [Chapter6.md](Chapter6.md)

Chapter 6 outline:

* Primer (ha ha) on DNA and RNA

* Transcription factor binding problem
    * Background on what we want to find, challenges, data
    * Use convolutional model to predict binding sites

* Model Number One (convolutional network)
    * Features, labels, weights
    * Network architecture (1D convolution layer, dropout, dense, sigmoid)
    * Dataset loading
    * Metrics (ROC vs epochs)
    * Improvement process - don't change architecture, add more data

* Model Number Two (One Plus Plus)
    * Chromatin accessibility data
    * Difficulty of having multiple features (and weights, and labels, etc.)
    * Resolved by using a generator that returns batches
    * Call `model.fit_generator()` instead of `model.fit()`

* RNA interference problem
    * Background on the problem, how it works
    * siRNA - pieces of RNA that bind to mRNA to turn off expression of a gene
    * Challenge: prediction of siRNA sequences

* Model Number Three (two-layer convolutional network)
    * Data set - 2431 siRNA molecules, 21 bases each, labeled with 0 or 1
    * Network architecture (2x(convolution, dropout), dense)
    * No weights (each sample should contribute equally)
    * Loss function - L2 distance (minimize mean square difference)
    * Metrics - Pearson R coeff, regression
    * Fit model on training data, then evaluate on training and validation data

