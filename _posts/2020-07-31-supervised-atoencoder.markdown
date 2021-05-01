---
layout: post
title:  ""
date:   2018-05-27 11:00:01
categories: machinelearning
author: Paul Hanakata
---
##### Machine learning for designing stretchable graphene kirigami
Recently, there has been great interests in applying mechanine learning to design composite materials. Early studies in optimizing materials properties usually use supervised learning as forward solver. Typically, a supervised model is trained with a very large datasets and then the supervised model is used to predict materials outside the traning sets. Another approach is to train a supervised model iteratively with small datasets, similar to optimization tool such as  genetic algorithm or greedy algorithm, and ask the model to generate superio designs. More details can be found in my paper[] or my other post on using CNN to search optimal kirigami design. 

Another popular machine learning approach to generate new designs is generative model such as varitional autoencoder.    

Here are the main takeaways of our work:
1. We show that supervised Autoencoder is able to organize material's properties in latent space
2. We find that we can use sAE to interpolate materials' properties in latent space and map these back to configurational space (i.e materials microstructures)
3. Using diversity metric we introduce a way to generate novel structures that are *different* from the training samples 




*To be continued ..*




***References***:
<a href="https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.121.255304" style="color:#268cd7
">[1] **P. Z. Hanakata**, Ekin D. Cubuk, David K. Campbell, and Harold S. Park, *Phys. Rev. Letter*, 121, 255304 (2018).</a>
<a href="https://arxiv.org/abs/1808.06111" style="color:#268cd7">[2] **Paul Z. Hanakata**, Ekin D. Cubuk, David K. Campbell, and Harold S. Park, arxiv.org/abs/1808.06111.</a>


Some of the analysis and TensorFlow codes are avalaible in my GitHub page: <a href="https://github.com/phanakata/ML_for_kirigami_design" style="color:#268cd7"> https://github.com/phanakata/ML_for_kirigami_design</a>

