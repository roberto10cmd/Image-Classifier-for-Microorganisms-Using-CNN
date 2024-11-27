# Image-Classifier-for-Microorganisms-Using-CNN

## Description
This project implements an image classifier for microorganisms using a Convolutional Neural Network (CNN). The dataset used contains images of microorganisms, divided into 8 specific types:
1. Amoeba
2. Euglena
3. Hydra
4. Paramecium
5. Rod_bacteria
6. Spherical_bacteria
7. Spiral_bacteria
8. Yeast

## Data Preprocessing
The images undergo a series of transformations for data augmentation, which helps the model generalize better and avoid overfitting. The transformations applied include:
- **Resizing** the images to 128x128 pixels.
- **Random rotation** with a maximum angle of 10 degrees.
- **Random changes** in brightness, contrast, saturation, and hue.
- **Conversion to tensor** which normalizes pixel values in the range [0, 1].

After preprocessing, the dataset is split into three subsets:
- **Train**: 80% of the dataset.
- **Validation**: 10% of the dataset.
- **Test**: 10% of the dataset.

## CNN Model
The model is a Convolutional Neural Network (CNN) consisting of the following layers:
1. **Convolutional Layer**: Applies filters to extract features from the images.
2. **ReLU**: Activation function to introduce non-linearity into the model.
3. **Pooling Layer**: Reduces the image size while extracting the most important features.
4. **Fully Connected Layer**: Dense layers that perform the final classification.

## Performance Analysis
The performance of the model is analyzed based on the following factors:

### 1. **Learning Rate**
The learning rate controls the step size the optimizer takes when updating the model's parameters. I tested two learning rates:
- `lr = 0.001`
- `lr = 0.01` (this was the most beneficial)

### 2. **Batch Size**
The batch size refers to the number of examples the model processes before updating its parameters. I tested several values:
- `batch_size = 32`
- `batch_size = 64`
- `batch_size = 128` (this provided more stable and precise updates, though it requires more memory)

### 3. **Number of Epochs**
The number of epochs represents how many times the model iterates over the entire training dataset. I tested the model for 20 epochs. A small number of epochs can lead to underfitting, while too many epochs can result in overfitting.

### 4. **Optimizers**
Optimizers are algorithms that adjust the model's parameters to minimize the loss function:
- **SGD (Stochastic Gradient Descent)** updates parameters using the gradient estimated for each batch.
- **Adam**: A combination of RMSprop and momentum, which adapts the learning rates for each parameter, making it more efficient for my dataset.
