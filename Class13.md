# Linear regression

Linear regression is a basic and commonly used type of predictive analysis.  The overall idea of regression is to examine two things: 

1. does a set of predictor variables do a good job in predicting an outcome (dependent) variable?

2. Which variables in particular are significant predictors of the outcome variable

example: 
![linear](./images/exa%20linear.png)

##  how to implement a linear regression in Python

- The first step is to import the required Python libraries into Ipython Notebook.

![importing](./images/Explore-1%20(1).png)

- in the examples w'll use a data set from sklearn

![data](https://bigdata-madesimple.com/wp-content/uploads/2016/04/sklearn.png)

-  In this data set I have 506 instances(rows) and 13 attributes or parameters(columns). The goal of this exercise is to predict the housing prices in boston region using the features given.


- convert boston.data into a pandas data frame.

![dataframe](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Pandas-DataFrame.png)

- import linear regression from sci-kit learn module.

![linearreg](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Skitlearn-linear-model1.png)

- ### plt

![plotting](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Scatter-plot.png)

- output 
![example](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Relationship-between-RM-and-Price.png)
