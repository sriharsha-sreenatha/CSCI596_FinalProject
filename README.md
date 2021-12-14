# Explainable AI - Visualing Convolutional Neural Network using Grad-CAM: Gradient-weighted Class Activation Mapping
This repository is for the final project of CSCI596 - Scientific Computing and Visualization.

- _Madhura Murulidhar (USC-ID: 4732217557)_
- _Sriharsha Sreenatha (USC-ID: 1357016181)_

<h2>Motivation/Abstract</h2>

Machine Learning and AI models are witnessing its use in various domains like Healthcare, FinTech, Physics, Aerospace etc. Though these models are capable of giving accurate solutions, developers who designed it cannot explain and understand why the model arrived at particular decision which makes the model a 'black-box'. Explainable AI helps in demystifying the models. This study concentrates on Grad-CAM: Gradient-weighted Class Activation Mapping[1] which will enable humans to understand what features/parts of the image Convolutional Neural Network is looking at. 

Recent detection methods of COVID-19 disease involves CNN models capturing modal features from chest X-rays images. There can be cases where model predicts false-positives. We can apply this study to produce a heat-map on the X-ray images to understand why and how CNN model gave the decision.

<h2>Requirements</h2>
<ul>
  <li> Python 3 </li>
  <li> Google Colab </li>
  <li> Tensorflow v2.7.0 </li>
  <li> VGG-16 model [2] </li>
  <li> Keras </li>
</ul>

<h2>Method</h2>
<h3>DataSet</h3>
The dataset[3] consists of labeled X-ray(PA-CXR) images of COVID-19, bacterial and viral pneumonia patients, and Normal people. 

Normal:
<img src="https://user-images.githubusercontent.com/28820837/146003836-239eb619-9930-4607-8ffe-065712e4b4ff.jpg" data-canonical-src="https://user-images.githubusercontent.com/28820837/146003836-239eb619-9930-4607-8ffe-065712e4b4ff.jpg" width="100" height="100" />

Pneumonia: 
<img src="https://user-images.githubusercontent.com/28820837/146003883-dec5ac34-5599-4df6-9c82-1d8d2705524f.jpg" data-canonical-src="https://user-images.githubusercontent.com/28820837/146003883-dec5ac34-5599-4df6-9c82-1d8d2705524f.jpg" width="100" height="100" />

COVID-19:
<img src="https://user-images.githubusercontent.com/28820837/146002877-7280fd5c-c2b0-4088-a5c5-18e77ff8d02b.jpg" data-canonical-src="https://user-images.githubusercontent.com/28820837/146002877-7280fd5c-c2b0-4088-a5c5-18e77ff8d02b.jpg" width="100" height="100" />


<h3>Model</h3>

<h3>Grad-CAM</h3>
Gradient-weighted Class Activation Mapping (GradCAM) uses the gradients of any target concept, flowing into the final convolutional layer to produce a coarse localization map highlighting the important regions in the image for predicting the concept.

<h4>Architecture</h4>
On the trained model, perform below steps:

- Load an image 
- Infer the image and get the topmost class index
- Take the output of the final convolutional layer
- Compute the gradient of the class output value w.r.t to feature maps
- Pool the gradients over all the axes leaving out the channel dimension
- Weigh the output feature map with the computed gradients (+ve)
- Average the weighted feature maps along channels
- Normalize the heat map to make the values between 0 and 1

![network](https://user-images.githubusercontent.com/13382099/143785350-2d6ca00a-64dc-4617-903c-c99d5f72a6f4.png)

<h2>Results</h2>

The CNN model to detect COVID-19 disease from X-ray images showed:

**Training accuracy: 91.7%**

**Validation accuracy: 93.17%**

<ol>
<li>A random X-ray image of type='NORMAL' was selected from the test dataset.</li>
<li>Model predicted the as type 'PNEUMONIA' which was false positive.</li>
<li>Grad-CAM visualization heatmap was produced on the image to see where the last convolution layer of the model was extracting features. </li>
  <h4> Observation </h4>
    From results, it can be seen that there can be false positive predictions. Visualizing why the model predicted using Grad-CAM is helpful for further investigation than blindly accepting model's prediction. With this study, the model's performance can be optimized by looking at where the model is going wrong.
</ol>

Image of type 'NORMAL'

<img src="https://user-images.githubusercontent.com/28820837/146004959-a93c03b1-295d-43a0-acff-90df51ecb350.png" data-canonical-src="https://user-images.githubusercontent.com/28820837/146004959-a93c03b1-295d-43a0-acff-90df51ecb350.png" width="250" height="250" /> 

Predicted as 'PNEUMONIA' - Grad-CAM Heatmap

<img src="https://user-images.githubusercontent.com/28820837/146004987-26ed8759-870b-495a-b138-6e94cf42fcd5.png" data-canonical-src="https://user-images.githubusercontent.com/28820837/146004987-26ed8759-870b-495a-b138-6e94cf42fcd5.png" width="250" height="250" /> 
  
<h2>Future Goals</h2>

![image](https://user-images.githubusercontent.com/13382099/143785469-9187ed0e-e240-4a45-9105-9aee430c1e0f.png)

<h2> Author Contribution </h2>

Madhura Murulidhar (USC-ID: 4732217557):

- Researched and understood Explainable AI.
- Explored Grad-CAM.
- Implemented Grad-CAM on pre-loaded VGG-16 model for sample picture of lion.
- Preprocessed X-ray image dataset.
- Observed the results.
- Report creation

Sriharsha Sreenatha (USC-ID: 1357016181):

- Researched and understood Explainable AI.
- Developed model using Transfer Learning from VGG-16.
- Trained model and tested for few images in test dataset.
- Produced heatmap on one of the image of test data.
- Observed the results.
- Report creation.

<h2>References</h2>
<ol>
<li> Ramprasaath R. Selvaraju et al., 2019 Grad-CAM: Visual Explanations from Deep Networks via Gradient-Based Localization. International Journal of Computer Vision, no. 2 (2020): 336-359.
  https://arxiv.org/pdf/1610.02391v4.pdf </li>
  <li> K. Simonyan, A. Zisserman, Very Deep Convolutional Networks for Large-Scale Image Recognition. International Conference on Learning Representations, 2015. </li>
<li> S. Daniel, G. Michael et al., Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning
2018: Cell, Volume: 172, Issue: 5, pp 1122-1131  DOI: 10.1016/J.CELL.2018.02.010 https://www.cell.com/cell/fulltext/S0092-8674(18)30154-5 </li>
</ol>
