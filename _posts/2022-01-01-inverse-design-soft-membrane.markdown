---
layout: post
title:  ""
date:   2022-01-01 11:00:01
categories: machine learning 
image: /img/invMembrane/animals.png
author: Paul Hanakata
---
#### Inverse design via machine learning
Recenty there are many ongoing work on applying machine learning (ML) to mechanics, which primarily focus on predicting mechanial properties and stress-strain relationship. Here, we take ML furhter by applying it to design soft membranes. One direct application of our machine learning  design approach is for designing inflated membranes with specified contacts (i.e., 3D target shape) which is important for developing mechanotherapy devices. 
<img src="/img/invMembrane/scars1.png" width="50" height="50" />

<table class="image" align="center">
<caption align="bottom">{{ "<i></i>" }}</caption>
<tr><td><img src="/img/scars1.png" alt="Valley degree of freedom" description="Drawing" style="width: 300px; max-width:100%;"/></td></tr>
</table>



I am summarizing our findings below:

We first showed that membranes with soft and stiff elements have non trivial shapes upon inflation. We then developed an FEM model to match the experiments and used the FEM simulations for training. Our goal is to map an inflated 3D shape onto 2D binary design+pressure.
<img src="/img/invMembrane/experiment.png" width="50" height="50" />


We generated training samples using three classes of designs: Random (sparse and random), Islands (clusters of elements with same type), and Fibers (arrays of elements with same type). Because of symmetries we used reflection and rotation to get data points for free!
<img src="/img/invMembrane/training.png" width="50" height="50" />


We found that model that is trained only with one class does not perform well when tested on a different class. This is not surprising yet, many, if not most, works on applying ML to mechanics use training samples with random microstructures.
<img src="/img/invMembrane/performance_diff_training.png" width="50" height="50" />

As the design space is very large ($2^100$ in our case), it’d be hard to randomly sample *many* designs with arrays or clusters of the same element; this region consisting clusters/arrays of stiff/soft elements is where most interesting inflated 3D shapes reside.

Our approach, in someway, *boosts* the performance in the area of interest without the need to sample more using the random class. So it's important to have a good sampling!

Having trained our model with all classes, we are able to predict binary designs and pressures. We used some animal shapes to test our ML and we validated the inflated shapes by FEM simulations and experiments.
<img src="/img/invMembrane/animals.png" width="50" height="50" />

Finally, we showed that our design approach can be used for designing soft membranes with specified contacts. This is important for developing mechanotherapy devices where we want to avoid contact around scars.
<img src="/img/invMembrane/scars2.png" width="50" height="50" />


We have put lots of details in the supplementary for people who are interested in learning about the materials fabrication, finite element simulation methods, machine learning model, or the algorithms to generate island and fiber classes.


This work was in collaboration with <a href="https://bertoldi.seas.harvard.edu/" style="color:#268cd7">Katia Bertoldi's group</a> at Harvard SEAS.

**References***:
<a href="https://onlinelibrary.wiley.com/doi/abs/10.1002/adfm.202111610" style="color:#268cd7">[3] Antonio E. Forte, **Paul Z. Hanakata**, Lishuai Jin, Emilia Zari, Ahmad Zareei, Matheus C. Fernandes, Laura Sumner, Jonathan Alvarez, Katia Bertoldi, , "*Inverse design of inflatable soft membranes through machine learning*", Advanced Functional Materials, 202111610, (2022).</a>\\






