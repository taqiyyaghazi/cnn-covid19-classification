# Image Recognition for X-Ray COVID-19 & Pneumonia

Image recognition to detect early diagnoses of people with COVID-19 or Pneumonia
using patient x-rays. This project is a personal experiment for
apply the Convolutional Neural Network algorithm in recognizing X-Ray images
as an initial diagnosis whether the patient has COVID-19 or Pneumonia.

## About Dataset
The Covid-19 dataset used in this experiment can be downloaded [here](https://www.kaggle.com/datasets/vijaykumar1799/face-mask-detection).
The following is a summary of the dataset.

| Number of Classes  | 3     | 
| :-------- | :------- | 
| Class Details | Normal, Viral Pneumonia, Covid |
| Amount of data | 251 Data Train, 66 Data Validation | 

## Model Architecture
The model architecture used in this experiment is as follows.

`Model: Sequential`
| Layer Type  | Output Shape | Params # | 
| :-------- | :------- | :-------|
| conv2d (Conv2D) | (None, 198, 198, 8) | 224 |
| max_pooling2d (MaxPooling2D) | (None, 99, 99, 8) | 0 |
| conv2d_1 (Conv2D) | (None, 97, 97, 16) | 1168 |
| max_pooling2d_1 (MaxPooling2D) | (None, 48, 48, 16) | 0 |
| conv2d_2 (Conv2D) | (None, 46, 46, 32) | 4640 |
| max_pooling2d_2 (MaxPooling2D) | (None, 23, 23, 32) | 0 |
| flatten (Flatten)  | (None, 16928) | 0 |
| dense (Dense) | (None, 64) | 1083456 |
| dense_1 (Dense) | (None, 3) | 195 |
| Total params: 1,089,683 |
| Trainable params: 1,089,683 |
| Non-trainable params: 0 |

## Model Evaluation
Model training is performed with `epoch = 50` and uses an Early Stopping callback which will stop model training if `val_accuracy` has converged to a value.
From the results of the training, the evaluation of the model in the last epoch (epochs = 24) was obtained as follows.
| Metrics  | Value |
| :-------- | :------- |
| Accuracy | 1.0000 |
| Loss | 0.0036 |
| Val Accuracy | 0.9062 |
| Val Loss | 0.2128 |

![Accuracy Plot](https://raw.githubusercontent.com/taqiyyaghazi/cnn-covid19-classification/main/img/accuracy.png)
![Loss Plot](https://raw.githubusercontent.com/taqiyyaghazi/cnn-covid19-classification/main/img/loss.png)

## Acknowledgements

 - [Sumber Data](https://www.kaggle.com/datasets/pranavraikokte/covid19-image-dataset)
