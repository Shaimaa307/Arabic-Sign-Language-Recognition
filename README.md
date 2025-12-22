

# 🤖 Arabic Sign Language (ArSL) Recognition: A Hybrid YOLO-CNN Approach

## 🌟 Project Overview: Bridging the Communication Gap

This project addresses the critical challenge of automating **Arabic Sign Language (ArSL) recognition** using a robust Deep Learning framework. Our goal was to create a highly reliable system that can accurately classify static hand gestures representing the Arabic alphabet, even when faced with complex real-world issues like **cluttered backgrounds** and **class imbalance**.

The success of this system stems from a strategic, hybrid methodology that prioritizes data cleanliness and feature isolation, resulting in a model that is not only accurate but also statistically trustworthy.

## ⚙️ The Hybrid Methodology: Focus First, Classify Second

The core of our solution is a two-stage pipeline designed to eliminate ambiguity and maximize classifier performance:

1. **Hand Detection & Isolation (YOLO-Based Detection):** The input image is first processed by a **YOLO (You Only Look Once)** object detection model. YOLO's role is to precisely locate and crop the hand, acting as an intelligent pre-processor. This crucial step **strips away background noise and irrelevant clutter**, presenting a clean, standardized image to the next stage.
2. **Fine-Grained Classification (EfficientNetB0 CNN):** The isolated hand image is fed into a **Convolutional Neural Network (CNN)** based on the efficient **EfficientNetB0** architecture. By receiving only clean, relevant data, the CNN can focus entirely on learning the subtle differences between the **28 distinct ArSL gestures**.

This hybrid approach, coupled with comprehensive **Data Augmentation** to mitigate the  class imbalance, ensures a highly reliable final classification.

## 🚀 Key Results & System Trustworthiness

The model's performance on the test set far exceeded our initial targets, demonstrating exceptional generalization capability:

| Metric | Value | Interpretation |
| --- | --- | --- |
| **Final Test Accuracy** | **99.66%** | Achieved near-perfect classification performance on unseen data. |
| **Mean Confidence (Correct)** | **0.9831** | The model is virtually certain when it makes a correct prediction. |
| **Mean Confidence (Incorrect)** | **0.3316** | Crucial insight: The model **"knows when it doesn't know,"** as confidence sharply drops during errors, allowing for a strong safety threshold. |

The significant gap between correct and incorrect confidence scores proves the system's **statistical trustworthiness**—a high confidence prediction can be treated as reliable in a real-world application.

## 📊 Dataset Information

This project utilizes the following dataset, which is formatted for YOLO (images and corresponding label files) and contains the initial challenges of background clutter and class imbalance that this project addresses:

* **Dataset:** Arabic Sign Language (Unaugmented Dataset)
* **Source:** [Kaggle Dataset Link](https://www.kaggle.com/datasets/sabribelmadoui/arabic-sign-language-unaugmented-dataset)

## 🛠️ Project Setup and Dependencies

To run and reproduce the experiments, please follow these steps:

1. **Clone the repository:**
```bash
git clone https://github.com/YourUsername/ArSL-YOLO-CNN.git
cd ArSL-YOLO-CNN

```


2. **Download Data:** Download and extract the dataset from the Kaggle link above into your project directory. Ensure the images and label files are correctly structured for YOLO.
3. **Install Dependencies:** We recommend using a Python environment with GPU support (if available).
```bash
pip install tensorflow keras numpy pandas matplotlib




## 🛣️ Future Work and Roadmap

While this is a strong foundation, the ultimate goal is dynamic, real-time recognition. Future development efforts will focus on:

* **Temporal Recognition:** Expanding the system to handle **video sequences** using time-series models (LSTMs or Transformers) to capture the natural motion and flow of sign language.
* **End-to-End Pipeline:** Exploring the integration of the detection and classification components into a single, unified, end-to-end trainable network to enhance robustness.

We welcome contributions and suggestions to expand this work, furthering the support for Arabic Sign Language in technology.
