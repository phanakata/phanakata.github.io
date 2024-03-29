---
layout: post
title:  ""
date:   2020-12-01 11:00:01
categories: statistical mechanics 
image: /img/T0.05_buckled.gif


author: Paul Hanakata
---
#### Thermalized Euler Buckling 
Recently there has been great interests in utilizing thin elastic sheets for engineered materials. Foppl van Karman number vK=$YL^2/\kappa$, ratio between Young's modulus $Y$ multiply by system's dimensions $L^2$ and bending rigidity $\kappa$, is often used to characterized "thinness" or how easy the materials are to bend relative to stretching. Many studies have shown that introducing altrenating cuts, known as "kirigami cuts", can prevent failure as the sheet can buckle out of the plane and its joint components can bend in-plane like hinges. Under stretching thin elastic sheets will experience compression in the direction perpendicular to the loading and we can think this as a 1D Euler buckling problem.  In our previous work (see my other  <a href="https://phanakata.github.io/kirigami/2017/08/29/kirigami.html" style="color:#268cd7
">post</a>  or my paper <span style="color:#268cd7"> [2]</span>), we indeed find a universality relationship between buckling and stretching (compression perpendicular to loading) of thin elastic sheets with a single slit from the macro (cm size) to nano scale. I want to note in that work <span style="color:#268cd7"> [2]</span> the nano sheets (graphene and MoS2) are stretched at a very low temperature 4.2 K. Most of mechanical devices (actuators) are working preferably at room temperature 300 K. It was found that the bending rigidity (at long wave length) of graphene increases by more than 1000 at room temperature relative to its zero temperature value due to thermal fluctuations. This bending stiffening is similar to how a perfectly smooth A4 paper sheet can easily bent (cannot hold its own weight), whereas a flattened crumpled A4 paper with random corrugations can hold a pen! In this work I will address how temperature affects Euler buckling using mean field theory and tested on molecular dynamics similations.

Here are the main takeaways of our findings:
1. Buckling at finite temperature is *not* stationary and we thus need statistical mechanics
2. We use a mean field theory approach to describe buckling and find similar Euler critical buckling expression but with *renormalized* elastic constants 
3. Similar to critical phenomena in magnetic systems, we also find that the height center of mass can be used as an oorder parameter
4. We indeed find magnetic-like transitions with $$\beta=1/2$$ and we also find that the susceptibility height center of mass shows a diverging trend (similar to magnetic susceptibiliy) near the buckling transition
5. We also use pertubing field to detect buckling 
6. We find that elastic constants (Young's modulus, bending rigidty, critical buckling strain) become temperature dependent once the system becomes comparable to thermal length. 
All details can be found in our paper <span style="color:#268cd7"> [1]</span>!

###### Buckling at finite temperature 

###### Mean field theory 

###### Universality in thermalized buckling transition 






















<img src="/img/T0.05_buckled.gif" width="200" height="200" />



*To be continued*

***Final notes*** 

This work was in collaboration with <a href="https://www.kitp.ucsb.edu/bowick" style="color:#268cd7
">Mark Bowick's group</a> at UCSB. If you want to use our pictures or animations for your research please send me an email and I am more than happy to provide the files and also cite our paper [2].

***References***:

<a href="https://www.sciencedirect.com/science/article/abs/pii/S2352431621000602" style="color:#268cd7
">[1] **P. Z. Hanakata**, S. S.  Bhabesh, M. J. Bowick, D. R. Nelson, D. Yllanes, "*Thermal buckling and symmetry breaking in thin ribbons under compression*", Extreme Mechanics Letters, 44, 101270 (2021).</a>

<a href="http://pubs.rsc.org/-/content/articlelanding/2017/sm/c7sm01693j/unauth#!divAbstract" style="color:#268cd7
">[2]  M. A. Dias, M. P. McCarron, D. Rayneau-Kirkhope, **P. Z. Hanakata**, D. K. Campbell, H. S. Park, D. P. Holmes,"*Kirigami actuators*", Soft Matter, 13, 9087 (2017).</a>
