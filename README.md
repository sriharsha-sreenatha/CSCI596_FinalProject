# CSCI596_FinalProject
This repository is for the final project of CSCI596 - Scientific Computing and Visualization.

**Grad-CAM: Gradient-weighted Class Activation Mapping - Visual Explanations from Deep Networks via Gradient-based Localization**

**Motivation/Abstract**

Machine Learning and AI models are witnessing its use in various domains like Healthcare, FinTech, Physics, Aerospace etc. Though these models are capable of giving accurate solutions, developers who designed it cannot explain and understand why the model arrived at particular decision which makes the model a 'black-box'. Explainable AI helps in demystyfying the models. This study concentrates on Grad-CAM: Gradient-weighted Class Activation Mapping which will enable humans to understand what features/parts of the image Convolutional Neural Network is looking at. 

Recent detection methods of COVID-19 disease involves CNN models capturing modal features from chest X-rays images. There can be cases where model predicts false-positives. We can apply this study to produce a heat-map on the X-ray images to understand why and how CNN model gave the decision.

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
