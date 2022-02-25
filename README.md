# DIMAL

This is a sample demo-code for the WACV 2019 paper: DIMAL: Deep Isometric Manifold Learning Using Sparse Geodesic Sampling
, by [Gautam Pai](https://sites.google.com/view/paigautam/home), [Ronen Talmon](https://ronentalmon.com/), [Alex Bronstein](https://bron.cs.technion.ac.il/) and [Ron Kimmel](https://www.cs.technion.ac.il/~ron/) 

[Paper](https://arxiv.org/pdf/1711.06011.pdf), [Poster](https://drive.google.com/file/d/1dS__6i5QTF6mwR-07UvgzYqy-rz4awqx/view), [Slides](https://drive.google.com/file/d/1qqfyWL2QDUdeGH5X1HAqcZ5yQ_7sasex/view)

![Alt text](Figures/S_Curve_FPS.png?raw=true)
## Main Functions

```
[S,T12,T21] = fast_sinkhorn_filter(KTar,KSrc,options)

%{
***Input***
(1.) KSrc -- a M X K Matrix of Features/Aligned Basis/Embedding in Source Shape with M Points and
K Features
(2.) KTar -- a N X K Matrix of Features/Aligned Basis/Embedding in Target Shape with N Points and
K Features
(3.) (optional) options struct - see below

***Output*** 
(1.) S -- The M X N doubly stochastic matrix after matrix scaling 
(2.) T12 -- pointwise forward map, i.e. Source(Src) to Target(Tar) 
(3.) T21 -- pointwise backward map, i.e. Target(Tar) to Source(Src)

***Parameters***
An options struct with the following
(1.) p -- (power of the distance for assignment matrix) - default set to 1
(2.) knn -- number of nearest neighbors for sparsifying kernel - default set to 50
(3.) distmax -- factor for choosing lambda, default value 500 as per https://marcocuturi.net/SI.html
(4.) maxiter -- number of matrix scaling iterations desired (~ 10-50)
(5.) kernel_type -- 'full' or 'sparse' (default) depending on nature of kernel desired. Choose 'sparse' for faster mode. 

***Additional Comments*** 
You can replace the knnsearch in this script with a possibly faster
k-nearest neighbor implementation for improved performance
%}
```
