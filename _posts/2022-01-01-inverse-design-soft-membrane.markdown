---
layout: post
title:  ""
date:   2022-01-01 11:00:01
categories: machine learning 
image: /img/T0.05_buckled.gif


author: Paul Hanakata
---
#### 
Recenty there are many ongoing work on applying machine learning (ML) to mechanics, which primarily focus on predicting mechanial properties and stress-strain relationship. Here, we take ML furhter by applying it to design soft membranes. 


Recently there has been great interests in utilizing thin elastic sheets for engineered materials. Foppl van Karman number vK=$YL^2/\kappa$, ratio between Young's modulus $Y$ multiply by system's dimensions $L^2$ and bending rigidity $\kappa$, is often used to characterized "thinness" or how easy the materials are to bend relative to stretching. Many studies have shown that introducing altrenating cuts, known as "kirigami cuts", can prevent failure as the sheet can buckle out of the plane and its joint components can bend in-plane like hinges. Under stretching thin elastic sheets will experience compression in the direction perpendicular to the loading and we can think this as a 1D Euler buckling problem.  In our previous work (see my other  <a href="https://phanakata.github.io/kirigami/2017/08/29/kirigami.html" style="color:#268cd7
">post</a>  or my paper <span style="color:#268cd7"> [2]</span>), we indeed find a universality relationship between buckling and stretching (compression perpendicular to loading) of thin elastic sheets with a single slit from the macro (cm size) to nano scale. I want to note in that work <span style="color:#268cd7"> [2]</span> the nano sheets (graphene and MoS2) are stretched at a very low temperature 4.2 K. Most of mechanical devices (actuators) are working preferably at room temperature 300 K. It was found that the bending rigidity (at long wave length) of graphene increases by more than 1000 at room temperature relative to its zero temperature value due to thermal fluctuations. This bending stiffening is similar to how a perfectly smooth A4 paper sheet can easily bent (cannot hold its own weight), whereas a flattened crumpled A4 paper with random corrugations can hold a pen! In this work I will address how temperature affects Euler buckling using mean field theory and tested on molecular dynamics similations.



