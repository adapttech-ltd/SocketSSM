# Modelling lower limb sockets through Statistical Shape analysis
A repository containing examples, in pointcloud format, of transtibial and transfemoral sockets generated using a Statistical Shape Model. 

## Folder Structure
* Transtibial: 100 .npy files
* Transfemoral: 100 .npy files

## Shape Generation
These artificial shapes were as part of the work described in the article "Modelling lower limb sockets through Statistical Shape analysis", up for consideration in BIBM 2020 conference.

They were built from two Statistical Shape Models (one pertaining the transtibial, and another the transfemoral sockets), trained on 30 transtibial sockets and 21 transfemoral sockets which were acquired through a laser-based 3D inner socket shape scanner (INSIGHT<sup>TM</sup> Scanner from [Adapttech](https://www.adapttech.eu/)). Before the model generation, the sockets from the left leg were mirrored, thus all provided examples will be right leg sockets. The new shapes were generated according to the formula:

<img src="https://render.githubusercontent.com/render/math?math=F = \overline{F} \+ \sum_{m=1}^{M} PC_{m}b_{m}">

Where `F` is the new shape, `M` is the number of principal components considered, `PC` is the principal component and `b` is a weight factor. The weight factors were randomly chosen from plausible ranges, as defined by orthoprosthetists. 

Due to a preprocessing stage, the transtibial examples have 4,731 points, while transfemoral examples have 11,487 points. 

## Socket Examples
![alt text](augmentation.png?raw=true)

## Load Example

To load and visualize one of the generated examples, simply run:
```python
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

pcl = np.load("TF/sockettf_008070.npy")
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.scatter(pcl[:, 0],
           pcl[:, 1],
           pcl[:, 2])
plt.show()
```
The shape of this array is  `(n,3)` where `n` is the number of points.


