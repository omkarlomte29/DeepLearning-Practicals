# DeepLearning-Practicals

# practical 1 :
    Let’s walk through how to implement a Multilayer Perceptron (MLP) to simulate an XOR gate. The XOR gate is a logic gate where the output is true (1) if and only if the two inputs are different. Here's how you can perform this practical step-by-step.

        ### Steps to Implement Multilayer Perceptron for XOR Gate

        #### 1. **Understanding XOR Logic**
        The XOR gate truth table is:
        ```
        Input1   Input2   XOR Output
            0         0          0
            0         1          1
            1         0          1
            1         1          0
        ```

        Here, you will need to train the MLP to learn this behavior.

        #### 2. **Overview of a Multilayer Perceptron (MLP)**
        An MLP consists of:
        - **Input layer**: Takes the two input values (for XOR, these are `0` or `1`).
        - **Hidden layer**: Contains neurons that help the network learn patterns in the data.
        - **Output layer**: Provides the XOR result.

        Typically, the XOR problem is solved using:
        - 2 input neurons (representing the two inputs of the XOR gate),
        - 1 or 2 hidden layers with a few neurons,
        - 1 output neuron (to predict the XOR result).

        #### 3. **Libraries Needed**
        - `numpy` for handling arrays and calculations.
        - `tensorflow` or `keras` for building and training the neural network.

        #### 4. **Python Code for XOR Using MLP**

        //code in practical1.py file

        #### 5. **Explanation of the Code**
        - **Inputs (`X`)**: These are the four possible input combinations for XOR.
        - **Outputs (`y`)**: These are the expected XOR outputs for each input pair.
        - **Model Structure**:
        - The model is built using `Sequential()`, which allows us to add layers one by one.
        - The first hidden layer has 2 neurons and uses the sigmoid activation function.
        - The output layer has 1 neuron, again using the sigmoid activation function because it's a binary classification problem.
        - **Optimizer**: We use Stochastic Gradient Descent (`SGD`) with a learning rate of `0.1`.
        - **Loss Function**: `binary_crossentropy` is used as this is a binary classification problem.
        - **Training**: The model is trained for 10,000 epochs to learn the XOR pattern.
        - **Testing**: After training, we test the model on the XOR inputs to check if it gives correct outputs.
        - **Evaluation**: The model's accuracy is computed on the XOR dataset.

        #### 6. **Practical Execution in Your Exam**
        1. **Setup**: Open a Python environment (like Jupyter Notebook, Google Colab, or any Python IDE) that has TensorFlow installed.
        2. **Copy-Paste the Code**: Paste the code provided above.
        3. **Run the Code**: Run each cell or the script.
        4. **Observe the Output**: The output should show the predicted XOR results (0 or 1), along with the model's accuracy.
        5. **Explain the Model**: During the viva, explain how the MLP works for binary classification problems like XOR.

        #### 7. **Understanding Results**
        The model will output the predicted XOR result for each input pair (like `[0,0]`, `[0,1]`, etc.). The expected outputs are:
        - For `[0,0]` → `0`
        - For `[0,1]` → `1`
        - For `[1,0]` → `1`
        - For `[1,1]` → `0`

        After sufficient training, the predictions should closely match these values.

        ### Best of Luck!
        This should help you perform the practical successfully during your exam. Let me know if you need any further clarifications!

