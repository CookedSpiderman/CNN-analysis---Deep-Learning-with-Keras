# CNN Brain Tumor Classification Project - Dev Nair DXN210046

## Project Description

This project uses transfer learning with MobileNetV2 in Keras to classify brain MRI images into four classes:

- Glioma
- Meningioma
- No Tumor
- Pituitary

The project includes an initial feature extraction stage followed by fine-tuning of selected MobileNetV2 layers.

## Google Colab

Public Colab Notebook:

https://colab.research.google.com/drive/1HLsYu3Dauf1IFiB-vNhZGr4KmHR9mx8D?usp=sharing

The notebook contains all code and saved outputs for the six experiments performed in the project.

## Dataset

The Brain Tumor MRI Dataset from Kaggle is used for this project.

Dataset source:

https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset

The dataset is downloaded directly in Google Colab using the `kagglehub` Python package, so no local dataset path is required.

The dataset contains four image classes:

- glioma
- meningioma
- notumor
- pituitary

The provided Training directory contains 5,600 images with 1,400 images per class. The Training directory is divided into 80% training data and 20% validation data. The separate labeled Testing directory is used only for final model evaluation.

## Environment

Google Colab with a GPU runtime is recommended.

To enable a GPU in Colab:

1. Open the Runtime menu.
2. Select Change runtime type.
3. Set Hardware accelerator to T4 GPU.
4. Save the setting.

## Required Python Libraries

The notebook uses the following libraries:

- TensorFlow / Keras
- kagglehub
- NumPy
- Matplotlib
- Pillow
- os

The notebook installs `kagglehub` automatically if necessary.

## Running the Notebook

1. Open the public Google Colab notebook or upload the submitted `.ipynb` file to Google Colab.
2. Enable a T4 GPU using the Colab runtime settings.
3. Run the notebook cells from top to bottom.
4. The dataset will automatically download from Kaggle using `kagglehub`.
5. The notebook creates the training, validation, and test datasets and resizes images to 224 x 224 pixels.
6. Run each experiment in order.
7. Allow each model training cell to finish before continuing to the next experiment.
8. The final sections evaluate the selected model on the test set and generate the required sample prediction grid.

## Model

The final selected model uses MobileNetV2 transfer learning.

Feature extraction settings:

- Pre-trained base: MobileNetV2 with ImageNet weights
- MobileNetV2 initially frozen
- Optimizer: Adam
- Learning rate: 0.001
- Batch size: 32
- Dropout: 0.2
- Epochs: 10

Fine-tuning settings:

- Top 20 MobileNetV2 layers unfrozen
- Learning rate: 0.00001
- Fine-tuning epochs: 5

The selected model achieved approximately 95.6% validation accuracy and 90.3% final test accuracy.

## Experiments

Six experiments were performed by changing settings including:

- Data augmentation
- Learning rate
- Dropout
- Number of unfrozen MobileNetV2 layers

The complete experiment results and outputs are saved in the notebook and summarized in the project report.

## Execution Time

Training time depends on the available hardware. A Google Colab T4 GPU is strongly recommended.

Several experiments are trained for multiple epochs, so running the entire notebook may take several minutes. CPU execution will be considerably slower.

## Files Submitted

- CNN project `.ipynb` notebook with saved outputs
- Project report in PDF format
- `README.md`

The image dataset itself is not included because it is downloaded directly from its public Kaggle source.