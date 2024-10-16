this repo was created using git clone https://github.com/mnielsen/neural-networks-and-deep-learning.git from Michael Nielsen's Neural Networks and Deep Learning ebook. 
This repo is intended to be used for learning purposes and any subsequent changes pushed will be for learning.


We start with the first understanding the data we'll be using to run this program. The data comes from MNIST (Modified National Institute of Standards and Technology Databse) and it is a large database of handwritten digits that are commonly used for training various image processing systems, such as this program. The reason this is important is because handwritten digits have variance to them depending on various factors such as: writing style, differences in how a number is written (i.e. a dash through the middle of a 7 or connecting the top of a 4 or not), and legibility. These can make numbers differ on paper, however our brain and eventually our program will be able to recognize what each number is.

The data set is 60,000 images, which we'll split into two parts. The first set is 50,000 images used to train the network and the second set is 10,000 images that will be used for validation. Last step is to make sure you have the Python library "Numpy" for the linear algebra parts.

The main part of the code starts with the "Network" class, which is how a neural network is represented. See "network.py line 19 for where the class is initialized. This Network class uses the list "sizes" to determine number of neurons in the respective layers. 

Weights and biases of the "Network" object are initialized randomly using the Numpy random.randn function to generate Gaussian distributions (Gaussian distribution refers to the probability distribution that is symmetric about the mean, aka the data closer to the mean the more frequent it happens. Think of a bell curve) with mean 0 and standard deviation 1. Note that weights and biases are stored as lists of Numpy matrices, so net.weights[1] stores the weights connecting the second and third layers since Python indexing starts at 1.

We define the sigmoid function at the bottom of the "network.py" file to reference. (The sigmoid function transforms the continuous real number into a range of ( 0 , 1 ) , so that the input value of the next layer is within a fixed range and the weight is more stable.) After that we create a feedforward method which acts as the input for the network. This is initialized by if "a" is input. 

Once we have the key parts in place, we create our first method of stochastic gradient descent. (LEAVE SECTION BLANK HERE TO REFER BACK TO EXPLANATION ALREADY PREPARED) Refer to the code in "network.py" line 44 for the implementation of SGD. We use variables epochs (An epoch is when all the training data is used at once and is defined as the total number of iterations of all the training data in one cycle for training the machine learning model. Another way to define an epoch is the number of passes a training dataset takes around an algorithm) and mini_batch_size, to set the number of epochs to train for and the size of the mini-batches to use when sampling. eta is the learning rate.

How the code executes, each epoch starts by randomly suffling the training data and then breaks it into mini-batches of appropriate size. For each mini_batch we then apply a single step of gradient descent. The "self.update_mini_batch(mini_batch, eta) updates the network weights and biases according to a single iteratino of gradient descent using only the training data in mini_batch. 

Finally in the update_mini_batch method, backpropagation is used to calculate the cost of gradient descent and inform our program how to best optimize based on the resuls. Backpropagation is invoked on line 69 by the line "delta_nabla_b, delta_nabla_w = self.backprop(x, y)" which ultimately updates the weights and biases.

Now you're finally ready to start the program! First you'll want to run the following commands: "import mnist_loader" and then "training_data, validation_data, test_data = mnist_loader.load_data_wrapper()" this is to get the mnist data working. From there you'll set up the Network! Run "import network" and then "net = network.Network([784, 30, 10])" what this does is import the Python program and then set up the neurons. 784 refers to the pixels from a single MNIST image. In each image we have 28 pixels by 28 pixels. So the total is 784 pixels in a single MNIST image, with 30 hidden neurons, and then 10 possible outcomes 0 through 9. Last step will be to use the stochastic gradient descent to have our program learn from the MIST training data over 30 epochs, with a mini-batch size of 10 and a learning rate of n = 3.0. Run the command "net.SGD(training_data, 30, 10, 3.0, test_data=test_data)" this will kick off the program and run the code to return our program. 

Ways to speed up the program could be to reduce the number of epochs, number of hidden neurons, or training data. This may not produce as accurate of a result, however that is the point of machine learning, to continuously train on data to improve performance. It is noted that this can be made to highly performant for production environments. 

By doing a few tests of increasing the number of hidden neurons to say 100, we should see improved accuracy. "net = network.Network([784, 100, 10])" and "net.SGD(training_data, 30, 10, 3.0, test_data=test_data)" check the results. 

Now if we took a different approach and wanted to see how changes can decrease performance, we can change the learning rate to n = 0.001. Run "net = network.Network([784, 100, 10])" and then "net.SGD(training_data, 30, 10, 0.001, test_data= test_data)" and check the results. We should see a significant decrease in performance. 

You can play around with the number of neurons and learning rate to find the optimal accuracy, however it can be tricky at first.

This is where we wrap up our demo for today. Some things to consider are what we if we had a different problem than just solving which number of an image is. Some hypothetical examples could be solving a puzzle, figuring out if an image is a face, or if an image is a car? Think about what would be needed from a layers and corresponding neurons from there and then consider building your own model using what you learned here! Remember though for whatever you decide to do, you'll need a lot of training data!