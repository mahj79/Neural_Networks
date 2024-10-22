Welcome to today's session on A.I. and Machine Learning Fundamentals: Neural Networks!

Before we go deep into today's session, let's first cover some of the basic definitions of terms you'll hear frequently used today.

- A.I. or Artifical Intelligence, Britannica Definition: The ability of a digital computer or computer-controlled robot to perform tasks commonly associated with intelligent beings. The term is frequently applied to the project of developing systems endowed with the intellectual processes characteristic of humans, such as the ability to reason, discover meaning, generalize, or learn from past experience. 

- ML or Machine Learning, MIT Sloan Definition: Machine learning is a subfield of artificial intelligence, which is broadly defined as the capability of a machine to imitate intelligent human behavior. Artificial intelligence systems are used to perform complex tasks in a way that is similar to how humans solve problems.

- Neural Networks, IBM Definition: A neural network is a machine learning program, or model, that makes decisions in a manner similar to the human brain, by using processes that mimic the way biological neurons work together to identify phenomena, weigh options and arrive at conclusions.

![Neural Networks Diagram](https://github.com/mahj79/Neural_Networks/blob/main/Neural_Networks/Learning_Section/Neural_Network_Drawing.jpg?raw=true)

**What is the difference between A.I. and Machine Learning?** According to Google, artificial intelligence encompasses the idea of a machine that can mimic human intelligence, machine learning does not. Machine learning aims to teach a machine how to perform a specific task and provide accurate results by identifying patterns. 

TLDR (Too Long Don't Read) - AI can do a lot of stuff. Machine Learning is focused on a specific task.


To help with our lesson today, we'll use the most common image recognition and learning method used in machine learning and that is recognizing numbers from hand drawn images maintained by the mnist database. Our good friends NIST (National Institute of Standards and Technology) have compiled thousands of handwritten images of numbers.

![MNIST Numbers Dataset](https://github.com/mahj79/Neural_Networks/blob/main/Neural_Networks/Learning_Section/mnist_numbers.png?raw=true)

Think about each number can be written uniquely. Some people will put dashes on their 7s, connect the tops of their 4s, or put curves on the top of their 1s.

![MNIST Numbers Extended](https://github.com/mahj79/Neural_Networks/blob/main/Neural_Networks/Learning_Section/mnist_extended_zoomed.png)

How we go about solving the problem of appropriately identifying a number, we can think of a neural network as a system of filters that continues to filter information based on educated assessments of a certain piece of information until ultimately arriving at an answer. These filters are the layers we referred to earlier. 

Let's take a look at a speicific example, a handdrawn image of the number 8.

![MNIST Number Eight](https://github.com/mahj79/Neural_Networks/blob/main/Neural_Networks/Learning_Section/mnist_image_number_eight.jpg)

 Think about how over time you would get really good at correctly identifying issuse if you did this thousands of times! To help our program learn over time and become more accurate at correctly identifying a number, we use weights and biases to help fine tune our program over time. Below is an example of how we can put more emphasis on information passed along from layer to next by adding more weight to a specific feature our layer is looking for. 

![MNIST Neural Network Weights Red](https://github.com/mahj79/Neural_Networks/blob/main/Neural_Networks/Learning_Section/Neural_Network_Drawing_Red_Weights.jpg)

Below is a different example with different neurons lit up. Think of this as our neurons communicating to the next layer as "yup, we got a loop over here" or "no loops identified here".

![MNIST Neural Network Weights Blue](https://github.com/mahj79/Neural_Networks/blob/main/Neural_Networks/Learning_Section/Neural_Network_Drawing_Blue_Weights.jpg)

Weights and biases are similar in that we are essentially telling the program what it should be caring about. So, what is a bias? A bias is how we leverage the neurons in a layer to say what or what not to look for. The bias helps us get closer to that 1 or 0 that tells our layers this is what we should be caring about. From a mathematical perspective it acts sort of like a negative effect. Take a look at our number 8 example again and how bias is applied.

![MNIST Number Eight with Bias](https://github.com/mahj79/Neural_Networks/blob/main/Neural_Networks/Learning_Section/number_eight_bias.JPG)

The bias plays a critical part in training our neural network / machine learning program as this is what we can continuously fine-tune to make predictions more accurate. The closer a bias has to 1, the more likely it is that that neuron is identifying the correct thing it has been told to look for. The further away from 1 or you can think of as closer to 0, the program is identifying something that is not what it is supposed to be looking for. 

Ok so we've covered a lot of conceptual knowledge.... Demo time with Code! Note this code was cloned from the git repo neural networks from Michael Nielsen's Neural Networks and Deep Learning ebook. Highly recommend taking a look after this!


So what did we learn? That's right everything is a neural network.

![Neural Network meme](https://github.com/mahj79/Neural_Networks/blob/main/Neural_Networks/Learning_Section/neural_network_meme.jpg)

For comedic relief after going through all that, note this is how my fiancee looks at me when I try to explain this sort of stuff to her.

![Always Sunny Crazy Meme](https://github.com/mahj79/Neural_Networks/blob/main/Neural_Networks/Learning_Section/always_sunny_meme.jpg)

Some things to consider are what we if we had a different problem than just solving which number of an image is. Some hypothetical examples could be solving a puzzle, figuring out if an image is a face, or if an image is a car? Think about what would be needed from a layers and corresponding neurons from there and then consider building your own model using what you learned here! Remember though for whatever you decide to do, you'll need a lot of training data!

Other considerations that should be thought about are what potential risks can come from machine learning and AI leveraging neural networks? What if training data is inaccurate or wrong? What if accuracy isn't at a high enough threshold and outputs wrong answers to the consumers / end users? What controls can be implemented to help mitigate some of the risks associated with these learning models?
