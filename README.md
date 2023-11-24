# Computer-Vision-Image-Classification-for-Cracks-or-No-Cracks-Dataset

## An image classification to classify concretes with or without cracks

This assessment necessitated an image classification task to distinguish between concrete surfaces with and without cracks. Various types of common concrete cracks were considered, including hairline cracks that typically emerge in concrete foundations during the curing process, shrinkage cracks occurring as the concrete cures, settlement cracks resulting from uneven settling or inadequate compaction of the ground beneath the slab, and structural cracks formed due to design errors. The dataset used in this project are from https://data.mendeley.com/public-files/datasets/5y9wdsg2zt/files/8a70d8a5-bce9-4291-bab9-b48cfb3e87c3/file_downloaded that contains the images of concrete surfaces with and without cracks.

## Directory Structure
- [Imran_Assesment1.py](https://github.com/Imraanjaafar/Computer-Vision-Image-Classification-for-Cracks-or-No-Cracks-Dataset/blob/main/Imran_Assesment1.py)

##Import Packages

- The necessary libraries are imported, including TensorFlow, Keras, NumPy, Matplotlib, and others.

##Data Loading

- The code specifies paths for training, validation, and test datasets and sets batch size and image size.
- It loads datasets using tf.keras.utils.image_dataset_from_directory for training, validation, and test sets.

##Inspect Data Examples:

- The code visualizes a few examples from the training dataset using Matplotlib.

##Further Split Validation and Test Dataset:

- The validation dataset is split from the test dataset using tf.data.experimental.cardinality.

##Convert Datasets into PrefetchDataset:

- The code converts the TensorFlow datasets into PrefetchDataset for better performance using the prefetch method.

##Create a Sequential Model for Image Augmentation:

- Image augmentation is set up using a Sequential model with random flip and rotation.

##Apply Image Augmentation:

- Image augmentation is applied to a single image from the training dataset, and the results are visualized.

##Define a Layer for Data Normalization:

- A layer for data normalization is defined using MobileNetV2's preprocess_input function.

##Load Pretrained Model and Freeze Feature Extractor:

- The ResNet50 model pretrained on ImageNet is loaded using Keras applications.
- The feature extractor is frozen to retain the pretrained weights.

##Create Model Using Functional API:

- A new model is constructed using the Functional API, incorporating data augmentation, data normalization, feature extraction, and classification layers.

##Compile the Model:

- The model is compiled with an Adam optimizer, sparse categorical crossentropy loss, and accuracy as the evaluation metric.

##Create TensorBoard Callback:

- A TensorBoard callback is set up for model training visualization.

##Evaluate Model Before Training:

- The model is evaluated on the test dataset before training.

##Model Training:

- The model is trained on the training dataset with early stopping and TensorBoard callbacks.

##Fine-tune the Model:

- The top layers of the pretrained model are unfrozen for fine-tuning.
- The model is compiled again, and fine-tuning is performed.

##Evaluate Model After Fine-tuning:

- The model is evaluated on the test dataset after fine-tuning.

##Deployment:

- A batch of images from the test dataset is used for prediction.
- Predictions and actual labels are visualized using Matplotlib.

##Save the Model:

- The trained model is saved as 'transfer_learning_model.h5'.

## Results
- The model achieved an accuracy of 96.16% on the test set, which demonstrates its effectiveness in classifying concrete images with and without cracks.

## Model Architecture

- The model design utilizes the ResNet50 architecture that includes the layers of the model, the output shape of each layer, and the number of parameters in each layer.
- Presented below is an overview of the model's architecture:

![model](https://github.com/Imraanjaafar/Computer-Vision-Image-Classification-for-Cracks-or-No-Cracks-Dataset/assets/151133555/5122dcb3-8ac0-4fb4-90fb-14587e9001ea)
