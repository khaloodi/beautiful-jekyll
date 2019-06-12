---
layout: post
title: Predicting The Functional Status of Pumps in Tanzania
subtitle: My First Kaggle Competition
---

Increasing population growth and urbanization pose serious pressure on the quantity and quality of available water. The sustainability of the present and future human life and environment depends mainly on proper water resources management.

![](/img/tanzania_water_pump.jpeg)

To do this we can analyze the functional status of the available water points in Tanzania (in our case). Specifically I looked  into the dataset of water pumps in Tanzania to predict the operating condition of a water point. There are three categories that classify the functional status of water pumps: functional, non functional, and non functional needs repair.

Throughout experimentation an iterative approach is utilized to progressively learn and improve upon accuracy scores. To begin my analysis I started with a naive baseline measurement the majority classifier as a fast first approach.

![](/img/majority_class.png)
![](/img/mc_accuracy.png)

As shown above, the naive baseline model purports an accuracy score of approximately 54%. Moving forward a train/validate split is used to not only improve the performance of the model but also avoid leaks. For a detailed explanation regarding the importance of this method check out this [article](https://www.fast.ai/2017/11/13/validation-sets/).

Next, [the category encoders library](https://contrib.scikit-learn.org/categorical-encoding/) is used to perform one-hot-encoding on categorical features of the dataset. This is a required preprocessing step in order to perform linear regression. 

![](/img/logistic_regression.png)

As we can see the model's accuracy score increases to 65.8%.

Scikit-learn's pipeline method is then used to manage the fit and transform operations on our split datasets. as opposed to using encoders and scalers in scikit-learn (shown above). 


