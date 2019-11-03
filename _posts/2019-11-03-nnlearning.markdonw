---
layout: post
comments: False
title: "Neural Network Learning Rule"
excerpt: "nn learning rule"
date:   2019-11-03 14:34:03
mathjax: true
---

# Synaptic weight

In neuroscience and computer science, synaptic weight refers to the strength or amplitude of a connection between two nodes, corresponding in biology to the amount of influence the firing of one neuron has on another. The term is typically used in artificial and biological neural network research.[1]  
Learning how the weight changing is central to neural network.

# Neural Network Learning Rule

### 1. Unsupervised learning

#### 1.1 Hebb's Rule

Hebb's based on Hebbian theory, which is a neuroscientific theory claiming that an increase in synaptic efficacy arises from a pre-synaptic cell's repeated and persistent stimulation of a post-synaptic cell. that is to say with the repeated and persistent stimulation between two neuron, the synaptic efficacy will increasing.

The Hebb rule can be formula as:
$$
w_{ij}=x_i y_j
$$
we talking about the case of linear neuron:
$$
y_j = \sum_i{x_i w_{ij} } \quad or \quad \mathbf{y} = \mathbf{x} \mathbf{w}
$$
the synaptic weight $w_{ij}$ is the weight of the synaptic weight from input neuron $x_i$ to output neuron $y_j$. Since the synaptic weight relative with the input neuron and output neuron, thus the rectified synaptic weight formulaic description is:
$$
\Delta{w_{ij}}=\alpha x_i y_j \quad or \quad \Delta{\mathbf{w}}=\alpha \mathbf{x}^T \mathbf{y}
$$
where $\alpha$ is learning rate, if the pre-neuron $x_i$  and post-neuron $y_j$ are activated simultaneously, the weight $w_{ij}$ would be positive, otherwise if pre-neuron is active but post-neuron is suppressed. However, this rule is not stable, the $\Delta{\mathbf{w}}$ will not convergence to an stable value, i.e., $\Delta{\mathbf{w}} \ne 0$. Let us exploit why.
$$
\Delta{\mathbf{w}} = \alpha \mathbf{x}^T\mathbf{y}=\alpha \mathbf{x}^T \mathbf{x}\mathbf{w}=\mathbf{C} \mathbf{w}
$$
when training is convergence,  $\Delta \mathbf{w}=0$ , where $\mathbf{C}$ is the covariance matrix, the essential of Hebb rule is to find the resolver of $\mathbf{C}\mathbf{w}=0$, but this formula is not always existing resolver, result in the training of Hebb rule is not always convergence.



#### 1.2 Oja's Rule

Oja's rule is another synaptic weight learning rule, it will offer a negative feedback to make training convergence. The Oja's learning formulaic expression is following:
$$
\Delta{\mathbf{w}}= \alpha(\mathbf{x}^T\mathbf{y} - \mathbf{y}^T\mathbf{y}\mathbf{w})
$$
We care about the linear case, this formulation will transform as:
$$
\Delta{\mathbf{w}}=\alpha(\mathbf{x}^T\mathbf{y} - \mathbf{y}^T\mathbf{y}\mathbf{w})=\alpha(\mathbf{x}^T\mathbf{x}\mathbf{w}-\mathbf{w}^T\mathbf{x}^T \mathbf{x}\mathbf{w} \mathbf{w}) \\
=\alpha(\mathbf{C}\mathbf{w}-\mathbf{w}^T\mathbf{C}\mathbf{w}\mathbf{w})=\alpha({\mathbf{C}}\mathbf{w}-\lambda \mathbf{w})
$$
Aim at $\Delta{\mathbf{w}}=0$, so the $\mathbf{C}\mathbf{w}=\lambda \mathbf{w}$, the $\lambda=\mathbf{x}^T \mathbf{C} \mathbf{x}$. The process of training Oja' rule transform to get the eigenvector. In some aspect, this process is also the PCA process.



### 2. Supervised Learning

#### 2.1 Radial Basis Function
TODO


#### 2.2 Backpropagation
TODO


#### Reference
[1] [synaptic weight](https://en.wikipedia.org/wiki/Synaptic_weight)
