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

- **Source:** MNIST dataset in keras
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


| File | Description |
|------|-------------|
| `Ananta_Thapaliya_Project2_Part2_Two_Layer_Neural_Network_for_MNIST_Dataset.ipynb` | Full notebook with implementation, training, and analysis |
