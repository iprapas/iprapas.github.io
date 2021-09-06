+++
date = "2021-08-30"
draft = false
title = "Fresh publication: Continuous Deployment of Deep Learning models"
tags = ["publication", "research", "deep learning"]
categories = ["Data Science", "Data Engineering", "Model Deployment", "Deep Learning"]
toc = true
+++

Check my research article presentation on "Continuous Training and Deployment of Deep Learning models" at LWDA 2021 - Wednesday, Sep 1st 14:00-14:20 CET. It is free to attend, you only need to register [here](https://mcml.ai/lwda2021/attending).

This article is based on the thesis I did for the completion of my studies in the Big Data Management and Analytics (BDMA) Erasmus Mundus MSc.

*Abstract*
>Deep Learning (DL) has consistently surpassed other Machine Learning methods and achieved state-of-the-art performance in multiple cases. Several modern applications like financial and recommender systems require models that are constantly updated with fresh data. The prominent approach for keeping a DL model fresh is to trigger full retraining from scratch when enough new data are available. However, retraining large and complex DL models is time-consuming and compute-intensive. This makes full retraining costly, wasteful, and slow. In this paper, we present an approach to continuously train and deploy DL models. First, we enable continuous training through proactive training that combines samples of historical data with new streaming data. Second, we enable continuous deployment through gradient sparsification that allows us to send a small percentage of the model updates per training iteration. Our experimental results with LeNet5 on MNIST and modern DL models on CIFAR-10 show that proactive training keeps models fresh with comparable - if not superior - performance to full retraining at a fraction of the time. Combined with gradient sparsification, sparse proactive training enables very fast updates of a deployed model with arbitrarily large sparsity, reducing communication per iteration up to four orders of magnitude, with minimal - if any - losses in model quality. Sparse training, however, comes at a price; it incurs overhead on the training that depends on the size of the model and increases the training time by factors ranging from 1.25 to 3 in our experiments. Arguably, a small price to pay for successfully enabling the continuous training and deployment of large DL models. 

([preprint pdf](/blog/lwda2021-article/dl_continuous_deployment.pdf) | [code](https://github.com/iprapas/dl-continuous-deployment))