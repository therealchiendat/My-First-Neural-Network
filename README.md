# My First Neural Network
MATLAB® was used to develop the neural network with the specification in the introduction section. <b>None</b> of the functions from MATLAB’s Deep Learning Toolbox was used during the process of developing this Neural Network.

This network uses Epochwise Backpropagation method to train the system, which only updates the weight values after every pattern of the training set has been gone through. There are three stopping criteria: The Average Sum of Squared Errors (ASSE) reaches a relatively low value, the training time limit reaches, and if the network starts to be overfitting. The training process stops when any of the criteria is met. 
At the beginning of the training process, a set of random values was generated to be used as initial weights. These random values are uniformly distributed between a value of weight limit, which will be discussed in the next part of the report.  

As each loop of the training set be gone through, the value of ASSE, which is denoted by ξ_TR (W)

The learning factor (μ) is the rate that determines how quickly the network abandon the old belief for new ones. 
Within the scope of this question, the belief refers to the choice the network makes when get presented a pair of two inputs. The learning factor is the trade off between training speed and convergence error. A large learning rate can help the network quickly realizes the features of the training set. However, a large training set also means that the network may abandoned many of the previous training data and for new features (That may not be correct) that the network realized when get presented a new training pattern. 
Generally, a good learning factor is a factor that is low enough that the network converges to a meaningful result, which is correctly identify most of different pair of inputs. However, it should be high enough so that the network only need to take a relatively short amount of time before reaching a meaningful result.
To be able to find the best learning factor, the developed script was modified to be able to try different values of μ (different in order of magnitude) for both case when the number of first-layer units are 3 and 30. The training time (The total number of epoch) will be set to a constant value of 10,000 so that the values can be easily compared. 
When the training is completed for all the values of μ, the plots of the ASSE values will be examined to get the most suitable value of μ. Since the neural network in the scope of this assignment is a relatively simple (small) neural network, only the plots that produce smooth results will be considered. Furthermore, at the end of 10,000 training cycles, the plots fail to deliver the final value ASSE less than 1 will be rejected. The plots eligible for consideration will then be examined and the μ that associates with the fastest convergence plot will be selected as optimal. 
With the optimal value of μ selected, the same process as above will be used to find the optimal value of initial weight limits. 
To be able to easily keep track of the result, the chosen value for the learning factor and initial weight limit will be similar in both case of 3 first-layer units and 30 first-layer units.

There are two inputs to the constructed neural networks, which forms in a two-dimensional input space. The dimensionality of the input space is low enough that it can be shown as a 2D map. The output of the neural network can be shown as different labels. For this assignment, the first feature will be labelled as the symbol ‘o’, the second feature will be labelled as the symbol ‘x’, and the third one will be labelled as the symbol ‘□’. The colour of these symbols will be labeled as blue if the input symbol is recognized correctly by the neural network and they will be coloured as red otherwise. 
The map will be constructed via MATLAB. Although there were attempts to construct the map using the “image” command, it is believed that the surf command is a more efficient method to construct an equivalent map. 
The input patterns in the input space, it rounded to 4 significant digits, the resolution of the maps is expected to be correct up to 〖10〗^(-4) value of x 
Using the optimal value of μ and weight limit factor found earlier to train the network. Both the case of 3 first-layer units and 30 first-layer units will be trained. The network will be trained until the network ASSE curve of the validation set starts to go up while the ASSE curve of the training set continue to decrease (the network starts to be overfitting to the training set) or reach the training time limit, which is set to be 10,000 epochs.

The network uses the cross-validation between the training set and the validation set to recognise when the network starts to be over-trained. The cross-validation method between two sets is a good method to find good stopping criteria. The goal for training the neural network is to get the network correctly identify the feature with a random two-dimensional input space. Having the network trained more on the training set will help the neural network more correctly identify the correct feature for each input from this set. However, the training set only has a limited number of patterns (in this question case is 120 patterns), and there can be outliner data. When the network is trained to correctly identify most of the patterns in the training set, including the outliner, the network may incorrectly identify many other patterns in the input space. The cross-validation of both the training set and the validation set will help the network to recognise the epoch at which the network be overfitted to the training set and causes the error rate of the validation set starts to increase.
During the training period, the script developed will store the weight values, error rate, ASSE value at every epoch as different arrays of variable where these variables will then be stored locally as a data file on the computer. The weight values of a particular epoch can be easily retrieved by retrieving that particular element in the weight value arrays.

To be able to further example the neural network structure, the original developed script for the neural network is modified to be able to train the network over 10 trials with the weights be randomized between each trial. The average sum of network outputs (avgSNO) and the standard deviation of the sum of network outputs (stdSNO) will also be calculated. At the end of the trials, a table includes the values of the epochs the training process stopped, the ASSE value, the Classification Error Rate (CER), the value of avgSNO, stdSNO with respect to all three of the data sets.
