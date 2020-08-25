# Modelling lower limb sockets through Statistical Shape analysis
A repository containing examples of transtibial and transfemoral sockets generated using a Statistical Shape Model.

## Folder Structure
* Transtibial: 100 .npy files
* Transfemoral: 100 .npy files

## Shape Generation
The shapes were as part of the work described in the article "Modelling lower limb sockets through Statistical Shape analysis", up for consideration in BIBM 2020 conference.

They were built from a Statistical Shape Model trained on 51 examples of transtibial and transfemoral sockets. The new shapes were generated according to the formula:

<img src="https://render.githubusercontent.com/render/math?math=F=\overline{F} + \sum_{m=1}^{M}PC_{m}b_{m}">

Where F is the new shape, M is the number of principal components considered, PC is the principal component and b is a weight factor. The weight factors were randomly chosen from plausible ranges, as defined by orthoprosthetists. 

Due to a preprocessing stage, the transtibial examples have 4,731 points, while transfemoral examples have 11,487 points.

## Examples
![alt text](augmented.png?raw=true)
