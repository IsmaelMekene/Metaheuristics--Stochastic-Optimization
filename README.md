# :card_index_dividers: Metaheuristics--Stochastic-Optimization
Application and illustration of a wide range optimization methods

<p align="center">
  <img src="https://miro.medium.com/max/1200/1*fpebFXB7TctmBvI0R7NXng.gif"/>
</p>

![gif](https://miro.medium.com/max/1200/1*fpebFXB7TctmBvI0R7NXng.gif)

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

### Subject

 Consider the following three optimization problems:
 
**- The Banana (Rosenbrock) Function**

This function is known as the “banana function” because of its shape; it is described
mathematically in Equation (1). In this problem, there are two design variables with lower and
upper limits of [-5, 5]. The Rosenbrock function has a known global minimum at [1, 1] with an
optimal function value of zero.

<a href="https://www.codecogs.com/eqnedit.php?latex=Minimize&space;f&space;(x)&space;=&space;100\left&space;(&space;x_{2}-x_{1}^{2}&space;\right&space;)^{2}&plus;\left&space;(&space;1-x_{1}&space;\right&space;)^{2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Minimize&space;f&space;(x)&space;=&space;100\left&space;(&space;x_{2}-x_{1}^{2}&space;\right&space;)^{2}&plus;\left&space;(&space;1-x_{1}&space;\right&space;)^{2}" title="Minimize f (x) = 100\left ( x_{2}-x_{1}^{2} \right )^{2}+\left ( 1-x_{1} \right )^{2}" /></a>   (1)

**- The Eggcrate Function**

This function is described mathematically in Equation (2). In this problem, there are two
design variables with lower and upper bounds of [-2π, 2π]. The Eggcrate function has a known
global minimum at [0, 0] with an optimal function value of zero.

<a href="https://www.codecogs.com/eqnedit.php?latex=Minimize&space;f&space;(&space;x&space;)&space;=&space;x_{1}^{2}&plus;x_{2}^{2}&plus;25\left&space;(&space;\sin&space;^{2}\left&space;(x_{1}&space;\right&space;)&space;&plus;(&space;\sin&space;^{2}\left&space;(x_{2}&space;\right&space;)\right&space;)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Minimize&space;f&space;(&space;x&space;)&space;=&space;x_{1}^{2}&plus;x_{2}^{2}&plus;25\left&space;(&space;\sin&space;^{2}\left&space;(x_{1}&space;\right&space;)&space;&plus;(&space;\sin&space;^{2}\left&space;(x_{2}&space;\right&space;)\right&space;)" title="Minimize f ( x ) = x_{1}^{2}+x_{2}^{2}+25\left ( \sin ^{2}\left (x_{1} \right ) +( \sin ^{2}\left (x_{2} \right )\right )" /></a>   (2)

**- Golinski’s Speed Reducer**

This hypothetical problem represents the design of a simple gearbox such as might be used in a
light airplane between the engine and propeller to allow each to rotate at its most efficient speed.
The gearbox is depicted in Figure and its seven design variables are labeled. The objective is
to minimize the speed reducer’s weight while satisfying the 11 constraints imposed by gear and
shaft design practices. A full problem description can be found in Reference [1]. A known
feasible solution obtained by a sequential quadratic programming (SQP) approach is a 2994.34
kg gearbox with the following values for the seven design variables: [3.5000 0.7000 17.0000
7.3000 7.7153 3.3502 5.2867 ].
This is a feasible solution with four active constraints, but is it an optimal solution?

![Golinski](https://www.researchgate.net/profile/Cenker_Aktemur2/publication/329715526/figure/fig1/AS:704855601582085@1545062079858/The-Speed-Reducer-labelled-with-the-Design-variables-4.png)
Figure: Golinski’s Speed Reducer with 7 design variables



Discuss the results and insights you get from numerically solving these three
nonlinear optimization problems.

### Solution

**- The Banana (Rosenbrock) Function**

![banana](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/images/banana.png)

In minimizing Rosenbrock function, the gradient descent approach (implemented in python) was used
within bounds [-4, 4]. In all cases, the global minimum was found within 6 significant digits (Minimum = 0).
This a feasible solution as we can observed on the python file, for each run the algorithm is converging
toward the global optimum

![bananagraph](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/images/banagraph.png)

**- The Eggcrate Function**

![eggcrate](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/images/eggcrate.png)

For eggcrate function, the same algorithm was employed and it was noticed that gradient- based
optimizer was stucked in the local optimum, depending on the starting point that were chosen
randomly within bounds [-2π, 2π].
Out of 10 runs, 9 were stucked in a local minima while 1 found the global optimum that is 0.
In this case we still have feasible solutions. Although the optimum at each run is feasible, it is still
unlikely to catch the global optimum.

![eggcrategraph](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/images/eggcrategraph.png)

**- Golinski’s Speed Reducer**

**SLSQP** – Sequential Least Squares Programming approach has been used for this optimization problem.

Finally the Golinski’s speed reducer problem was solved using sequential quadratic programming
approach (implemented in Python) that handles gradient-based constrained optimization
problems. This problem has 11 constraints, in addition to bound constraints and objective is to
minimize the weight of the speed reducer. The 10 starting points were picked at random as before
and the quickly optimizer converged to the optimum in all cases.

![goldinski](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/images/goldinskigraph.png)

see code [gradientDescent](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/model/Exercise%202_Metaheuristics.ipynb)

## 3. Non-linear Optimization & PSO - Particle Swarm Optimization approach

### Subject

Repeat the numerical experiments from exercise 2, but this time using a heuristic technique of your choice (e.g. SA, GA …). 
Explain how you “tuned” the heuristic algorithm. 

### Solution

As heuristic technique, we have used the **PSO - Particle Swarm Optimization** approach (See Python file).

see code [ParticleSwarmOptimization](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/model/Exercise%203_Metaheuristics.ipynb)

**- The Banana (Rosenbrock) Function**

![rosenPSO](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/images/rosenPSO.png)

**- The Eggcrate Function**

![eggPSO](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/images/eggPSO.png)

**- Golinski’s Speed Reducer**

![golinPSO](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/images/golinPSO.png)


**i. Dependence of answers on initial design vector (start point, initial population)**

| Problem Name | Gradient-Based Optimizer | Particle Swarm Otpimizer |
| :---: | :---: | :---: |
| Rosenbrock Function  | low | low |
| Eggcrate Function  | high | low |
| Golinski Speed Reducer  | low | low |

**ii. Computational effort (CPU time [sec] or FLOPS)** 

| Problem Name | Gradient-Based Optimizer | Particle Swarm Otpimizer |
| :---: | :---: | :---: |
| Rosenbrock Function  | 0.031 | 0.347 |
| Eggcrate Function  | 0.008 | 0.151 |
| Golinski Speed Reducer  | 0.117 | 17.43 |

**iii. Convergence history** 

| Problem Name | Gradient-Based Optimizer | Particle Swarm Otpimizer |
| :---: | :---: | :---: |
| Rosenbrock Function  | Always converged to global minimum. | Converged, but efficiency depends on the tuning parameters selected |
| Eggcrate Function  | Always converged, but either a local or a global minimum. | Converged, but efficiency depends on the tuning parameters selected|
| Golinski Speed Reducer  | Always converged to global minimum. | Converged, but efficiency depends on the tuning parameters selected |

**iv. Frequency at which the technique gets trapped in a local optimum**

| Problem Name | Gradient-Based Optimizer | Particle Swarm Otpimizer |
| :---: | :---: | :---: |
| Rosenbrock Function  | 0 | 0 |
| Eggcrate Function  | 0.9 | 0 |
| Golinski Speed Reducer  | 0 | 0 |

**v. Conclusion**

Gradient-based optimizers can get stuck in local optima and are sensitive to the starting point,
especially if there are multiple optima in the design space.

Genetic Algorithms are computationally expensive and requires considerable “tuning” effort,
especially for complex problems. 



see report [Report](https://github.com/IsmaelMekene/Metaheuristics--Stochastic-Optimization/blob/main/report/Metaheuristics_20203001-2-8.pdf)
