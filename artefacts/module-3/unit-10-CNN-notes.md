[← Back to Unit 10](./)

# Study Notes – Neural Networks & Convolutional Neural Networks (CNNs)

## Artificial Neural Networks (ANNs)
- Definition: Computational models inspired by the way the human brain processes information.  
- Structure:  
  - Neurons (nodes): Basic processing units performing simple computations.  
  - Layers:  
    - Input layer – receives data.  
    - Hidden layers – process data using weighted connections.  
    - Output layer – produces final predictions.  
  - Weights & Biases: Adjust input influence and shift activation.  
  - Activation Functions: Introduce non-linearity (e.g., ReLU, Sigmoid, Tanh) to help learn complex patterns.  

---

## Training Process
1. Initialization: Randomly set starting weights.  
2. Forward propagation: Pass input through the network to get an output.  
3. Loss calculation: Compare prediction to true label using a loss function (e.g., high loss if “cat” predicted as 80% dog).  
4. Backpropagation: Adjust weights using the gradient of the loss to reduce error.  
5. Iteration: Repeat across epochs until loss is minimized.  

---

## Key Hyperparameters to Tune
- Architecture: Number/type of layers, convolution kernel size, etc.  
- Activation function: Controls signal flow (ReLU, Sigmoid, Tanh).  
- Loss function: Defines the error measure (cross-entropy for classification, MSE for regression).  
- Optimizer: Updates weights (e.g., SGD, Adam, RMSProp).  
- Learning rate (LR): Size of update steps.  
- Batch size: Number of samples before weight update.  
- Epochs: How many times the model sees the entire dataset.  

---

## Data Splitting
| Set | Purpose | Typical Size |
|------|----------|--------------|
| Training set | Used to train and update weights | 60–80% |
| Validation set | Used to tune hyperparameters and prevent overfitting | 10–20% |
| Test set | Used once at the end to evaluate final model performance | 10–20% |

Tip: If the dataset is small → use a larger validation set or apply data augmentation.  

---

## Convolutional Neural Networks (CNNs)
- CNNs are specialized neural networks for image and pattern recognition.  
- Instead of manually designing features, CNNs learn features automatically during training (e.g., edges, shapes, textures).  
- You don’t instruct a CNN to find “cat ears” — it discovers these through its filters.  
- Typical architecture includes convolution layers, pooling layers, and fully connected layers.  
- CNNs are a core model in deep learning (DL), which is essentially ML using neural networks with multiple layers.

---

## Example Dataset – CIFAR-10
- Released: 2009 by the University of Toronto.  
- Description: 60,000 colour images (32×32 pixels) in 10 categories (e.g., airplane, cat, ship).  
- Purpose: Standard benchmark for testing image classification algorithms.  
- Complexity: Harder than MNIST but simpler than ImageNet — a vital stepping stone for computer vision research.  
- Link: https://www.cs.toronto.edu/~kriz/cifar.html

---

## Summary
| Concept | Key Point |
|----------|------------|
| ANNs | Mimic biological brains using layers of interconnected nodes. |
| DL vs ML | Deep learning = ML with multi-layer neural networks. |
| CNNs | Learn image features automatically via convolutions. |
| Training | Involves forward pass, loss calculation, and backpropagation. |
| Performance | Depends on architecture, learning rate, loss, and optimizer tuning. |
