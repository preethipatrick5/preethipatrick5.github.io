
# Robustness of Deepfake Detection Model

  

## What?

  
<div style="text-align: justify">
My dissertation involved trying to understand the Robustness of various machine learning models that are used for Deepfake Detection. I chose this topic, out of the several, as it seemed challenging and was addressing a very important topic of conversation. Let me start by explaning what deepfakes are even though most people should have heard the term.  

Deepfake is a digitally edited, surrealistic video that shows an individual saying or doing something that isn't happening. Feeding their footage to a deep learning system and training them to exchange faces is part of the process. On the left of the Figure, a snapshot from the original interview with talk show Alison Brie, and on the right is a snapshot from a received deepfake showing Alison Brie's body and Jim Carrey's face. Deepfakes are hard to spot because they use authentic video and legitimate audio and aim to go viral on social media. As a result, many viewers believe the film they are watching is genuine.
<img  src="pages/images/dissertation/deepfake_example.png?raw=true"/>
</div>  

## How?

  

The how started with finding a dataset that can closely represent the latest updates in the deepfake domain.

  

I chose [DFDC](https://ai.facebook.com/datasets/dfdc/) and [FaceForensics++](https://www.kaggle.com/datasets/sorokin/faceforensics) as they were both the state of the art datasets available for deepfake related research.

  

### DFDC

  

The dataset created by [Meta](https://ai.facebook.com/) for the challenge consists of more than 100,000 videos. DFDC is the largest publicly available deepfake dataset utilizing multiple deepfake models. The dataset is specifically created with paid actors with consent. This dataset part of the Kaggle deepfake detection competition. It is meant to provide a framework to be used to build detector models that works on the real world. Another smaller version of this is available which is meant to encourage more research. But the same care to the variety of data can be seen here as well.

  

#### [Preview dataset](https://arxiv.org/abs/1910.08854)

  

- 5k videos

  

- Featuring two facial modification algorithms

  

#### [Full dataset](https://arxiv.org/abs/2006.07397)

  

- 124k videos

  

- Featuring eight facial modification algorithms

  

### FaceForensics

  

FaceForensics++ is a forensics dataset consisting of 1000 original video sequences that have been manipulated with four automated face manipulation methods: Deepfakes, Face2Face, FaceSwap and NeuralTextures.  The way the dataset is built is specifically for that purpose to allow researchers to compare the performance against specific deepfake generator models.


### Project Goals

Deepfakes are becoming increasingly dangerous to people's privacy, society's security, and democracy. This problem is unsurprisingly more apparent when new deepfakes algorithms arise. Thus there is a need for creating algorithms that are really good at detecting these manipulations. Each time a deepfake is generated, a detection method should also arise. There are plenty of algorithms that are created for the detection but not everything is adaptable to noise exposure. In this project the robustness of various detection algorithm is analysed. This would let us understand how strong the algorithm works when noise is added and if the algorithm can be improved. This helps improve detectors so that generators cannot fool detectors by adding noise.

This project uses the popular DFDC Preview \& FF++ Datasets for the experiments. The project has employed 3 different types of algorithms to observe and monitor the robustness; CNN, CNN+LSTM \& finally 3D-CNN. These 3 algorithms form the baseline. These algorithms are initially trained on both datasets. These models are initially evaluated on the clean dataset, once the performance is measured, they are evaluated again after exposing the data to 9 different noises including Gaussian Blur, Gaussian Noise,  Padding, Perspective Transform, Pixelization, Random Noise, Saturation, Shuffle Pixels \& finally a random combinations of these. This forms the initial set of results for the project. Once the performance of each algorithm is measured, the next step is to improve the model performance. For the same, the models are then trained again exposing it to random combination of above mentioned noises. This retrained model is again evaluated following the same procedure as mentioned above to observe the performance gain of each model.