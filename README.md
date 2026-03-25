<div align="center">

# Satellite Image Classification with Hybrid CNN + Classical ML Models

![Python](https://img.shields.io/badge/Python-3.8+-green?style=for-the-badge&logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-orange?style=for-the-badge&logo=pytorch)
![scikit-learn](https://img.shields.io/badge/scikit--learn-blue?style=for-the-badge&logo=scikit-learn)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter)
![License: MIT](https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge)

</div>

---

## Overview

This project investigates **hybrid image classification pipelines** for satellite remote sensing imagery. Rather than relying solely on end-to-end deep learning, we explore a two-stage approach: using a pretrained **VGG16 CNN as a feature extractor**, then benchmarking five classical machine learning classifiers on those extracted features.

The core question: *can classical ML models match or complement a full deep network when given rich CNN-derived features?*

The study is conducted on the **RSI-CB256 dataset**, a four-class satellite image benchmark, and provides a systematic comparison of task accuracy across all model configurations.

---

## Dataset

**RSI-CB256** — Remote Sensing Image Classification Benchmark

- **4 classes** of satellite sensor imagery
- Images available in two resolutions: `224×224` and `64×64`
- All images are standardized to `224×224` for consistency across experiments

---

![Screenshot from 2024-02-15 22-27-53](https://github.com/9Xxi8Q4f/ML_ImageClassification/assets/89272933/4f321709-e9cb-4be1-a96d-1eee499afa31)

---

## Method

### Pipeline Architecture

![Screenshot from 2024-02-15 22-32-01](https://github.com/9Xxi8Q4f/ML_ImageClassification/assets/89272933/6c0b53dd-a9de-4f3e-8a83-888cfa0dc8dc)

<br/>

The system is built around a two-stage design:

**Stage 1 — Feature Extraction (CNN)**
A VGG16 backbone pretrained on ImageNet is used as a fixed feature extractor via transfer learning. The output of the convolutional layers serves as a rich, high-dimensional feature representation of each satellite image.

**Stage 2 — Classification**
The extracted CNN features are passed to one of two classification heads:

- **Deep Network** — A fully connected neural network trained end-to-end on the VGG16 features
- **Classical ML Classifiers** — The same CNN features are used to train and evaluate five classical models:

| Classifier | Type |
|---|---|
| K-Nearest Neighbors (KNN) | Instance-based |
| Logistic Regression | Linear |
| Support Vector Machine (SVM) | Kernel-based |
| Random Forest (RF) | Ensemble / Bagging |
| AdaBoost | Ensemble / Boosting |

This setup enables a controlled, apples-to-apples comparison: every classifier receives identical feature inputs, so differences in accuracy are attributable purely to the classifier, not the features.

---

## Results

### Deep Network — Training & Validation Performance
## **Training and validation loss and accuracy rate of deep network.**

![Screenshot from 2024-02-15 22-40-02](https://github.com/9Xxi8Q4f/ML_ImageClassification/assets/89272933/b6eba867-3fcd-4707-8a4e-9cc9d21eb518)

![Screenshot from 2024-02-15 22-41-44](https://github.com/9Xxi8Q4f/ML_ImageClassification/assets/89272933/7b9a2ae7-8e88-4f8a-88d5-0a412270d72f)

> Full classifier comparison results and metrics are available in the notebook.

## Key Takeaways

- **Transfer learning is highly effective** — VGG16 features pretrained on ImageNet generalize well to satellite imagery without any fine-tuning of the backbone
- **Classical ML on CNN features is competitive** — Several classical classifiers achieve strong accuracy when given rich deep features, demonstrating that end-to-end training is not always necessary
- **SVM and Logistic Regression** tend to perform best among the classical methods on linearly separable CNN feature spaces
- The hybrid pipeline offers a **practical alternative** in resource-constrained settings where full deep network training is costly

---

## Topics

`machine-learning` `deep-learning` `computer-vision` `image-classification`
`transfer-learning` `vgg16` `svm` `knn` `random-forest` `adaboost`
`satellite-imagery` `remote-sensing` `jupyter-notebook`

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

<div align="center">
  <i>Bursa Uludağ University · Computer Engineering Department</i>
</div>

