# Metaheuristics--Stochastic-Optimization
Application and illustration of a wide range optimization methods

## 1. Continuous Optimization & Sensitivity Analysis 


This problem is to use sensitivity analysis on revenue management for a very simplified airline
pricing model. We will assume that an airline has one flight per day from Boston to Atlanta and
they use an airplane that seats 150 people. The airline wishes to determine three prices, pi
(i=1,2,3), one for seats in each of the three fare buckets it will use. The fare buckets are designed
to maximize revenue by separating travelers into groups, for instance 14 days advance purchase,
leisure travelers, and business travelers. The airline models demand for seats in each group
using the formula:

- <img src="https://latex.codecogs.com/gif.latex?\[Di = Ai\times \exp \left [ -\frac{1}{Ai} \times Pi\right ]\]
" />

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



## 2. Non-linear Optimization & Gradient Descent




## 3. Non-linear Optimization & PSO - Particle Swarm Optimization approach
