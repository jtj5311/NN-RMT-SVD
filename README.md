# NN-RMT-SVD
Accompanying code for the paper "Deep Learning Weight Pruning with RMT-SVD: Increasing Accuracy and Reducing Overfitting"

## Abstract

In this work, we present some applications of random matrix theory for
the training of deep neural networks. Recently, random matrix theory (RMT) has
been applied to the overfitting problem in deep learning. Specifically, it has been
shown that the spectrum of the weight layers of a deep neural network (DNN) can
be studied and understood using techniques from RMT. In this work, these RMT
techniques will be used to determine which and how many singular values should
be removed from the weight layers of a DNN during training, via singular value
decomposition (SVD), so as to reduce overfitting and increase accuracy. We show
the results on a simple DNN model trained on MNIST. In general, these techniques
may be applied to any fully connected layer of a pretrained DNN to reduce the
number of parameters in the layer while preserving and sometimes increasing the
accuracy of the DNN.


## Longer Explanation
It is a known technique to compute the SVD of fully connected layers and then prune
some amount of the smallest values (giving a low rank approximation). 
This allows one to compress neural networks without changing the accuracy (by much),
potentially lowering memory storage requirements and lowering the cost of running a
network (one potential application being deploying the network on low power devices).

In existing literature, the number of singular values to prune is mostly decided in
an ad-hoc manner (for instance, using energy methods or by iteratively checking
the accuracy of the modified network). In this work, we propose a novel principled
approach to deciding how many singular values to prune using random matrix theory(RMT)
to decide which singular values can likely be pruned without modifying accuracy.

Specifically, we assume our weight matrix is of the form signal + noise, leading to
a spiked eigenvalue model. Using the BEMA (Bulk Eigenvalue Matching Analysis) 
algorithm, we can classify each singular value in the spectrum of our weight matrix as 
noise or signal. With this we can then prune some of the noise singular values.

This theory can be used as either a modified training algorithm where one periodically
prunes small singular values during training as a method of impededing overfitting,
or it can be used on a pre-trained network for compression.


## Contact Info
Authors contact info is yms5281@psu.edu, jtj5311@psu.edu, omk5165@psu.edu
