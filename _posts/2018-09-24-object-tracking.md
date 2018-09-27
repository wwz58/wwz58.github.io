---
title: object tracking
tags: OT
---
## Intro
Modern trackers can be roughly divided into two branch
- The first branch 
is based on correlation filter, which
trains a regressor by exploiting the properties of circular
correlation and performing operations in the Fourier domain.
It can do online tracking and update the weights of
filters at the same time efficiently.
Recent correlation filter based
methods use deep features to improve the accuracy, but it
largely harms the speed during model update
-  Another
branch of methods aims to use very strong deep features
and do not update the model [13, 4, 35]. However,
because the domain specific information is not used, performance
of these methods is always not as good as correlation
filter based methods.

## Siam-RPN
