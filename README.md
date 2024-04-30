# DEEP LEARNING CHALLENGE
## Overview
The goal of this exercise is to attempt to create a model that can predict whether or not a venture will succeed given a number of input features about the venture. The input features are various properties about the organization behind the venture, including the type of application they submitted, the type of organization, and whether or not the venture succeeded, among others. Using deep learning, we will create a neural network capable of predicting a venture's success within reasonable accuracy expectations. 

## Results
- Data Preprocessing
    - The target variable is whether or not the venture succeeded, named "IS_SUCCESSFUL".
    - The features were derived from all other columns; we removed four columns that were either useless for such analysis or were not useful for the model. We also used the "get_dummies()" method to expand some columns.
    - The four columns removed were: "EIN" and "NAME" that were irrelevant to success entirely; "STATUS" and "SPECIAL_CONSIDERATIONS" that were overwhelmingly of one value.
- Model Creation
    - I chose an initial set of neuron parameters arbitrarily based off of the starter code. I started with 60/30 neurons in the first/second layers respectively. My hidden layers used ReLU and my output layer used the sigmoid activation function.
    - I attempted to refine each of these parameters. I cut down neuron count to 20/10 based on [this advice](https://medium.com/geekculture/introduction-to-neural-network-2f8b8221fbd3). I added and removed hidden layers. These attempts failed to improve performance.
    - I changed my activation functions via testing. This improved performance very slightly. I researched applications of different activation functions and found that softmax is typically used in the final hidden layer. The changes on the first hidden and output layers had little effect on accuracy.
    - I was unable to achieve the 75% accuracy performance benchmark.
    - To try and come closer, I revised our preprocessing. I expanded the number of bins for "APPLICATION TYPE" and "CLASSIFICATION" columns and binned "INCOME_AMT" as well. I increased the number of epochs for training. I removed the "STATUS" and "SPECIAL_CONSIDERATIONS" because too much of the dataset was of a single value for these columns. Finally, I took the steps to modify the layers of the model described above.