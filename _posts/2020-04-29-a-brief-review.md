---
layout: post
title: A brief review of data safety in building an AI system. 
description: Example and introduction. Most updated from Openmined.
summary:  Example and introduction. Most updated from Openmined.
tags: [ai, summary, TrustworthyAI]
---
What you can find in this summary note:

*   Why would we care about safety from a perspective of car manufacture and design?
*   A particular example of decentralized methodology called “Split Neural Network”
*   An introduction of Recommendation System: the convention and the Federated fashion.

Related link: [A starter guide towards building a trustworthy AI](https://www.trackcovid19.tech/2020/04/24/privacy-tech-ai)

_Most of the content here is updated from the Content Sharing Call of OpenMined Community - one of the most active open groups about privacy-preserving data science and AI. Please go to original blogs for more details if you have any questions. Thanks Nick from Miratrix/ OpenMined to share information with me._

In some industries such as healthcare, operational logistic and finances, traditionally most of data is private and/or sensitive. In addition, there is still a need for applying machine learning techniques to solve problems. Take an example from healthcare. Applications could be used to increase patients' outcome by better diagnostics and reduce a time to make clinical decisions by doctors.

![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-29-a-brief-review/image6.png)
_Source: ShutterStock_

Nevertheless, data privacy becomes one of the most challenging barriers for innovation. The fact is people don’t know whether their data has not been sold on or used without their consent or stored longer than intended. Users also become more aware of their data used without consent. On the other side, it is difficult to manage the consent when gathering data. All of these makes the conventional industries be difficult to move forward data protection policies, e.g. GDPR or California Privacy Consumer Act.


# Big picture: The past, the present and the future

Why would we care about safety from a perspective of car manufacture and design?

![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-29-a-brief-review/image6.png)


Source: Seatbeltplus.com


## The past: Lessons

The three-point seat belt was introduced in 1959 by Nils Bohlin - the chief safety officer of Volvo. It was a result of tens of thousands of accidents studied by hundreds of experiments. This is a great demonstration of a commitment for public good. Using this example, would we ask ourselves whether there is a better way to promote an open culture of such innovation. 


## The present: Attention

There are three key points when working towards an AI system.



1. An importance of data.
2. A trend of implementing and updating safety critical features.
3. An optimization on an entire dataset.


![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-29-a-brief-review/image2.png)


_An example of a process to select an image by slicing function. The result we have is a photo satisfying rain and rain. Source: Openmined Blog._

Here, we pay more attention on the second highlight with three options: 



1. How to release a model without losing competitive advantage.
2. How to release enough data without losing privacy.
3. How to do both with Federated Learning, especially by identifying application and critical data subset with slicing functions.

![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-29-a-brief-review/image3.png)


A computer vision system in a self-driving car. Source: NVIDIA/VICTOR TANGERMANN


## The future: An ecosystem

Here is an hypothetical example of Federated Learning in Tesla computer vision system to identify pedestrians on country lanes.



1. Create a slicing function.
2. Function sent to an ecosystem governed by federated learning.
3. Approved or rejected by ecosystem members.
4. Models are federated to approving members.
5. Models are gathered and insight gained.



![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-29-a-brief-review/image4.png)


_Source: Openmined Blog_

In such system, we would have an ecosystem achieve three goals:



*   **Mission critical:** Decentralization ownership of data, e.g. backlog.
*   **Insights:** Data as a service.
*   **Commodity:** Access for every manufacturer.


# Case study 1: Data storage



*   A particular example of decentralized methodology called “Split Neural Network”


## Introduce SplitNN

The critical pain point is a centralization of data, which leads us to an approach of decentralization. Here we introduce a concept called Split Neural Network from Open Minded. This technique was introduced by MIT in December 2018, then opened a new branch of privacy-preserving research in machine learning. In simple words, we split a training process into two or more hosts. Each part is self-contained, so it feeds the segment in front.


![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-29-a-brief-review/image5.png)


A diagram of how SplitNN works. [Source](https://arxiv.org/abs/1810.06060)


## Why would we use a SplitNN?



*   Remove a burden of training neural networks up to 2000%



![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-29-a-brief-review/image1.png)


An illustration of how effective it is [Source](https://arxiv.org/abs/1812.00564)


## Train & Implementation of a SplitNN

Please go to the blog for further information. [Blog](https://blog.openmined.org/split-neural-networks-on-pysyft/)


# Case study 2: An application of using data

An introduction of Recommendation System: the convention and the Federated fashion.


## “Recommendation system”: what is it? 

An engine that allows websites and mobile applications to suggest information based on pre-existing data. 

Some examples are Facebook Ads, Amazon Suggest Product, Youtube recommended videos. The good side is an exploration of new ideas and products. The down side is unwanted decisions, e.g. purchasing a service that you don’t need, spending too much time on cats and dogs video, etc. Most of these are driven by algorithms with your personal data.

Technically, there are three main domains of such algorithms:



1. **Content filtering:** Create a portrait by item and user with a set of features. It is aimed to understand interests.
2. **Collaborative filtering:** A common way to build a recommendation system by applying a technique called Matrix Factorization. It is solely based on an interaction between data and a platform, e.g. e-commerce website.
3. **Hybrid filtering:** A combination of the above.

Other domains,



1. Learning to rank with ranking/ recommendation/ search domain.
2. Neural based recommendation system: Neural collaborative filtering, wide and deep networks.


## Privacy preserving recommendation systems

This post is an example of how to build a federated collaborative filtering model via matrix factorization.


## How to do federated collaborative filtering (Federated ALS)

Highlights



*   All item vectors are updated on the central server then distribute and redistribute to each clients (device/ user)
*   The user vectors are trained on devices using owner’s with item latent vectors.
*   Gradients for each item vector are calculated and propagated back to the central server where it is aggregated and item vectors updated.
*   Performance comparison between the convention and the Federated Fashion showed a slight difference by a study in a simulated environment.
*   A notion of engineering challenges for an entire dataset.


## Train & implementation of Federated ALS

Please go to the blog for further information. [Blog](https://blog.openmined.org/federated-learning-recommendations-part1/)

