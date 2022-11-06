# Driver-Drowisness-Detection
This system is used in detecting the drowsiness level in drivers while driving. 
PROPOSED METHODOLOGY 

Detection Stage: 

 This is the initialization stage of the system. Every time the system is started it needs to be set up and optimized for current user and conditions. The key step in this stage is successful head detection. If the driver’s head is correctly located we can proceed to extract the features necessary for setting up the system. Setup steps include: (i) extracting driver’s skin color and using that information to create custom skin color model and (ii) collecting a set of open/closed eyes samples, along with driver’s normal head position.  

To help achieve these goals, user interaction might be required. The driver might be asked to sit comfortably in its normal driving position so that system can determine upper and lower thresholds needed for detecting potential nodding. The driver might also be asked to hold their eyes closed and then open for a matter of few seconds each time. This is enough to get the system started. Over time, the system will expand the dataset of obtained images and will become more error resistant and overall more robust. 

 

Tracking Stage : 

Once the driver’s head and eyes are properly located and all the necessary features are extracted, the system enters the regular tracking (monitoring) stage. A key step in this stage is the continuous monitoring of the driver’s eyes within a dynamically allocated tracking area. More specifically, in order to save some processing time, the system will determine the size of the tracking area based on the previous history of eye movements. For example, if the eyes were moving horizontally to the left for a number of frames it is to be expected that that trend with continue in the following frame also. So it is logical to expand the tracking area towards the expected direction of the eyes and shrink the area in other three directions. During this stage, the system must also determine the state of the eyes. All these tasks must be carried out in realtime; depending on the processor’s abilities and current load, it might be necessary to occasionally skip a few frames, without sacrificing algorithmic accuracy. 

 

Warning Stage: 

 If the driver keeps his eyes closed for prolonged period of time or starts to nod, alertness has to be raised. The key step within this stage is close monitoring of drivers eyes. The system must determine whether the eyes are still closed, and what is the eyes’ position relative to previously established thresholds. We cannot afford to skip frames in this stage. In practice, tracking of eyes is performed much in the same way as in the tracking stage with the addition of the following processes: calculation of velocity and trajectory of the eyes and threshold monitoring. These additional computations are required to improve the system’s ability to determine whether the driver is drowsy or not. 

Alert Stage : 

Once it has been determined that the driver appears to be in an abnormal driving state, the system has to be proactive and alert the driver of potential dangers that can arise. Combination of audio/visual alerts are used to attract the driver’s attention and raise their alertness level. Alerting has to be implemented in such a way as not to cause the opposite effect of intended and startle the driver into causing an accident. 

Convolution Neural Network 

 

It is assumed that the reader knows the concept of Neural networks. 
When it comes to Machine Learning, Artificial Neural Networks perform really well. Artificial Neural Networks are used in various classification tasks like image, audio, words. Different types of Neural Networks are used for different purposes, for example for predicting the sequence of words we use Recurrent Neural Networks more precisely an LSTM, similarly for image classification we use Convolution Neural networks. In this blog, we are going to build a basic building block for CNN. 
Before diving into the Convolution Neural Network, let us first revisit some concepts of Neural Network. In a regular Neural Network there are three types of layers: 
  

Input Layers: It’s the layer in which we give input to our model. The number of neurons in this layer is equal to the total number of features in our data (number of pixels in the case of an image). 

Hidden Layer: The input from the Input layer is then feed into the hidden layer. There can be many hidden layers depending upon our model and data size. Each hidden layer can have different numbers of neurons which are generally greater than the number of features. The output from each layer is computed by matrix multiplication of output of the previous layer with learnable weights of that layer and then by the addition of learnable biases followed by activation function which makes the network nonlinear. 

Output Layer: The output from the hidden layer is then fed into a logistic function like sigmoid or softmax which converts the output of each class into the probability score of each class. 

 

