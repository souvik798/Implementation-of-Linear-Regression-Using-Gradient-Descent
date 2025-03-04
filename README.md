# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the standard libraries in python required for finding Gradient Design 
2. Read the dataset file and check any null value using .isnull() method.
3. Declare the default variables with respective values for linear regression.
4. Calculate the loss using Mean Square Error.
5. Predict the value of y.
6.Plot the graph respect to hours and scores using .scatterplot() method for Linear Regression.
7.Plot the graph respect to loss and iterations using .plot() method for Gradient Descent

## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: SOUVIK KUNDU
RegisterNumber: 212221230105

import numpy as np
import matplotlib.pyplot as plt
import pandas as pd

data=pd.read_csv("ex1.txt",header =None)

plt.scatter(data[0],data[1])
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City (10,000s)")
plt.ylabel("Profit ($10,000")
plt.title("Profit Prediction")

def computeCost(X,y,theta):

  m=len(y)
  h=X.dot(theta)
  square_err=(h-y)**2
  j=1/(2*m)* np.sum(square_err)
  return j

data_n=data.values
m=data_n[:,0].size
X=np.append(np.ones((m,1)),data_n[:,0].reshape(m,1),axis=1)
y=data_n[:,1].reshape(m,1)
theta=np.zeros((2,1))

computeCost(X,y,theta)

def gradientDescent(X,y,theta,alpha,num_iters):
  m=len(y)
  J_history=[]

  for i in range (num_iters):
    predictions=X.dot(theta)
    error = np.dot(X.transpose(),(predictions-y))
    descent=alpha*1/m * error
    theta-=descent
    J_history.append(computeCost(X,y,theta))

  return theta,J_history  

theta,J_history = gradientDescent(X,y,theta,0.01,1500)
print("h(x) ="+str(round(theta[0,0],2))+" + "+str(round(theta[1,0],2))+"x1" )

plt.plot(J_history)
plt.xlabel("Iteration")
plt.ylabel("$J(\Theta)$")
plt.title("Cost function using Grading Descent")

plt.scatter(data[0],data[1])
x_value=[x for x in range(25)]
y_value=[y*theta[1]+theta[0] for y in x_value]
plt.plot(x_value,y_value,color="r")
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City(10,000s)")
plt.ylabel("Profit ($10,000")
plt.title("Profit Prediction")

def predict (x,theta):
  predictions=np.dot(theta.transpose(),x)
  return predictions[0]

predict1=predict(np.array([1,3.5]),theta)*10000
print("For population = 35,000,we predict a profit a profit of $"+str(round(predict1,0)))

predict2=predict(np.array([1,7]),theta)*10000
print("For population =70,000,we predict a profit a profit of $"+str(round(predict2,0)))


*/
```

## Output:
# profit prediction graph:
![1](https://github.com/souvik798/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/94752764/25c4b296-e1eb-4332-8475-f7d5b7d82621)

# compute cost value
![2](https://github.com/souvik798/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/94752764/e68e4d39-9551-44d1-843b-f960bf7efcf7)

# h(x) value
![3](https://github.com/souvik798/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/94752764/4ad2d8da-8e9a-4a99-aab4-f7069dee31f2)

# Cost function using Gradient descent graph:
![4](https://github.com/souvik798/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/94752764/3365e19b-9bc3-42b1-98f8-0d08d15e209e)

# Profit prediction graph:
![5](https://github.com/souvik798/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/94752764/92e21d81-f3b1-465c-a967-a2f9c70f145c)

# profit of population 35,000:
![6](https://github.com/souvik798/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/94752764/075f3222-e2b6-4c57-93bc-f7e707a37633)

# profit of population 70,000:
![7](https://github.com/souvik798/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/94752764/099c3ad3-a48b-4192-9a30-ef7c5568d2fa)







## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
