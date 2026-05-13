

# Fashion-MNIST Classification using Optimized CNNs

This project implements a state-of-the-art Deep Learning model for the classification of fashion article images, based on research from the **Indian Institute of Technology Patna**.

---

### 👕 Project Overview
The goal is to classify images from the **Fashion-MNIST dataset**, a collection of Zalando's fashion article images.

* **Total Examples**: 70,000
* **Training Set**: 60,000 examples
* **Test Set**: 10,000 examples
* **Image Format**: 28x28 grayscale
* **Classes**: 10 distinct fashion categories

---

### 🧠 Model Architectures
This study compares three CNN architectures to evaluate modern deep learning techniques:

* **Vanilla CNN2**: A baseline model with two convolutional and max-pooling layers.
* **CNN2 + BatchNorm**: Incorporates **Batch Normalization** before every convolutional layer to normalize inputs. This reached the same loss in **10 epochs** that took 40 epochs without it.
* **CNN2 + BatchNorm + Skip (SOTA)**: The optimized model utilizing **Residual Skip Connections**. By adding the previous input directly to the convoluted output, it ensures effective gradient propagation.

---

### ⚙️ Training Parameters
A standardized backend is used for all models to ensure fair comparison:

* **MLP Hidden Layer**: 128 neurons with **ReLU** activation
* **Regularization**: **50% Dropout** to prevent overfitting
* **Optimizer**: **Adam optimizer** for loss minimization
* **Output Layer**: 10 neurons with **Softmax** activation

---

### 📊 Results
The optimized model outperforms existing systems reported in literature.

| Model | Test Accuracy (%) |
| :--- | :--- |
| SVC (C=10; kernel: rbf) | 89.70% |
| EDEN | 90.60% |
| **CNN2 + BatchNorm + Skip** | **92.54%** |

---

### 🔍 Key Insights from Research
* **Visualization**: Lower layers detect sharp features (boundaries/corners), while specific kernels act as "sleeve detectors" or "strap detectors".
* **Error Analysis**: The primary source of error is confusion between **T-Shirts, Pullovers, Coats, and Shirts** due to visual similarity in low-resolution grayscale.
* **Specific Error**: In the research, 100 T-Shirt/Top images were wrongly predicted as Coats, and 83 Coats were wrongly predicted as T-Shirt/Tops.

---

### 📚 References
* Bhatnagar, S., Ghosal, D., & Kolekar, M. H. (2017). *Classification of Fashion Article Images using Convolutional Neural Networks*. 2017 Fourth International Conference on Image Information Processing (ICIIP).
