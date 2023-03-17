# myfirstNN
This is a very simple example of neural network. Its purpose is to approximate an unknown single valued function using a dense deep network.

"myhiddenfunction" is the definition of the function you want to approximate by means of a neural network (NN). The definition is hidden to the NN, who can only access it as a blackbox, to get training samples. This is implemented by means of a generator (a special kind of function), taking in input a number (batchsize) and returning a pair of input output vectors of length batchsize. Each input is a random number in the interval [-pi,pi] and the output is computed by means of myhiddenfunction.

If you want to see an example of a generated batch, you need to invoke next on the generator

Now we define the network. The function we want to approximate is single valued, so the network will have a single input and a single output, and its (dense) structure is completely defined by a list specifying the number of neurons per layer

We are finally ready to compile our model and train it. As loss function we use mean square error (mse). The "optimizer" is the technique used to tune the learning rate during backpropagation: you may ignore it for the moment.

If everything is working correctly, the loss should decrease during training.
If it doesn't, it means that, for some reason, the network is not learning.

We are finally ready to check the result of the approximation. We plot the hidden function in red, and the approximation computed by the network in blu.

