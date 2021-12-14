# Grad-CAM: Gradient-weighted Class Activation Mapping - Visual Explanations from Deep Networks via Gradient-based Localization
This repository is for the final project of CSCI596 - Scientific Computing and Visualization.

<h2>Motivation/Abstract</h2>

Machine Learning and AI models are witnessing its use in various domains like Healthcare, FinTech, Physics, Aerospace etc. Though these models are capable of giving accurate solutions, developers who designed it cannot explain and understand why the model arrived at particular decision which makes the model a 'black-box'. Explainable AI helps in demystifying the models. This study concentrates on Grad-CAM: Gradient-weighted Class Activation Mapping which will enable humans to understand what features/parts of the image Convolutional Neural Network is looking at. 

Recent detection methods of COVID-19 disease involves CNN models capturing modal features from chest X-rays images. There can be cases where model predicts false-positives. We can apply this study to produce a heat-map on the X-ray images to understand why and how CNN model gave the decision.

<h2>Requirements</h2>
<ul>
  <li> Python 3 </li>
  <li> Google Colab </li>
  <li> Tensorflow v2.7.0 </li>
  <li> VGG-16 model </li>
  <li> Keras </li>
</ul>

<h2>Method</h2>
<h3>DataSet</h3>
The dataset[2] consists of labeled X-ray(PA-CXR) images of COVID-19, bacterial and viral pneumonia patients, and Normal people. 
Normal: ![image](https://user-images.githubusercontent.com/28820837/145994648-1fe8f854-7ac1-40e3-9a70-11e1f8367d6e.png)
Pneumonia:
COVID-19: 

<h3>Model</h3>
<h3>Grad-CAM</h3>

<h2>Results</h2>
The CNN model to detect COVID-19 disease from X-ray images showed:
**Training accuracy: 91.7%
Validation accuracy: 93.17%**

<ol>
<li>A random X-ray image of type='NORMAL' was selected from the test dataset.</li>
  <li>Model predicted the as type 'PNEUMONIA' which was false positive.</li>
<li>Grad-CAM visualization heatmap was produced on the image to see where the last convolution layer of the model was extracting features. </li> </ol>
![image](https://user-images.githubusercontent.com/28820837/145995430-a2ce0211-871c-42b2-81f1-e9cf620cff5d.png) ![image](https://user-images.githubusercontent.com/28820837/145995450-5bab363d-7adf-4e2a-bf5a-847609ab16b0.png)

  
<h2>Future Goals</h2>
<h2>References</h2>
<ol>
<li> Grad-CAM: Visual Explanations from Deep Networks via Gradient-Based Localization. International Journal of Computer Vision, no. 2 (2020): 336-359.
  https://arxiv.org/pdf/1610.02391v4.pdf </li>
<li> Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning
2018: Cell, Volume: 172, Issue: 5, pp 1122-1131  DOI: 10.1016/J.CELL.2018.02.010 https://www.cell.com/cell/fulltext/S0092-8674(18)30154-5 </li>
</ol>
****
Link to paper: https://arxiv.org/pdf/1610.02391v4.pdf

Architecture

![network](https://user-images.githubusercontent.com/13382099/143785350-2d6ca00a-64dc-4617-903c-c99d5f72a6f4.png)

Visualization of each layer

![image](https://user-images.githubusercontent.com/13382099/143785580-a7833f13-4102-4a00-9d8e-dfcca741413f.png)

Last layer - For class: Glasses

![image](https://user-images.githubusercontent.com/28820837/143785818-7db4d0a1-4546-4634-8cd9-b3c2109777e2.png)
![image](https://user-images.githubusercontent.com/28820837/143785833-c13b9077-caf1-4c55-9ddc-682c65aeb349.png)


Where to go from here? Use-cases

![image](https://user-images.githubusercontent.com/13382099/143785469-9187ed0e-e240-4a45-9105-9aee430c1e0f.png)
