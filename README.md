# Face2Multimodal

[**VideoPreview(Youtube)**](https://youtu.be/Pb4gTS0ghGI)  
This website presents Face2Multimodal Demo, powered by BROOK Database.

## Introduction

We present an in-vehicle real-time design to estimate driver's multi-modal states(skin conductance and heart rates) and driving status(speed) through their facial expressions. For each kind of data flows, we apply DenseNet as the model architecture.

## Showcase Examples
Hereby, we showcase one example use case: Face-to-Multimodal Predictor, as follow.

![example](https://raw.githubusercontent.com/unnc-idl-ucc/BROOK/master/figures/facecapture.jpg){:height="200" width="300"}
![predictor](https://raw.githubusercontent.com/unnc-idl-ucc/BROOK/master/figures/Estimator.jpg){:height="200" width="300"}

## How to Setup

1. Utilize a face detector (e.g. dlib) to crop the driver's front face and resize to 224x224 px.
2. Load the model under the folder "models" by PyTorch and set the face as the input.
3. Run the model and get the predict result.
4. Because predicting results is represented as a class number, some computation is required to get the result:
  * For predicting heart rate: result = predict result + 60
  * For predicting skin conductance: result = predict result/10.0
  * For predicting vehicle speed: result = predict result

   
## Models for Demonstrations

All models are saved under the folder "models". Sample models of DenseNet-BC-100. Training data contains Heart Rates(per minute), Skin Conductance(uS), Speed (km\h). The training procedure is powered by PyTorch. Further trainings are work-in-progress, we are confident that extensively hyperparameter adjustment would imporve the accuracy.

## Accuracy
![accuracy](https://raw.githubusercontent.com/unnc-idl-ucc/BROOK/master/figures/Accuracy.png)