# practical 3 :
        Let’s go step-by-step on how to design and implement a fully connected deep neural network (DNN) for a classification task, which includes using the Adam optimizer, softmax activation for the output, and the cross-entropy loss function. This guide will provide you with everything you need to perform the practical.

        ### Steps to Implement a Fully Connected Deep Neural Network for Classification

        #### 1. **Problem Overview**
        A DNN is a type of neural network with multiple layers between the input and output layers. In this case, we'll create a DNN with at least 2 hidden layers to classify data into multiple categories (multi-class classification). 

        #### 2. **Dataset**
        For this example, let’s use the classic **MNIST dataset** (handwritten digit classification). MNIST is a well-known dataset for digit classification (0-9), making it a 10-class classification problem.

        #### 3. **Components of the Model**
        - **Input Layer**: The input will be a flattened version of the MNIST images (28x28 pixels).
        - **Hidden Layers**: At least two fully connected (Dense) layers.
        - **Output Layer**: A softmax layer with 10 neurons (since we are classifying digits 0-9).
        - **Optimizer**: Adam optimizer for better performance.
        - **Loss Function**: Categorical Cross-Entropy for multi-class classification.
        - **Activation Functions**: ReLU for the hidden layers and softmax for the output.

        #### 4. **Python Code for a DNN**

        Here is the complete implementation using TensorFlow/Keras for classification:

        //code available in practical3.py

        #### 5. **Explanation of the Code**
        - **Data Loading (`mnist.load_data()`)**: We use the MNIST dataset, which is split into a training set (60,000 images) and a test set (10,000 images).
        - **Data Normalization**: The pixel values of the images are normalized to a range between 0 and 1 for better performance.
        - **One-Hot Encoding**: Since this is a multi-class classification problem, the labels (digits 0-9) are one-hot encoded (i.e., converted into a vector where only the correct class index is 1, and all other values are 0).
        - **Model Structure**:
        - The **Flatten** layer reshapes the 28x28 pixel image into a 1D vector of 784 values.
        - We add two hidden layers:
            - First hidden layer with 128 neurons and ReLU activation.
            - Second hidden layer with 64 neurons and ReLU activation.
        - The output layer has 10 neurons (one for each digit class) with softmax activation to perform multi-class classification.
        - **Model Compilation**:
        - The model uses the **Adam** optimizer, which is a common choice for DNNs.
        - The **categorical cross-entropy** loss function is appropriate for multi-class classification tasks.
        - **Model Training**: The model is trained for 10 epochs with a batch size of 32.
        - **Model Evaluation**: After training, we evaluate the model on the test dataset to check its accuracy.
        - **Predictions**: The model makes predictions on new data (in this case, the first 5 images from the test set).

        #### 6. **Practical Execution in Your Exam**
        1. **Setup**: Open a Python environment with TensorFlow/Keras installed (Jupyter Notebook, Google Colab, etc.).
        2. **Copy-Paste the Code**: Paste the provided code into your environment.
        3. **Run the Code**: Execute the code step by step or as a script.
        4. **Observe the Output**: The output will show the model's accuracy on the test data, and optionally, the predictions for some test images.
        5. **Explain the Model**: Be ready to explain the different components of the DNN, such as the role of the hidden layers, optimizer, loss function, and activation functions.

        #### 7. **Understanding the Results**
        The output will show the test accuracy. For example:
        ```
        Test accuracy: 97.45%
        ```

        You will also see the model’s predictions on the first 5 test images compared to the true labels, like:
        ```
        Predicted: 7, True label: 7
        Predicted: 2, True label: 2
        ...
        ```

        ### Key Points to Discuss During the Practical Exam:
        - **Adam Optimizer**: Explain that Adam adjusts the learning rate dynamically, making it an efficient and widely used optimizer.
        - **Softmax Activation**: Used in the output layer for multi-class classification, it converts the outputs into probabilities that sum to 1.
        - **Cross-Entropy Loss**: Measures the difference between the predicted probabilities and the true labels in multi-class classification.

        ### Best of Luck!
        This code and explanation will help you perform well in your practical. Let me know if you need any more clarifications or help.

# practical 4 :
        Here’s how you can implement a backpropagation algorithm to train a Deep Neural Network (DNN) with at least two hidden layers. Backpropagation is the algorithm used to adjust the weights of the network by calculating the gradient of the loss function, enabling the network to learn.

        ### Steps to Implement a DNN with Backpropagation

        #### 1. **Understanding Backpropagation**
        Backpropagation involves:
        - **Forward Propagation**: Compute the output for each layer.
        - **Loss Calculation**: Compare the predicted output with the actual output using a loss function (e.g., mean squared error or cross-entropy).
        - **Backward Propagation**: Calculate the gradient of the loss concerning each weight in the network and adjust the weights accordingly using a learning rate.

        #### 2. **Structure of the DNN**
        - **Input Layer**: Takes input data (for this example, we’ll use a simple dataset).
        - **Hidden Layers**: Two hidden layers with activation functions (ReLU).
        - **Output Layer**: Provides the predicted output.
        - **Optimizer**: Gradient descent will be used for weight updates.
        - **Loss Function**: Mean squared error (for simplicity).

        #### 3. **Python Code for Backpropagation in DNN**

        Here is the complete code for implementing backpropagation from scratch:

        // code in practical 4.py

        #### 4. **Explanation of the Code**
        - **Input Data (`X`)**: We use the XOR dataset for simplicity.
        - **Weights and Biases Initialization**: Random values are assigned to weights and biases, which will be updated during training.
        - **Forward Propagation**:
        - We first compute the inputs and outputs for each layer using matrix multiplication and activation functions.
        - Sigmoid is used as the activation function for simplicity, but you can use ReLU for hidden layers if desired.
        - **Loss Calculation**: The error is calculated using mean squared error.
        - **Backward Propagation**:
        - Gradients are calculated for each layer, starting from the output and moving backward, using the chain rule.
        - We update the weights and biases using these gradients and the learning rate.
        - **Training Loop**: The network is trained over multiple epochs (10,000 iterations), adjusting the weights to minimize the loss.

        #### 5. **Understanding the Results**
        After training, the network will output values close to the expected XOR outputs:
        - For inputs `[0, 0]`, `[0, 1]`, `[1, 0]`, and `[1, 1]`, the network should output values close to `[0]`, `[1]`, `[1]`, and `[0]` respectively.
        
        The loss decreases over time, indicating that the network is learning the correct patterns.

        ### Key Points to Explain During the Practical Exam:
        - **Backpropagation**: Explain that this algorithm calculates the gradient of the loss function and adjusts the weights to minimize the error.
        - **Learning Rate**: This controls how large the weight updates are during training.
        - **Activation Function**: Sigmoid is used to introduce non-linearity, allowing the network to learn complex patterns.
        - **Gradient Descent**: This is used to minimize the loss by adjusting the weights.
        
        ### Practical Execution in Your Exam:
        1. **Setup**: Use a Python environment that supports NumPy (like Jupyter Notebook or any Python IDE).
        2. **Copy-Paste the Code**: Paste the provided code.
        3. **Run the Code**: Execute it step by step or as a script.
        4. **Observe the Output**: See the final predictions and the loss during training.

        ### Best of Luck!
        This guide should help you implement backpropagation for your DNN practical. Let me know if you need any further assistance!

