this repo was created using git clone https://github.com/mnielsen/neural-networks-and-deep-learning.git from Michael Nielsen's Neural Networks and Deep Learning ebook. 
This repo is intended to be used for learning purposes and any subsequent changes pushed will be for learning.


We start with the first understanding the data we'll be using to run this program. The data comes from MNIST (Modified National Institute of Standards and Technology Databse) and it is a large database of handwritten digits that are commonly used for training various image processing systems, such as this program. The reason this is important is because handwritten digits have variance to them depending on various factors such as: writing style, differences in how a number is written (i.e. a dash through the middle of a 7 or connecting the top of a 4 or not), and legibility. These can make numbers differ on paper, however our brain and eventually our program will be able to recognize what each number is.

The data set is 60,000 images, which we'll split into two parts. The first set is 50,000 images used to train the network and the second set is 10,000 images that will be used for validation. Last step is to make sure you have the Python library "Numpy" for the linear algebra parts.

The main part of the code starts with the "Network" class, which is how a neural network is represented. See "network.py line 19 for where the class is initialized. This Network class uses the list "sizes" to determine number of neurons in the respective layers. 

Weights and biases of the "Network" object are initialized randomly using the Numpy random.randn function to generate Gaussian distributions (Gaussian distribution refers to the probability distribution that is symmetric about the mean, aka the data closer to the mean the more frequent it happens. Think of a bell curve) with mean 0 and standard deviation 1. Note that weights and biases are stored as lists of Numpy matrices, so net.weights[1] stores the weights connecting the second and third layers since Python indexing starts at 1.

We define the sigmoid function at the bottom of the "network.py" file to reference. (The sigmoid function transforms the continuous real number into a range of ( 0 , 1 ) , so that the input value of the next layer is within a fixed range and the weight is more stable.) After that we create a feedforward method which acts as the input for the network. This is initialized by if "a" is input. 


