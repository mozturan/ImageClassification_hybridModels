# IMAGE CLASSIFICATION w/ hybrid classification algorithms

**Satellite image classification on different ml algorithms.**
----------------

RSI-CB256 dataset, which contains sensor images of four different classes, was used to test different hybrid classification algorithms. Since the images have two different resolutions, 224x224 and 64x64, all images were resized and converted to 224x224.

![Screenshot from 2024-02-15 22-27-53](https://github.com/9Xxi8Q4f/ML_ImageClassification/assets/89272933/4f321709-e9cb-4be1-a96d-1eee499afa31)

The architecture of the hybrid models was created as "CNN + classical ML models" and the CNN architecture was provided from the VGG16 architecture. A backbone created using transfer learning technique with CNN (VGG16) and ImageNet was then given to the fully connected layer and classification was made with neural networks. The outputs of the CNN layers were drawn and given to KNN, Logistic Regression, SVM, RF, AdaBoost classifiers, and the performance comparison of the classification of CNN outputs was made.

![Screenshot from 2024-02-15 22-32-01](https://github.com/9Xxi8Q4f/ML_ImageClassification/assets/89272933/6c0b53dd-a9de-4f3e-8a83-888cfa0dc8dc)

## **Training and validation loss and accuracy rate of deep network.**

![Screenshot from 2024-02-15 22-40-02](https://github.com/9Xxi8Q4f/ML_ImageClassification/assets/89272933/b6eba867-3fcd-4707-8a4e-9cc9d21eb518)

![Screenshot from 2024-02-15 22-41-44](https://github.com/9Xxi8Q4f/ML_ImageClassification/assets/89272933/7b9a2ae7-8e88-4f8a-88d5-0a412270d72f)