# practical 5 :
        Here's how you can implement an Autoencoder model for image compression or denoising, step by step.

        ### Introduction to Autoencoders:
        An autoencoder is a type of neural network used to learn efficient codings of input data, typically for dimensionality reduction (compression) or denoising. It has two parts:
        1. **Encoder**: Compresses the input into a latent space representation.
        2. **Decoder**: Reconstructs the input from the latent representation.

        ### Use Case 1: Image Compression
        - **Objective**: Reduce the dimensionality of the image and then reconstruct it, achieving compression.
        
        ### Use Case 2: Image Denoising
        - **Objective**: Remove noise from images, such as blurring or distortions, by training the autoencoder to reconstruct clean images.

        ---

        ### Steps to Implement an Autoencoder for Image Compression / Denoising

        #### 1. **Setting Up the Environment**
        Make sure you have Python, TensorFlow, and Keras installed. You can install TensorFlow using the command:

        ```bash
        pip install tensorflow
        ```

        #### 2. **Understanding the Architecture**
        - **Input**: Image (e.g., 28x28 grayscale or color images like MNIST or CIFAR-10).
        - **Encoder**: Compresses the image.
        - **Latent Space**: Bottleneck where information is stored in a compressed form.
        - **Decoder**: Reconstructs the image back to the original size.

        #### 3. **Building the Autoencoder Model Using Keras**

        The following example uses the **MNIST dataset** (28x28 grayscale images) for simplicity. You can easily adapt it for other datasets like CIFAR-10.
    
        //code in practical5.py

        #### 4. **Explanation of the Code**
        - **Dataset**: We are using MNIST, but you can switch to any other dataset. For image compression, you don’t need to add noise. For denoising, we add noise using a normal distribution.
        - **Model Architecture**:
        - **Encoder**: Two convolutional layers followed by max-pooling layers to compress the image.
        - **Decoder**: Two convolutional layers followed by up-sampling to reconstruct the image.
        - The model compresses the input to a smaller representation and then reconstructs it.
        
        - **Loss Function**: We use `binary_crossentropy`, which works well for image data that’s normalized between 0 and 1.
        - **Optimizer**: `Adam` optimizer is used for faster convergence.

        #### 5. **Training the Autoencoder**
        The model is trained for 50 epochs. The `X_train_noisy` dataset is used for training if denoising is the goal, and the clean dataset (`X_train`) is used for regular compression.

        #### 6. **Denoising the Images**
        After training, we pass noisy test images (`X_test_noisy`) through the autoencoder, and it reconstructs denoised versions of the images (`decoded_imgs`).

        #### 7. **Visualizing the Results**
        The output of the model is visualized in three rows:
        - **Original Images**: Clean MNIST digits.
        - **Noisy Images**: Corrupted versions with added Gaussian noise.
        - **Denoised Images**: Reconstructed images generated by the autoencoder.

        ---

        ### Key Points to Explain During the Practical Exam:
        - **Autoencoder**: A type of neural network that is trained to map input data to itself, used for tasks like compression or denoising.
        - **Architecture**: The model consists of an encoder and a decoder.
        - The encoder compresses the input into a lower-dimensional space (latent space).
        - The decoder reconstructs the original input from this compressed representation.
        - **Loss Function**: We use binary cross-entropy for image reconstruction.
        - **Optimizer**: Adam optimizer is used to adjust weights efficiently during training.

        ---

        ### How to Execute the Practical in Your Exam:
        1. **Setup**: Ensure TensorFlow is installed.
        2. **Copy-Paste the Code**: Paste the code in a Python file or Jupyter Notebook.
        3. **Run the Code**: Train the model, and then observe the results using matplotlib for visualization.
        4. **Show the Output**: You’ll need to show the comparison between original, noisy, and denoised images.

        ---

        ### Best of Luck!
        This step-by-step guide should help you understand and implement the Autoencoder for your practical exam. Let me know if you need any more clarifications!

