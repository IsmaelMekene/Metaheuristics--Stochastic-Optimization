# Metaheuristics--Stochastic-Optimization
Application and illustration of a wide range optimization methods

## 1. Continuous Optimization & Sensitivity Analysis 

### Subject

This problem is to use sensitivity analysis on revenue management for a very simplified airline
pricing model. We will assume that an airline has one flight per day from Boston to Atlanta and
they use an airplane that seats 150 people. The airline wishes to determine three prices, pi
(i=1,2,3), one for seats in each of the three fare buckets it will use. The fare buckets are designed
to maximize revenue by separating travelers into groups, for instance 14 days advance purchase,
leisure travelers, and business travelers. The airline models demand for seats in each group
using the formula:

<a href="https://www.codecogs.com/eqnedit.php?latex=Di&space;=&space;Ai\times&space;\exp&space;\left&space;[&space;-\frac{1}{Ai}&space;\times&space;Pi\right&space;]" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Di&space;=&space;Ai\times&space;\exp&space;\left&space;[&space;-\frac{1}{Ai}&space;\times&space;Pi\right&space;]" title="Di = Ai\times \exp \left [ -\frac{1}{Ai} \times Pi\right ]" /></a>

Where Di is the people that want to fly given price pi, the remaining parameters are a1=100,
a2=150, and a3=300. Please note, for simplicity you may assume that each Di is a
continuous variable.
(a) Formulate the revenue maximization problem for this flight as an optimization problem.
(b) What are the optimal prices and how many people are expected to buy a ticket in
each fare bucket?
(c) Using sensitivity analysis, if the airline were to squeeze three additional seats onto this
flight,
a. How much do you expect revenue to change?
b. By how much should the airline change each price?

### Solution

 a) Revenue Maximisation Problem using the Simplex Method

 Formulation as an optimization problem:
 Min [ - ((a1×exp(-p1/a1)) + (a2×exp(-p2/a2)) +(a3×exp(-p3/a3))]

Under the following constraints:
- D1= a1×exp(-p1/a1)
- D2= a2×exp(-p2/a2)
- D3= a3×exp(-p3/a3)

 ![graph](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/images/graph.png)
 
 b) see code [continuousOptimization](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/model/Exercise1_Metaheuristics.ipynb)
 
 c) see code [sensitivityAnalysis](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/model/Exercise1_Metaheuristics.ipynb)





## 2. Non-linear Optimization & Gradient Descent

### Subject*

 Consider the following three optimization problems:
 
The Banana (Rosenbrock) Function
This function is known as the “banana function” because of its shape; it is described
mathematically in Equation (1). In this problem, there are two design variables with lower and
upper limits of [-5, 5]. The Rosenbrock function has a known global minimum at [1, 1] with an
optimal function value of zero.

<a href="https://www.codecogs.com/eqnedit.php?latex=Minimize&space;f&space;(x)&space;=&space;100\left&space;(&space;x_{2}-x_{1}^{2}&space;\right&space;)^{2}&plus;\left&space;(&space;1-x_{1}&space;\right&space;)^{2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Minimize&space;f&space;(x)&space;=&space;100\left&space;(&space;x_{2}-x_{1}^{2}&space;\right&space;)^{2}&plus;\left&space;(&space;1-x_{1}&space;\right&space;)^{2}" title="Minimize f (x) = 100\left ( x_{2}-x_{1}^{2} \right )^{2}+\left ( 1-x_{1} \right )^{2}" /></a>   (1)



## 3. Non-linear Optimization & PSO - Particle Swarm Optimization approach
