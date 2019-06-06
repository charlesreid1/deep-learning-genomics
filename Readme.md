# Deep Learning for Genomics

This repository contains Jupyter notebooks and notes for 
deep learning for genomics. We principally use keras and
scikit-learn for deep learning, but other libraries (joblib,
ray, trace, hyperas, hyperopt) are used along the way as well.

# Notebooks and Topics

## Data Sets

* Data Exploration for DNA transcription binding site data set:
    * [Jupyter notebook: data_exploration_dna_transcription.ipynb](data_exploration_dna_transcription.ipynb)
    * [Google CoLab notebook: data_exploration_dna_transcription.ipynb](https://colab.research.google.com/github/charlesreid1/deep-learning-genomics/blob/master/data_exploration_dna_transcription.ipynb#)

## Convolutional Neural Nets

* Keras 1D CNN for predicting DNA transcription binding sites:
    * [Jupyter notebook: keras_cnn1d_dna_transcription.ipynb](keras_cnn1d_dna_transcription.ipynb)
    * [Google CoLab notebook: keras_cnn1d_dna_transcription.ipynb](https://colab.research.google.com/github/charlesreid1/deep-learning-genomics/blob/master/keras_cnn1d_dna_transcription.ipynb#)

* Keras + Scikit-learn Cross-Validated 1D CNN (transcription factor bind site predictions):
    * [Jupyter notebook: keras_sklearn_cnn1d_dna_transcription.ipynb](keras_sklearn_cnn1d_dna_transcription.ipynb)
    * [Google CoLab notebook: keras_sklearn_cnn1d_dna_transcription.ipynb](https://colab.research.google.com/github/charlesreid1/deep-learning-genomics/blob/master/keras_sklearn_cnn1d_dna_transcription.ipynb#)

* Keras + Scikit-learn Cross-Validated 1D CNN, Applying Power Transform to Chromatin Data:
    * [Jupyter notebook: keras_sklearn_cnn1d_dna_transcription_powerx.ipynb](keras_sklearn_cnn1d_dna_transcription_powerx.ipynb)
    * [Google CoLab notebook: keras_sklearn_cnn1d_dna_transcription_powerx.ipynb](https://colab.research.google.com/github/charlesreid1/deep-learning-genomics/blob/master/keras_sklearn_cnn1d_dna_transcription_powerx.ipynb)

* Keras + Scikit-learn Cross-Validated 1D CNN, Applying Quantile Transform to Chromatin Data:
    * [Jupyter notebook: keras_sklearn_cnn1d_dna_transcription_quantx.ipynb](keras_sklearn_cnn1d_dna_transcription_quantx.ipynb)
    * [Google CoLab notebook: keras_sklearn_cnn1d_dna_transcription_quantx.ipynb](https://colab.research.google.com/github/charlesreid1/deep-learning-genomics/blob/master/keras_sklearn_cnn1d_dna_transcription_quantx.ipynb)

* Hyperas for Hyperparameter Optimization of Cross-Validated 1D CNN (transcription factor bind site predictions):
    * [Jupyter notebook: hyperparameter_cnn1d_dna_transcription.ipynb](hyperparameter_cnn1d_dna_transcription.ipynb)
    * [Google CoLab notebook: hyperparameter_cnn1d_dna_transcription.ipynb](https://colab.research.google.com/github/charlesreid1/deep-learning-genomics/blob/master/hyperparameter_cnn1d_dna_transcription.ipynb#)

* Ray/Tune for Hyperparameter Optimization of Cross-Validated 1D CNN (IN PROGRESS):
    * [Jupyter notebook: ray_tune_cnn1d_dna_transcription.ipynb](ray_tune_cnn1d_dna_transcription.ipynb)
    * [Google CoLab notebook: ray_tune_cnn1d_dna_transcription.ipynb](https://colab.research.google.com/github/charlesreid1/deep-learning-genomics/blob/master/ray_tune_cnn1d_dna_transcription.ipynb#)
