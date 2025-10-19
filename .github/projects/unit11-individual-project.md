# Unit 11 – Individual Project: Object Recognition with Convolutional Neural Networks (CNNs)

This individual project explored **object recognition using deep learning**, comparing two approaches on the CIFAR-10 dataset:  
1. A **custom convolutional neural network (CNN)** trained from scratch.  
2. A **VGG16 transfer-learning model** pretrained on ImageNet.  

The aim was to understand how **data preparation, network architecture, and pretrained knowledge** influence model performance and generalisation.

The artefacts below represent my final submission for Unit 11:

- [View Presentation Slides (PDF)](presentation.pdf)  
- [Read Transcript (PDF)](transcript.pdf)

These materials demonstrate my ability to:
- Apply machine learning theory to a practical image-classification problem.  
- Compare architectures and evaluate model performance.  
- Reflect on ethical and professional considerations in deep learning.  
- Communicate complex technical ideas clearly to an academic audience.

---

## Summary of Approach and Key Findings

### Data and Preprocessing
- Used **45 000 images for training**, **5 000 for validation**, and **10 000 for testing**.  
- Normalised pixel values (0–1 range) and one-hot encoded labels.  
- Applied **light data augmentation** (horizontal flips, small rotations, translations, zooms) to improve generalisation.  
- Both models used the same preprocessing pipeline for fair comparison.

### Models
- **Custom CNN:** two convolution–pooling blocks, dense layer (256 units), softmax output.  
  - Optimised with Adam (lr = 1e-3) and early stopping.  
  - Tested with and without augmentation.  
- **VGG16 Transfer Learning:** reused pretrained convolutional base; added custom classifier (global average pooling, dense 256 ReLU, dropout 0.5, softmax).  
  - Frozen lower layers; fine-tuned top layers; early stopping with patience = 5.

---

## Results Summary

| Model | Training Setup | Avg Precision / Recall / F1 | Key Insights |
|--------|----------------|-----------------------------|---------------|
| **CNN (no augmentation)** | Trained from scratch | ≈ 0.67 | Overfitted quickly; confused similar classes (cats vs dogs, vehicles). |
| **CNN (with augmentation)** | Random flips, rotations, translations | ≈ 0.71 | Improved generalisation; more balanced predictions along the confusion-matrix diagonal. |
| **VGG16 Transfer Learning** | Pretrained on ImageNet; fine-tuned top layers | ≈ 0.78 – 0.79 | Strongest overall performance; cleaner diagonal; faster convergence; best generalisation. |

This progression from **0.67 → 0.71 → 0.78** clearly demonstrates the benefits of **data augmentation** and **transfer learning**.  
VGG16 achieved the highest metrics by leveraging pretrained features, confirming that reusing large-scale visual knowledge improves small-dataset performance.

---

## Reflection Notes

This project consolidated my understanding of convolutional networks and deep learning best practices.  
I learned how:
- Validation sets, early stopping, and dropout prevent overfitting.  
- Data augmentation increases model robustness.  
- Transfer learning reduces training time and improves accuracy.  

It also reinforced the importance of **ethical and sustainable AI** — ensuring fairness, transparency, and awareness of computational cost.

---
