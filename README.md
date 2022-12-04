# HUMAN ACTIVITY RECOGNITION
# 19BCI7017
# DATASET
DATA SET LINK IS [UCF50](https://www.crcv.ucf.edu/data/UCF50.rar).
has its own limitations.

# Approach  Using 3D CNN’s (aka. Slow Fusion)

Another option is to use a 3D Convolutional Network, where the temporal and spatial information are merged slowly throughout the whole network that is why it’s called Slow Fusion. But a disadvantage of this approach is that it is computationally really expensive so it is pretty slow.

# Approach : Using Pose Detection and LSTM

Another method is to use a pose detection network on the video to get the landmark coordinates of the person for each frame in the video. And then feed the landmarks to an LSTM Network to predict the activity of the person. 

There are already a lot of efficient pose detectors out there that can be used for this approach. But a disadvantage of using this approach is that you discard all the information other than the landmarks, like the environment information can be very useful, for example for playing football action category the stadium and uniform info can help the model a lot in predicting the action accurately.

Before going to the approach that we will implement in this tutorial, let’s briefly discuss what are Long Short Term Memory (LSTM) networks, as we will be using them in the approach.

Long Short Term Memory (LSTM) 
An LSTM network is specifically designed to work with a data sequence as it takes into consideration all of the previous inputs while generating an output. LSTMs are actually a type of neural network called Recurrent Neural Network, but RNNs are not known to be effective for dealing with the Long term dependencies in the input sequence because of a problem called the Vanishing gradient problem.

LSTMs were developed to overcome the vanishing gradient and so an LSTM cell can remember context for long input sequences.


Many-to-one LSTM network
This makes an LSTM more capable of solving problems involving sequential data such as time series prediction, speech recognition, language translation, or music composition. But for now, we will only explore the role of LSTMs in developing better action recognition models.

Now let’s move on towards the approach we will implement in this tutorial to build an Action Recognizer. We will use a Convolution Neural Network (CNN) + Long Short Term Memory (LSTM) Network to perform Action Recognition while utilizing the Spatial-temporal aspect of the videos.

# Approach : CNN + LSTM
We will be using a CNN to extract spatial features at a given time step in the input sequence (video) and then an LSTM to identify temporal relations between frames.


The two architectures that we will be using.

