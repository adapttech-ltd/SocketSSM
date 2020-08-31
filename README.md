# Modelling lower limb sockets through Statistical Shape analysis
A repository containing examples of transtibial and transfemural sockets generated using a Statistical Shape Model.

## Folder Structure
* Transtibial: 100 .npy files
* Transfemoral: 100 .npy files

## Shape Generation
The shapes were as part of the work described in the article "Modelling lower limb sockets through Statistical Shape analysis", up for consideration in BIBM 2020 conference.

They were built from two Statistical Shape Models (one pertaining the transtibial, and another the transfemural sockets), trained on 30 transtibial sockets and 21 transfemoral sockets. Before the model generation, the sockets from the left leg were mirrored, thus all provided examples will be right leg sockets. The new shapes were generated according to the formula:

<img src="https://render.githubusercontent.com/render/math?math=F = \overline{F} \+ \sum_{m=1}^{M} PC_{m}b_{m}">

Where `F` is the new shape, `M` is the number of principal components considered, `PC` is the principal component and `b` is a weight factor. The weight factors were randomly chosen from plausible ranges, as defined by orthoprosthetists. 

Due to a preprocessing stage, the transtibial examples have 4,731 points, while transfemoral examples have 11,487 points. 

## Socket Examples
![alt text](augmentation.png?raw=true)

## Load Example

To load one of the generated examples, simply run:
```python
import numpy as np
pcl = np.load(filename)

```
The shape of this array is  `(n,3)` where `n` is the number of points.


