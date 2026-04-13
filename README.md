# Two-Layer Neural Network for MNIST — From Scratch

A two-layer fully connected neural network built from scratch using NumPy to classify handwritten digits from the MNIST dataset. No deep learning frameworks — all forward propagation, backpropagation, and gradient descent are implemented manually.

## Architecture

```
Input (784)  →  Hidden Layer (64, tanh)  →  Output (10, softmax)
```

| Component      | Detail                        |
|----------------|-------------------------------|
| Input          | 784 nodes (28×28 flattened)   |
| Hidden Layer   | 64 nodes, tanh activation     |
| Output Layer   | 10 nodes, softmax activation  |
| Loss Function  | Cross-entropy                 |
| Optimizer      | Full-batch gradient descent   |

## Dataset

- **Source:** MNIST (loaded via Keras)
- **Train:** 60,000 images | **Test:** 10,000 images
- **Preprocessing:** pixel values normalized to [0, 1]; labels one-hot encoded

## Training

| Hyperparameter | Value                |
|----------------|----------------------|
| Learning Rate  | 1.0                  |
| Epochs         | 2,500                |
| Batch Size     | Full batch (60,000)  |
| Training Time  | ~74 minutes          |

## Results

| Split    | Accuracy |
|----------|----------|
| Training | 94%      |
| Test     | 92%      |

- All 10 digit classes achieved 91%+ accuracy
- Digit **5** was the most difficult to classify
- Most common confusions: digits {3, 5, 8} with each other; {4, 7, 9} with each other

## Key Findings

- **Learning rate sensitivity:** A rate of 0.05 degraded accuracy below 80%; a rate of 1.0 converged reliably, reducing cross-entropy loss from ~11 to ~0.23
- **No significant overfitting:** Only 2% gap between train and test accuracy
- **Image orientation matters:** A misclassified tilted "9" was correctly predicted after rotating it −30°, suggesting preprocessing normalization could further improve accuracy

## Implementation Notes

All core components are implemented from scratch with NumPy:

- **Forward pass:** `Z1 = W1·X + b1`, `A1 = tanh(Z1)`, `Z2 = W2·A1 + b2`, `A2 = softmax(Z2)`
- **Backward pass:** Full analytical gradient derivations for `dW1`, `db1`, `dW2`, `db2`
- **Evaluation:** `sklearn` used only for `classification_report` and `confusion_matrix`

## Files

| File | Description |
|------|-------------|
| `Ananta_Thapaliya_Project2_Part2_Two_Layer_Neural_Network_for_MNIST_Dataset.ipynb` | Full notebook with implementation, training, and analysis |

## Context

This is Part 2 of Project 2 from a graduate Deep Learning course (Fall 2020). Part 1 used 10 separate binary logistic regression classifiers (one-vs-rest); this part replaces them with a single unified neural network trained end-to-end with multi-class cross-entropy.
