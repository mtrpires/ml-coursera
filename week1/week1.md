# [Coursera Machine Learning](https://www.coursera.org/learn/machine-learning)


### Marco Túlio Pires (mtrpires@)


# Week 1


## Supervised Learning

 

In Supervised Learning, you give the “right answers” to the algorithm. There is a relationship between input and output. The lesson talks about two types of problems:



*   **Regression Problem**: This is when you predict a continuous valued output. This means we are trying to map input variables to some continuous functions.
    *    We saw an example of house prices where the algorithm would try to predict the sell value based on the square-footage. 
    *   Given a picture of a person, we have to predict their age on the basis of the given picture.
*   **Classification Problem**: This problem refers to when you try to predict a discrete value output (zero or one, for example). We are trying to map input variables into discrete categories.
    *   We could have turned the house prices regression problem into a Classification Problem by making the output about whether the house sells for more or less than the asked price.
    *   Given a patient with a tumor, we have to predict whether the tumor is benign or malignant.
    *   There may be an **infinite number** of discrete values. In these cases, we there will be a mathematical tool to assist in the classification for the Support Vector Machine algorithm. 


## Unsupervised Learning

In Unsupervised Learning there are no labels in the dataset. We can approach problems with little or no idea what our results should look like. We can derive structure from data where we don’t necessarily know the effect of the variables. The algorithm may decide to group  the data into different segments or categories. There is no feedback based on prediction of the results. The lesson mentions two types of algorithms for Unsupervised Learning: the Clustering algorithm and the Cocktail Party algorithm.



*   **Clustering Algorithm**: This algorithm clusters data together into different groups or categories. It identifies patterns in the data and automatically creates the groups for further analysis. There are many applications for the Clustering Algorithm, such as:
    *   **Google News**: create clusters of articles that talk about similar topics or stories.
    *   **Genomics**: creates different types of individuals who manifest the same gene.
    *   **Social Networking**: creates cohesive groups of friends, who are likely to have stronger bonds or connections.
    *   **Market Segmentation**: in this case, the algorithm might discover how customers may organize themselves in different segmentation markets that were not seen before. This might allow selling or marketing more efficiently to this segment.
    *   **Astronomy**: the clustering algorithm is helping astronomers develop interesting theories about how galaxies are formed.
*   **Cocktail Party Algorithm**: This algorithm does not use clustering. Instead, it identifies different sources in the data provided and tries to separate them. It identifies structure in a chaotic environment. For example, to identify individual voices and music from a mesh of sounds at a cocktail party. 


## Model and Cost Function

For future reference x<sup>(i) </sup>will denote “input” variables, like the area of an apartment, also called “input features”. y<sup>(i)</sup> will denote the “output” or target variable that we’re trying to predict, for example, the price of a given apartment or house.

A pair (x<sup>(i)</sup>, <sup> </sup>y<sup>(i)</sup>) is called training example. The dataset that we will be using to learn from is called a training set. The dataset is a list of training examples noted (x<sup>(i)</sup>, <sup> </sup>y<sup>(i)</sup>); i = 1, …, m. The superscript has nothing to do with exponentiation. It is just an index to indicate the position in the dataset. X will also be used to denote the space of input values, and Y to denote the space of output values. For example, X = Y = ℝ.






![alt_text](images/Untitled-document0.png "image_tooltip")


If the target variable we’re trying to predict is continuous, such as in the example of predicting housing prices, we call the learning problem a “regression problem”. When y can take only a small number of discrete values, we call it a classification problem. For example, if we’d like to know whether the house was sold above or below the ask price.


## Cost Function

The **Cost Function** help us figure out the best possible straight line to our data. As mentioned before, the Hypothesis function has parameters called “thetas”. These are the parameters of the model. The Cost Function is used to measure the accuracy of our hypothesis function.

In linear regression, we have a training set that might describe a linear function, and we need to find the straight line that best describes the distribution of the data points. In other words, we need to find the theta zero and theta one that would give us a straight line function that best describes the distribution of our training set.

The Cost Function takes an average difference (actually, a fancier version of an average) of all the results of the hypothesis with inputs from x’s and the actual output y’s.






![alt_text](images/Untitled-document1.png "image_tooltip")


It is ½ x’, where x’ is the mean of the squares of the difference between the predicted value and the actual value. 

This function is called the “Squared error function”, or “Mean squared error”. The mean is halved by half as a convenience for the computation of the gradient descent, as the derivative term of the square function will cancel our the ½ term. The following image summarizes what the cost function does:






![alt_text](images/Untitled-document2.png "image_tooltip")



## Cost Function - Intuition I

The goal is to get the best possible line. The best possible line is such that the average squared vertical distances of the scattered points from the line will be the least (ideally zero). In the ideal case (where the distance is zero) our best possible line will pass through all the points of our training data set. In this case, the value of J(theta zero, theta one) will be zero. The following example shows the ideal situation where we have a cost function of 0. 






![alt_text](images/Untitled-document3.png "image_tooltip")


When theta one = 1, we get a slope of 1 which goes through every single data point in our model. When that value is 0.5, we see that the distance from our fit to the data points increase.






![alt_text](images/Untitled-document4.png "image_tooltip")


This increases the cost function to 0.58. Plotting several other points yields the following graph:






![alt_text](images/Untitled-document5.png "image_tooltip")


As a goal, we should try to minimize the cost function. In this case, our global minimum is 1. Notice that when we have 1 for the J(theta) function, the base of the parable hits zero in the vertical axis.


## Cost Function - Intuition II

A contour plot is a graph that contains many contour lines. A contour line of a two variable function has a constant value at all points of the same line. An example of such a graph is the one to the right below.






![alt_text](images/Untitled-document6.png "image_tooltip")


