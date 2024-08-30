Fetal Health Classification Using Neural Networks

Table of Contents

Introduction
Dataset
Dependencies
Data Preprocessing
Model Architecture
Model Training
Evaluation
Results
Usage
Contributing
License
Introduction

Reduction of child mortality is a key indicator of human progress and is reflected in several of the United Nations' Sustainable Development Goals. The UN aims to end preventable deaths of newborns and children under 5 years of age by 2030, with a target to reduce under-5 mortality to at least as low as 25 per 1,000 live births. In parallel, maternal mortality remains a significant concern, with a large proportion of deaths occurring in low-resource settings that could be prevented.

Cardiotocograms (CTGs) provide a cost-effective means of assessing fetal health. By analyzing CTGs, healthcare professionals can monitor fetal heart rate, fetal movements, and uterine contractions, which can help prevent child and maternal mortality.

This project uses machine learning to classify fetal health conditions based on features extracted from CTGs. The model aims to classify fetal health into three categories: Normal, Suspect, and Pathological.

Dataset

The dataset used in this project contains 2126 records of features extracted from Cardiotocogram exams. Each record has been classified by three expert obstetricians into one of three classes:

Normal: The fetal health is considered normal.
Suspect: There may be some anomalies in the fetal health.
Pathological: There are serious health concerns for the fetus.
Source: Fetal Health Classification Dataset

Dependencies

This project requires the following Python libraries:

pandas
numpy
missingno
seaborn
matplotlib
scikit-learn
tensorflow

Data Preprocessing

The dataset contains no missing values and all features are numerical. The preprocessing steps include:

Data Normalization: StandardScaler from sklearn is used to scale the features.
Data Shuffling and Splitting: The dataset is shuffled and split into training (80%), validation (10%), and test sets (10%).
Balancing the Dataset: The dataset is highly imbalanced. To address this, we balanced it downwards to match the class with the lowest number of records, which might not be the optimal solution but it ensures balanced classes for training.
Model Architecture

The model is a neural network constructed using TensorFlow and Keras. It has the following architecture:

Input Layer: Takes the input features.
Hidden Layers: Two hidden layers with 21 units each and ReLU activation.
Output Layer: A dense layer with 3 units (for the three classes) and a softmax activation function.
Model Training

The model is compiled using the Adam optimizer and trained using the categorical cross-entropy loss function, which is suitable for multi-class classification. Training is done for 200 epochs with early stopping to prevent overfitting.

Evaluation

The model is evaluated on the test dataset using accuracy and a confusion matrix to understand the performance across different classes.

Results

The model achieved an overall accuracy of 92% on the test set. Below is the confusion matrix for the classification results:

Predicted Normal	Predicted Suspect	Predicted Pathological
Actual Normal	157	8	0
Actual Suspect	2	22	1
Actual Pathological	0	6	18

Contributing

Contributions are welcome! If you have any suggestions or improvements, feel free to open an issue or create a pull request.
