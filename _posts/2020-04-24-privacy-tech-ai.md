---
layout: post
title: A starter guide for trustworthy AI
description: Example and introduction. Most updated from Openmined.
summary:  Example and introduction. Most updated from Openmined.
tags: [ai, summary, TrustworthyAI]
---


What you can find in this blog:

*   An example of how privacy tech is applied for genetic-data.
*   Introduce PYSYFT, with Microsoft [SEAL](https://github.com/Microsoft/SEAL) and Pytorch.
*   Introduce PYGRID, a P2P platform for private data science and federated learning.
*   Road map of PyGrid and PySyft in 2020.


# WHY AND HOW PRIVACY TECH SHOULD BE USED IN HEALTH DATA

[Link](https://blog.openmined.org/genetic-data-privacy/)

Genetic data has been known as an inference to understand disease, evolution, treatments and forensics.

Recently, the access has been open not only for research but the consumer market. People want to know about their ancestry, risk of some severe disease and how to change lifestyle and nutrition to reduce the potential. Law enforcement also uses it as the way to investigate crimes.

Your genetic code is invariant and unique. Once you share, this information can not be drawn back. For example, your height, weight, body mass index, voice, age, sex and ancestry could be inferred from your gentic profile. This application called “DNA phenotyping”



![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-24-privacy-tech-ai/GENT-TESTING.jpg)


*An example of phenotyping reconstruction on the _right whereas the real face is on the left. [Source](https://www.pnas.org/content/114/38/10166)*

This could open to an intrusive invasion of privacy in the present. For example, discrimination and bias in insurance policies which not cover life and disabilities. A negative side effect could be a lack of trust in healthcare when people are aware of their data shared unethically or involuntarily.

From this perspective, it takes society responsibility to work on legislation to assure that genetic data and its applications will not be exploited. Nonetheless, we could not wait for policy stakeholders to provide adequate documents of data protection.

In this case, technology could be a solution. There are several privacy-preserving techniques that have been introduced.


## Cryptographic

One of examples is homomorphic encryption. Intermediate results are encrypted and inaccessible.

A simple form of the workflow could be seen as

Input data _m  _→ encrypted - enc(_m_)_ _-  → perform _function f _on data  → decrypt - enc(f(_m_)) - → f(_m_) The biggest challenges of this technique is time-consuming.


### Hands-on package:  

*   Intel [HE-transform](https://www.intel.com/content/www/us/en/artificial-intelligence/posts/he-transformer-for-ngraph-enabling-deep-learning-on-encrypted-data.html)
*   Opemined [TenSEAL](https://github.com/OpenMined/TenSEAL)
*   Webank [FATE](https://github.com/FederatedAI/FATE)


## Information theory technique

Other names, multi-party computation (MPC). One of the examples is SPDZ “Speedz” protocol.


![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-24-privacy-tech-ai/OM-Graphic-1%403x.png)
*Source: Openmined Blog*


An example of a secure two-party computation in machine learning.


### Hands-on package:



*   Openmined + Cape Privacy + Alibaba [TF encrypted](https://github.com/tf-encrypted/tf-encrypted).
*   Facebook [CrypTen](https://github.com/facebookresearch/CrypTen)
*   WeBank [FAFE](https://github.com/FederatedAI/FATE)


# INTRODUCE PYSYFT WITH A MICROSOFT SEAL AND PYTORCH

[Link](https://blog.openmined.org/ckks-homomorphic-encryption-pytorch-pysyft-seal/) (Tutorial)

The motivation of homomorphic encryption (HE) in machine learning comes from a need of sharing machine learning models between companies and users.

The problem is that those models are not public, but users also want to use the model without exposing data. Here, HE is a technique that allows both entities to utilize resources without leaking information.

Here we introduce an example of TenSEAL - a library of HE encrypted operation on tensors. It is a wrapper of SEAL to tensor operations with HE of PySyft - an open source from Openmined. SEAL is an C++ library of cryptography and privacy research hosted by Microsoft.


# INTRODUCE PYGRID: A P2P PLATFORM FOR PRIVATE DATA SCIENCE AND FEDERATED LEARNING

[Link](https://blog.openmined.org/what-is-pygrid-demo/)


## Understand federated learning

It is a technique to train machine learning models, especially AI-based algorithms, without losing an ownership of data. Models are owned by AI companies.



![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-24-privacy-tech-ai/OM-Graphic-1%403x.png)
*Source: Openmined Blog*



![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-24-privacy-tech-ai/OM-Graphic-2%403x.png)
*Source: Openmined Blog*


The process: when an initial model is created, it is sent to the data owner’s device. In this case, it is Joe’s. After updating with data from Joe, the model will be returned to the company.



![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-24-privacy-tech-ai/OM-Graphic-3%403x.png)
*Source: Openmined Blog*


Now we update this model with Jane data in a similar way. (Sidenote: Sounds like a Poker uh?)

This process can be trained over many nodes of data. All can be done simultaneously on multiple nodes. Results can be averaged allowing faster improvements.


## Why is it good?



*   Data is on devices (hospital’s servers, mobile phones)
*   Privacy-preserve of sensitive data.
*   Remove legal liability for model owners (companies)
*   Reduce bandwidth for uploading huge dataset.


## Understand secure multi-party computation

![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-24-privacy-tech-ai/OM-Graphic-4%403x.png)
*Source: Openmined Blog*



![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-24-privacy-tech-ai/OM-Graphic-5%403x.png)
*Source: Openmined Blog*



## What is Pysyft and PyGrid, anyway?


![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-24-privacy-tech-ai/OM-Graphic-6%403x.png)
*Source: Openmined Blog*


Pysyft is a Python library built on top of Pytorch. It is aimed for secure and private deep learning and supported for both TensorFlow and Pytorch. Data scientists can use the framework for managing any kind of sensitivity data by applying preserving concepts without being privacy experts.


![alt_text](https://emmablogimg.s3.amazonaws.com/2020-04-24-privacy-tech-ai/OM-Graphic-7%403x.png)
*Source: Openmined Blog*

A peer to peer platform that uses PySyft for Federated Learning and Data Science. To describe, PyGrid use Gateways and Nodes with an analogy of DNS and routing nodes to access desired datasets. Data sets are nodes managed and monitored by owners. Data scientist will use PyGrid to get access to nodes through gateways to perform analysis or federated learning across multiple datasets.


## Use case 1: Private Statistical Analysis.



1. Data owner who wants to share sensitive data on his/ her node. (For example, a hospital).
    * Step 1: Import Pysyft and dependencies.
    * Step 2: Connect your node.
    * Step 3: Prepare data as tensors and add brief description.
    * Step 4: Define access rules and permissions
    * Step 5: Add tags and labels to help data scientists to find your dataset.
    * Step 6: Publish
2. Data scientist who wants to find a specific dataset over the grid network for some analytics statistics.
    * Step 1: Import Pysyft and dependencies.
    * Step 2: Connect Grid platform.
    * Step 3: Search for net work for datasets.
    * Step 4: Create a reference for data pointers.
    * Step 5: Understand and explore the data. In this step, data scientists can not copy data without an allowance of data owner.
    * Step 6: Run computation


## Use case 2: Cross-silo Federated Learning

In this section, we demonstrate how to use PyGrid architecture to perform federated learning across institutions or devices with MNIST.

As a data scientist, here is the process



* Step 1: Import PySyft and dependencies.
* Step 2: Define our model architecture.
* Step 3: Connect to the Grid Platform.
* Step 4: Search for your dataset.
* Step 5: Create a reference to a data pointer
* Step 6: Train your model


## Use case 3: Encrypted MLaaS

In this section, we will learn how to host models and perform interences in a secure and private way.

* Step 1: Import PySyft and dependencies.
* Step 2: Connect to the Grid Platform.
* Step 3: Define model.
* Step 4: Define input data.
* Step 5: Initialize model.
* Step 6: Serve model onto the grid network.
* Step 7: Return results.

# ROAD MAP 2020

## PyGrid

*   Heterogeneous network.
*   Privacy budget.
*   Automatic differential privacy tracking.
*   Data request queue.


## PySyft

*   Support tensor operations including dot-product, matrix multiplication and convolution.

*Most of this summary note is updated from the Content Sharing Call of OpenMined Community - one of the most active open groups about privacy-preserving data science and AI. Please go to original blogs for more details if you have any questions. Thanks Nick from Miratrix/ OpenMined to share information with me.*