Taking any color and going along the 'circle', one would expect to get the same value of the cost function. For example, the three green points found on the green line above have the same value for J(theta zero, theta one) and as a result, they are found along the same line. The circled x displays the value of the cost function for the graph on the left when theta zero = 800 and theta one = -0.15. Taking another h(x) and plotting its contour plot, one gets the following graphs:


![alt_text](images/Untitled-document7.png "image_tooltip")


When theta zero = 360 and theta one = 0, the value of J(theta zero, theta one) in the countour plot gets closer to the center, thus reducing the cost function error. Now giving our hypothesis function a slightly positive slope results in a better fit of the data.


![alt_text](images/Untitled-document8.png "image_tooltip")


The graph above minimizes the cost function as much as possible and consequently, the result of θ<sub>1</sub> and θ<sub>0</sub> tend to be around 0.12 and 250 respectively. Plotting these values on our graph to the right seems to put our point in the center of the innermost 'circle'.


## Gradient Descent

So we have our hypothesis function and we have a way of measuring how well it fits into the data. Now we need to estimate the parameters in the hypothesis function. That's where gradient descent comes in.

Imagine that we graph our hypothesis function based on its fields θ<sub>0 </sub>and θ<sub>1</sub> (actually we are graphing the cost function as a function of the parameter estimates). We are not graphing x and y itself, but the parameter range of our hypothesis function and the cost resulting from selecting a particular set of parameters.

We put​	θ<sub>0</sub> on the x axis and θ<sub>1</sub> on the y axis, with the cost function on the vertical z axis. The points on our graph will be the result of the cost function using our hypothesis with those specific theta parameters. The graph below depicts such a setup.


![alt_text](images/Untitled-document9.png "image_tooltip")


We will know that we have succeeded when our cost function is at the very bottom of the pits in our graph, i.e. when its value is the minimum. The red arrows show the minimum points in the graph.

The way we do this is by taking the derivative (the tangential line to a function) of our cost function. The slope of the tangent is the derivative at that point and it will give us a direction to move towards. We make steps down the cost function in the direction with the steepest descent. The size of each step is determined by the parameter α, which is called the learning rate.

For example, the distance between each 'star' in the graph above represents a step determined by our parameter α. A smaller α would result in a smaller step and a larger α results in a larger step. The direction in which the step is taken is determined by the partial derivative of J(θ<sub>0</sub>,θ<sub>1</sub>). Depending on where one starts on the graph, one could end up at different points. The image above shows us two different starting points that end up in two different places.

The gradient descent algorithm is:

repeat until convergence:


![alt_text](images/Untitled-document10.png "image_tooltip")


where

j=0,1 represents the feature index number.

At each iteration j, one should simultaneously update the parameters θ<sub>1, </sub>θ<sub>2</sub>, …, θ<sub>n</sub>. Updating a specific parameter prior to calculating another one on the j<sup>(th)</sup> iteration would yield to a wrong implementation.


![alt_text](images/Untitled-document11.png "image_tooltip")



## Gradient Descent Intuition

In this lesson we learned that regardless of the slope sign for the derivative, theta 1 will eventually converge to its minimum value. Notice the values on the right and left side of the minimum point in the parable.


![alt_text](images/Untitled-document12.png "image_tooltip")


We should be mindful of the parameter alpha so that it doesn’t take a lot of time to compute (if alpha is too small) or it fails to converge or it can even diverge (if alpha is too big) -- this implies that our step size is wrong.


![alt_text](images/Untitled-document13.png "image_tooltip")


How does gradient descent converge with a fixed step size alpha?

As the derivative approaches zero, we approach the bottom of the convex function. At the minimum, the derivative will always be zero (as the tangent will have slope = 0). 

Θ<sub>1 </sub>:= θ<sub>1 </sub>- _α_ * - 0


![alt_text](images/Untitled-document14.png "image_tooltip")



## Gradient Descent for Linear Regression

When specifically applied to the case of linear regression, a new form of the gradient descent equation can be derived. We can substitute our actual cost function and our actual hypothesis function and modify the equation to:


![alt_text](images/Untitled-document15.png "image_tooltip")


where m is the size of the training set, θ<sub>0</sub> a constant that will be changing simultaneously with θ<sub>1</sub> and x<sub>i</sub>, y<sub>i</sub> are values of the given training set (data).

Note that we have separated out the two cases for θ<sub>j</sub> into separate equations for θ<sub>0</sub> and θ<sub>1</sub>; and that for θ<sub>1</sub> we are multiplying x<sub>i</sub> at the end due to the derivative. The following is a derivation of J(θ) for a single example :


![alt_text](images/Untitled-document16.png "image_tooltip")


The point of all this is that if we start with a guess for our hypothesis and then repeatedly apply these gradient descent equations, our hypothesis will become more and more accurate.

So, this is simply gradient descent on the original cost function J. This method looks at every example in the entire training set on every step, and is called **batch gradient descent**. Note that, while gradient descent can be susceptible to local minima in general, the optimization problem we have posed here for linear regression has only one global, and no other local optima; thus gradient descent always converges (assuming the learning rate α is not too large) to the global minimum. Indeed, J is a convex quadratic function. Here is an example of gradient descent as it is run to minimize a quadratic function.


![alt_text](images/Untitled-document17.png "image_tooltip")


The ellipses shown above are the contours of a quadratic function. Also shown is the trajectory taken by gradient descent, which was initialized at (48,30). The x’s in the figure (joined by straight lines) mark the successive values of θ that gradient descent went through as it converged to its minimum.


## Quiz


![alt_text](images/Untitled-document18.png "image_tooltip")

![alt_text](images/Untitled-document19.png "image_tooltip")