# practical 6 :
        Here’s a guide on how to design and implement a CNN model for a **digit recognition application** using the MNIST dataset. This step-by-step explanation assumes you have no prior knowledge, making it easy to follow for your practical exam.

        ### What is a Convolutional Neural Network (CNN)?

        CNNs are a type of neural network that work exceptionally well for image data. They consist of convolutional layers, pooling layers, and fully connected layers.

        - **Convolutional layers** extract features from the input images (edges, shapes, etc.).
        - **Pooling layers** reduce the spatial dimensions, lowering computation and focusing on important features.
        - **Fully connected layers** classify the images based on the features extracted by the convolutional layers.

        ### Steps to Implement a CNN for Digit Recognition

        #### 1. **Setting Up the Environment**

        Ensure you have Python and TensorFlow installed. Use the following command to install TensorFlow if not already installed:

        ```bash
        pip install tensorflow
        ```

        #### 2. **Dataset: MNIST**

        The **MNIST dataset** consists of 28x28 pixel grayscale images of handwritten digits (0–9). The goal is to classify these digits using a CNN model.

        #### 3. **Building the CNN Model Using Keras**

        //code in prac6.py

        #### 4. **Explanation of the Code**

        - **Data Preparation**:
        - The dataset is loaded using `tf.keras.datasets.mnist`.
        - The pixel values are normalized between 0 and 1 to improve training performance.
        - Labels are one-hot encoded to work with multi-class classification.

        - **Model Architecture**:
        - **Convolutional Layers**: These layers use filters (kernels) to detect patterns like edges, curves, and shapes in the images. The number of filters increases deeper into the network to learn more complex patterns.
        - **MaxPooling Layers**: These layers reduce the dimensionality of the feature maps, retaining important features while reducing the computational cost.
        - **Flatten Layer**: Converts the 2D feature maps into 1D vectors to feed into fully connected layers.
        - **Dense Layers**: These are fully connected layers. The final dense layer has 10 units (for the 10 digit classes) and uses a softmax activation function, which outputs the probabilities for each class.
        
        - **Model Compilation**:
        - The model is compiled with the `Adam` optimizer, which adjusts the weights efficiently.
        - `Categorical cross-entropy` is used as the loss function, which is ideal for multi-class classification.
        
        - **Training**:
        - The model is trained on the MNIST training set for 5 epochs. The `batch_size` determines how many samples are processed before updating the model weights.
        
        - **Evaluation**:
        - The model is evaluated on the test data, and accuracy is printed.

        - **Visualization**:
        - The first 10 images from the test set are visualized along with their predicted labels.

        #### 5. **What to Explain During the Practical Exam**

        - **Convolutional Neural Networks (CNNs)**: Explain the role of convolutional layers in feature extraction and pooling layers for dimensionality reduction.
        - **Model Layers**: Describe how the three convolutional layers extract features, and the fully connected layer makes the final classification.
        - **Activation Functions**: Explain why `ReLU` is used in hidden layers and `Softmax` in the output layer.
        - **Loss Function and Optimizer**: Categorical cross-entropy is suitable for multi-class classification, and Adam optimizer is chosen for faster convergence.
        - **Model Training**: Explain the importance of training and validation data for evaluating model performance.

        #### 6. **How to Execute This in Your Exam**
        1. **Set Up**: Make sure TensorFlow is installed.
        2. **Write the Code**: You can use a Jupyter Notebook or Python file to write and execute the code.
        3. **Train the Model**: Train the model on the MNIST dataset provided in the code.
        4. **Show the Output**: Once the model is trained, show the test accuracy and some sample predictions.
        5. **Answer Questions**: Be prepared to explain the architecture and how each component works.

        ---

        ### Best of Luck for Your Practical Exam!

        You now have a complete guide to implementing a CNN for digit recognition using the MNIST dataset. Let me know if you need further clarifications!