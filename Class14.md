# Matplotlib

- matplotlib is probably the single most used Python package for 2D-graphics.

- it provides both a very quick way to visualize data from Python and publication-quality figures in many formats.

## IPython

- IPython is an enhanced interactive Python shell that has lots of interesting features

## pyplot

- pyplot provides a convenient interface to the matplotlib object-oriented plotting library 

## Simple plot

1. get the data for the sine and cosine functions:

```
import numpy as np

X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
C, S = np.cos(X), np.sin(X)
```

- X is now a NumPy array with 256 values ranging from -π to +π (included). C is the cosine (256 values) and S is the sine (256 values).

```
import matplotlib.pyplot as plt
plt.plot([1,2,3,4])
plt.ylabel('some numbers')
plt.show()
```

output:
![plt](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_1.png)


- Matplotlib comes with a set of default settings that allow customizing all kinds of properties. You can control the defaults of almost every property in matplotlib: 

- figure size 
-  dpi
- line width
- color and style
- axis and grid properties,and alot more 

## Setting limits

```
plt.xlim(X.min()*1.1, X.max()*1.1)
plt.ylim(C.min()*1.1, C.max()*1.1)
```
output: 
![pltlim](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_4.png)

- and a lot more you can do using Matplotlib [Matplotlib tutorial](https://github.com/rougier/matplotlib-tutorial)

- [Python For Data Science Cheat Sheet
](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Python_Seaborn_Cheat_Sheet.pdf)