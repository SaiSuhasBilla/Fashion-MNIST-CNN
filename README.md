# Fashion-MNIST CNN Implementation
# Fashion-MNIST Classification using Optimized CNNs

[cite_start]This project implements a state-of-the-art Deep Learning model for the classification of fashion article images, based on research from the **Indian Institute of Technology Patna**[cite: 5, 10].

---

### 👕 Project Overview
[cite_start]The goal is to classify images from the **Fashion-MNIST dataset**, a collection of Zalando's fashion article images[cite: 18].

* [cite_start]**Total Examples**: 70,000[cite: 18].
* [cite_start]**Training Set**: 60,000 examples[cite: 18].
* [cite_start]**Test Set**: 10,000 examples[cite: 18].
* [cite_start]**Image Format**: 28x28 grayscale[cite: 19].
* [cite_start]**Classes**: 10 distinct fashion categories[cite: 19].

---

### 🧠 Model Architectures
[cite_start]This study compares three CNN architectures to evaluate modern deep learning techniques[cite: 12]:

* [cite_start]**Vanilla CNN2**: A baseline model with two convolutional and max-pooling layers[cite: 87, 88].
* [cite_start]**CNN2 + BatchNorm**: Incorporates **Batch Normalization** before every convolutional layer to normalize inputs[cite: 67, 91]. [cite_start]This reached the same loss in **10 epochs** that took 40 epochs without it[cite: 94].
* [cite_start]**CNN2 + BatchNorm + Skip (SOTA)**: The optimized model utilizing **Residual Skip Connections**[cite: 95]. [cite_start]By adding the previous input directly to the convoluted output ($y = convolution(x) + x$), it ensures effective gradient propagation[cite: 100, 102].



---

### ⚙️ Training Parameters
[cite_start]A standardized backend is used for all models to ensure fair comparison[cite: 104, 138]:

* [cite_start]**MLP Hidden Layer**: 128 neurons with **ReLU** activation[cite: 105, 106].
* [cite_start]**Regularization**: **50% Dropout** to prevent overfitting and improve generalization[cite: 113, 115].
* [cite_start]**Optimizer**: **Adam optimizer** for loss minimization[cite: 132].
* [cite_start]**Output Layer**: 10 neurons with **Softmax** activation for class probability distribution[cite: 105, 106, 112].

---

### 📊 Results
[cite_start]The optimized model outperforms existing systems reported in literature[cite: 14, 201].

| Model | Test Accuracy (%) |
| :--- | :--- |
| SVC ($C=10$; kernel: rbf) | [cite_start]89.70% [cite: 202] |
| EDEN | [cite_start]90.60% [cite: 202] |
| **CNN2 + BatchNorm + Skip (Proposed)** | [cite_start]**92.54%** [cite: 205, 387] |

---

### 🔍 Key Insights from Research
* [cite_start]**Visualization**: Lower layers detect sharp features (boundaries/corners), while specific kernels act as "sleeve detectors" or "strap detectors"[cite: 216, 225, 226].
* [cite_start]**Error Analysis**: The primary source of error is confusion between **T-Shirts, Pullovers, Coats, and Shirts** due to visual similarity in low-resolution grayscale[cite: 245, 322, 324].
* [cite_start]**Specific Error**: 100 T-Shirt/Top images were wrongly predicted as Coats, and 83 Coats were wrongly predicted as T-Shirt/Tops[cite: 259, 260].

---

### 📚 References
* Bhatnagar, S., Ghosal, D., & Kolekar, M. H. (2017). *Classification of Fashion Article Images using Convolutional Neural Networks*. [cite_start]2017 Fourth International Conference on Image Information Processing (ICIIP)[cite: 1, 2, 3].
