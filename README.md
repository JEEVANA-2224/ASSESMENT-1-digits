Handwritten Digit Recognition using Artificial Neural Network (ANN)
Project Overview

This project demonstrates how to build a basic Artificial Neural Network (ANN) using TensorFlow and Keras to recognize handwritten digits from the MNIST dataset.

The MNIST dataset contains grayscale images of handwritten digits from 0 to 9. Each image is of size 28 × 28 pixels.

Objectives
Load and visualize the MNIST dataset
Preprocess image data for deep learning
Build an ANN model using Keras Sequential API
Train the model using TensorFlow
Evaluate model performance
Predict handwritten digit labels
Technologies Used
Python
TensorFlow
Keras
NumPy
Matplotlib
Dataset

The project uses the built-in MNIST dataset available in Keras.

Training Images: 60,000
Testing Images: 10,000
Image Size: 28 × 28 pixels
Classes: Digits 0–9
Project Steps
1. Data Loading

The MNIST dataset is loaded using Keras datasets module.

(X_train, y_train), (X_test, y_test) = keras.datasets.mnist.load_data()
2. Data Visualization

The handwritten digit images are displayed using Matplotlib.

plt.matshow(X_train[0])
3. Data Preprocessing
Pixel values are normalized between 0 and 1
Images are flattened from 28×28 into 784 input features
X_train = X_train / 255
X_test = X_test / 255
4. Model Architecture

The ANN model contains:

Input Layer: 784 neurons
Hidden Layer: 100 neurons with ReLU activation
Output Layer: 10 neurons with Sigmoid activation
model = keras.Sequential([
    keras.layers.Dense(100, input_shape=(784,), activation='relu'),
    keras.layers.Dense(10, activation='sigmoid')
])
5. Model Compilation

The model is compiled using:

Optimizer: Adam
Loss Function: Sparse Categorical Crossentropy
Metric: Accuracy
model.compile(
    optimizer='adam',
    loss='sparse_categorical_crossentropy',
    metrics=['accuracy']
)
6. Model Training

The model is trained for 5 epochs.

model.fit(X_train_flattened, y_train, epochs=5)
7. Model Evaluation

The trained model is evaluated using test data.

loss, accuracy = model.evaluate(X_test_flattened, y_test)
Result
Loss: 0.0816
Accuracy: 97.54%
8. Prediction

The model predicts handwritten digit labels from test images.

Example Prediction:

[np.int64(7), np.int64(2), np.int64(1), np.int64(0), np.int64(4)]

Predicted digits:

7
2
1
0
4

Conclusion

This project successfully demonstrates the implementation of an Artificial Neural Network for handwritten digit recognition using TensorFlow and Keras. The model achieved high accuracy on the MNIST dataset and can accurately classify handwritten digits.
