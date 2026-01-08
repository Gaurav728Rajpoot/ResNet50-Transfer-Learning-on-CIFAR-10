# 🐯 CIFAR-10 Image Classification: From 22% to 95% Accuracy

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow&logoColor=white)
![Status](https://img.shields.io/badge/Status-Success-brightgreen)
![Accuracy](https://img.shields.io/badge/Final_Accuracy-95%25-success)

This project demonstrates a complete Deep Learning pipeline using **Transfer Learning** to classify images from the CIFAR-10 dataset. By refining a pre-trained **ResNet50** model, we achieved a massive performance jump from an initial 22.6% to ~95%.

---

## 📝 Project Steps & Workflow

### 1. 🖼️ Visualizing the Dataset
We utilized the **CIFAR-10** dataset, which consists of 60,000 32x32 color images in 10 classes (airplanes, cars, birds, cats, etc.).
- **Action:** Visualized random sample images to understand the data distribution and quality.

### 2. 🧹 Data Normalization
To ensure the neural network trains effectively, the pixel intensity values were scaled.
- **Action:** Normalized pixel values from the range `0-255` to `0-1`.

### 3. 🏗️ Initial Model Building (Transfer Learning)
We constructed a baseline model using **ResNet50** pre-trained on ImageNet.
- **Base:** ResNet50 (Frozen layers to preserve learned features).
- **Head:** A custom classifier added on top for feature extraction.
- **Goal:** To see how well the pre-trained weights perform without modification.

### 4. 📉 Initial Evaluation & Analysis
The initial model performance was analyzed to identify bottlenecks.
- **Result:** The model achieved only **22.6% Accuracy**.
- **Visualization:** Plotted `Train Accuracy vs. Val Accuracy` and `Train Loss vs. Val Loss`.
- **Insight:** The model was significantly underfitting, likely due to the domain gap between ImageNet and CIFAR-10 (different image resolutions).

### 5. 🔄 Data Augmentation
To prevent overfitting and improve the model's ability to generalize, I used data generated data augmentation techniques on the fly.
- **Techniques Used:** Rotation, Zooming, Horizontal Flips, and Shifts.

### 6. 🚀 Building the Final Model (Fine-Tuning)
To boost performance, we modified the training strategy.
- **Action:** Unfroze the **last convolutional block** of the ResNet50 base.
- **Training:** Retrained the model with the custom classifier and the fine-tuned block using the augmented data.

### 7. 🏆 Final Results
The optimizations led to state-of-the-art performance.
- **Final Accuracy:** **~95%**
- **Visualization:** Generated final `Train vs. Val` Accuracy and Loss curves showing convergence.

---

## 📊 Performance Comparison

| Model Phase | Strategy | Accuracy |
| :--- | :--- | :---: |
| **Initial** | Frozen Base + Custom Head | 22.6% |
| **Final** | Fine-Tuned Last Block + Augmentation | **~95%** |

---

## 💻 How to Run
1. Clone this repository.
2. Install dependencies: `pip install tensorflow numpy matplotlib`
3. Open `project_final.ipynb` in Jupyter Notebook or Google Colab.
4. Run all cells to replicate the analysis and training process.
5. Visualize the final result along with the custom predicted images.
---
*Created with ❤️ using TensorFlow & Keras*
