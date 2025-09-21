# Neural Networks Concepts

## Sigmoid Function

An activation function used in neural networks that squashes input values into a range between 0 and 1.

Formula: $1 / (1 + e^{-sum_func})$.

It introduces non-linearity, allowing the network to learn complex patterns. The input sum_func typically represents the weighted sum of inputs to a neuron. It enables neural networks to learn and model complex, non-linear relationships in data, which is essential for solving many real-world problems. 

## Neuron

The fundamental building block of a neural network.
It receives inputs, processes them using an activation function, and produces an output.

## Layer

A group of neurons that are organized together at a specific stage in the network.
Processes information collectively before passing it to the next layer.

### Types of Layers

- Input Layer: Presents the raw input data to the network. The number of nodes equals the number of input features.
- Hidden Layers: Layers between the input and output layers. Their neuron values are not directly observed in the training data, hence "hidden." They learn to extract and combine features.
- Output Layer: Produces the final output of the network based on the problem type (e.g., one neuron for binary classification, multiple for multi-class classification).

## Simple Perceptron:

A basic type of neural network with no hidden layers. Inputs are directly connected to the output neuron.
It is limited in what it can learn (cannot solve non-linear problems like XOR).

## Deciding Network Architecture (Number of Layers and Neurons):

No strict rules - it's an iterative process of experimentation. Consider the complexity of the problem, amount of data, and computational resources.
Start simple and gradually increase complexity if needed. Monitor for overfitting and use techniques like regularization if necessary.
The number of input and output neurons is determined by the data and problem, while hidden layer sizes require experimentation.

## Weights

Weights are parameters in a neural network that determine the strength of the connections between neurons in adjacent layers. They are represented as matrices.

Weights are learned during the training process. They transform the input data as it passes through the network, allowing the network to learn complex patterns and relationships.

Weight Matrices in a Network with One Hidden Layer:

- weights_0 (Input to Hidden): Connects the input layer to the hidden layer. Its shape is (number of input features, number of hidden neurons).
- weights_1 (Hidden to Output): Connects the hidden layer to the output layer. Its shape is (number of hidden neurons, number of output neurons).

The number of weight matrices depends on the number of layers with connections between them. For a standard feedforward network, there is a set of weights for each connection between adjacent layers. A network with one hidden layer has two sets of weights. A network with multiple hidden layers will have a set of weights for each connection (input to first hidden, first hidden to second hidden, etc., and last hidden to output).


Weights must be initialized before training. Random initialization is a common and effective strategy to break symmetry and provide a starting point for learning. Poor initialization can hinder training or lead to "dead" neurons.
