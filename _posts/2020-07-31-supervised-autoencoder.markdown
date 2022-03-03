---
layout: post
title:  ""
date:   2020-07-01 11:00:01
categories: machinelearning
image: /img/sae_schematic.png
author: Paul Hanakata
---
##### Forward and inverse design for structural design via supervised autoencoder
Recently, there has been great interests in applying mechanine learning to design composite materials. Early studies in optimizing materials properties usually use a supervised machine learning (ML) model as a forward solver. Typically, a supervised ML model is trained with a very large datasets and then the supervised model is used to predict materials outside the traning sets. Another approach is to train a supervised model iteratively with small datasets, similar to optimization tool such as  genetic algorithm or greedy algorithm, and ask the model to generate superior designs. More details can be found in my paper[1] or my other post on using CNN to search optimal kirigami design. 

Another popular machine learning approach to generate new designs is generative model such as autoencoder (AE), variational autoencoder (VAE), and Generative Adversarial Neural Networks (GANs). Generative models have shown great success in generating realistic synthetic data. Motivated by this advancement, we adopted this type of generative models to solve forward and inverse problem in mechanics. In this work we propose a *supervised* autoencoder (sAE) for inverse structural design. We set up our training such that we can evaluate the effectiveness of interpolation (generating new designs) within and outside the training domain. First, we find that the sAE is able to generate designs consisting of mixed cuts even though the sAE is trained with kirigami structures with only parallel and orthogonal cuts, which shows the ability of sAE to perform interpolation in the latent space. Moreover, in the latent space, the sAE captures similarities and differences between distinct structures with different cut types whereas the information about cut types is not provided during the training. As generalization requires diversity in the training set, we can leverage the ability of the sAE to distinguish different structures in the latent space to use it as an exploration strategy to propose designs that lie outside the training data.

###### Basic principles of sAE 
An autoencoder (AE) consists of two parts: (i) an encoder $\mathcal{E}$ that maps a vector to a reduced representation and (ii) a decoder $\mathcal{D}$ that reconstructs a vector to its original representation from the reduced representation. The standard loss function of AE is

$$\mathcal{L}^{\mathcal{X}}(\pmb{x},\pmb{x}')=\frac{1}{m}\sum_{i=1}^{m}|\pmb{x}^{(i)}-\pmb{x}'^{(i)}|^2=\frac{1}{m}\sum_{i=1}^{m}|\pmb{x}^{(i)}-\mathcal{D}(\mathcal{E}(\pmb{x}^{(i)}))|^2,$$

where $\pmb{x}\in{\rm R^n}=\mathcal{X}$ be the $n$-dimensional vector, and $\pmb{z}=(z_0, z_1, \cdots, z_{p-1})\in{\rm R^p}=\mathcal{Z}$ be the $p$-dimensional latent variables. Since we want to prescribe a user chosen design to the networks, we modify the loss function by "inserting" materials' target properties into the latent space 

$$\mathcal{L}^{\mathcal{Y}}(\pmb{y}, \pmb{z})=\frac{1}{m}\sum_{i=1}^{m}|\pmb{z}^{(i)}-\pmb{y}^{(i)}|^2=\frac{1}{m}\sum_{i=1}^{m}\sum_{k=0}^{d-1}|z_k^{(i)}-y_k^{(i)}|^2.$$

Specifically for our problem we use a 2D image of graphene with each pixel representing cut or no cut as the input vector $\pmb{x}$ and the target properties, ultimate stress and ultimate strain, as $\pmb{y}$. 

###### Main results 
With this sAE we are able to reconstuct the "mechanical design space" in the latent space. This allows us to do both predict mechanical properties based on the structural design (cuts locations) and also to generate new design by interpolating between different designs in the latent space. One limitation is that sAE performs very well inside the training domain but not too great for generating designs outside the training domainm, i.e., extrapolation. We  also investigated how we can use similarity metric to generate new "novel" designs that are not present in the traning designs. Interestingly, we can generate designs with mixed cuts which are not present in the training set. More details can be found in our paper[2]. We hope to use sAE for other inverse design problems accross different scales. If you are interested in collaborating feel free to shoot me an email! 

Here are the main takeaways of our work:
1. We show that supervised Autoencoder is able to organize material's properties in latent space
2. We find that we can use sAE to interpolate materials' properties in latent space and map these back to configurational space (i.e materials microstructures)
3. Using diversity metric we introduce a way to generate novel structures that are *different* from the training samples 

***References***:
<a href="https://journals.aps.org/prresearch/abstract/10.1103/PhysRevResearch.2.042006" style="color:#268cd7">[2] **P. Z. Hanakata**, Ekin D. Cubuk, David K. Campbell, and Harold S. Park, "Forward and inverse design of kirigami via supervised autoencoder", *Phys. Rev. Research*, 2, 042006(R)  (2020).</a>

<a href="https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.121.255304" style="color:#268cd7">[1] **P. Z. Hanakata**, Ekin D. Cubuk, David K. Campbell, and Harold S. Park, "Accelerated search and design of stretchable graphene kirigami using machine learning", *Phys. Rev. Letter*, 121, 255304 (2018).</a>

Some of the analysis and TensorFlow codes are avalaible in my GitHub page: <a href="https://github.com/phanakata/ML_for_kirigami_design" style="color:#268cd7"> https://github.com/phanakata/ML_for_kirigami_design</a>

