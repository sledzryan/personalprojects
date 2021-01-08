Abstract:

This project was developed to classify heart disease in patients across multiple locations. Such locations consist of: 
Cleveland, Hungary, Switzerland, and Virginia. This data was imputed using k-nearest neighbors as much of the data
was missing. Given this, the testing accuracy achieved in the model was 86.2%. The model created was an Artifical
Neural Network (ANN/MLP). The creation of such model was done with the help of Neural Networks from Scratch by
Harrison Kinsley and Daniel Kukiela. The model consisted of two hidden (or dense) layers. The first activation
function used was ReLU, and the second was Sigmoid. The loss function chosen was Binary Cross Entropy, and
regularization techniques used were Dropout and L2 (ridge) regularization. Lastly, the optimizer chosen was Adam.

Methods:

First, the data was split into train, test, and validate into ratios of 70/15/15 respectively. We then began
to build the model. Here, there were a total of 13 features and 1 label. Each feature was recommended by the 
authors as the most important for predictions. Also, most of the data in the other features was missing
which would have lead to a much more inaccurate, and difficult model. The label contained values 0-5.
Each value was scaled as 0 = 0 and 1 = 1,2,3,4,5 where 0 was no presence of heart disease and 1,2,3,4,5 
was no presence of heart disease. 

There were two hidden or dense layers in the model. Both contained 340 neurons. 


The layout for the neural network is as follows:

Forward Pass:

Our input layer will be all scaled x values. They will be assigned random weights which will be multiplied by each x.
All x's at every neuron in the first dense (hidden) layer will be summed and have a bias added to them. From there, 
we now have output values from the input layer in the neurons of the first hidden layer. Because we summed different 
weights multiplied by x, and then added them to a bias. Each input in the first hidden layer will contain a different 
value. Here, we will use our first activation function. With the goal of creating the best model for this problem in 
mind, we are going to use ReLU as our first activation function. ReLU will return either 0, if the value produced
is less than or equal to 0, or it will return the value itself if it greater than 0. For the second hidden layer,
we wil use the Sigmoid function. This will allow us to return probabilities in the output layer which will be 
classified as either 0 (output<0.5) or 1 (output => 0.5).

Loss:

For loss, we used binary cross-entropy loss function. This was applied to each layer with 
respect to the predictions, y. We also used L2 or ridge regularization to calculate the loss on both 
hidden layers. This is the loss calculated from our optimizer. The total amount of loss will be the product of 
both types of loss.

Backpropogation:

For backpropogation, we need to apply the chain rule to every layer. For this, we first start with the 
derivative of the BinaryCrossEntropy with respect to the sigmoid activation output. Then, we take the 
derivative of the sigmoid function with respect to the derivative of the inputs of BinaryCrossEntropy. 
Next, we take the derivative of the values of the input of sigmoid function. Then we take the 
derivative of ReLU with respect to the derivative of the inputs of the second hidden layer. We will 
then take the derivative of the values and L2 regularization of weights and biases with respect to
the input of the derivative of ReLU.

Optimizer:
Here we used Adam, an optimizer for which will help adjust the learning rate and gets the momentum of 
the weights and biases which then caches and updates them at each layer.

Dropout:
Dropout with a value of 0.15 was used on the first hidden layer after ReLU was used as the first activation function.

Citations:

Harrison Kinsley & Daniel Kukieła Neural Networks from Scratch (NNFS) https://nnfsio
