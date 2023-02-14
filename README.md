# Optimisation Problem Python Project
- In this school project, the aim is to help a ficticious pizza chain restaurant that is facing problems inventory delivery planning and rising costs, to optimise the best delivery route.
- This was a team project and I contributed mainly in the vehicle routing problem.

## Data
As the pizza restaurant in question is a fictitious company, we do not have the actual data belonging to it. We used a Polish pizza restaurant’s order dataset (https://www.kaggle.com/janusznoszczynski/polish-pizza-restaurants-orders-history), which contains information about the amount of pizza sold from 2016 to 2018, as a basis for demand and generated our own 2020 demand dataset, with the demand separated by different outlets. This is to ensure that our fictitious dataset is representative of actual industry data.

In order to determine the distance from one location to another, we performed the calculation of the respective distance values on R. Since the computation of distance based on Euclidean geometry may give a false impression of the actual distance required to travel, the route distances were obtained based on Google’s Distance Matrix API with the help of the ggmap package in R.

## Vehicle Routing Problem
The Vehicle Routing Problem is one that seeks to design an optimal route for the vehicle(s) to a set of destinations given certain constraints. This model is commonly used to minimise the overall transportation cost.

In this problem, we aim to find the most optimal route for the delivery truck to deliver different kinds of pizzas to the different outlets given capacity, fuel constraints. There will also be a resource allocation problem that will be solved within the model as the different pizzas take up different capacities within the delivery truck.

### Mathematical Formulation
**Notations:**

𝑁 is the outlets, where 𝑁 = {1, 2, . . . , 𝑛}.

𝑉 is the set of nodes with  𝑉 = [0]∪ 𝑁.

𝐴 is the set of arcs, with 𝐴 = {(𝑖, 𝑗) ∈ 𝑉2: 𝑖 ≠ 𝑗}.

𝐶𝑖𝑗 is the distance to travel over the arc (𝑖, 𝑗) ∈ 𝐴

𝑄 is the capacity of the truck

𝐻 is the total travelling capacity of the truck.

𝑞𝑖 is the amount that has to be delivered to the customer, 𝑖 ∈ 𝑁

**Decision Variables:**

𝑥𝑖𝑗 is a binary variable taking value 1 if the vehicle travels from Node i to j. Otherwise, 𝑥𝑖𝑗 takes value 0.

𝑢𝑖 is the amount of pizza type 1 delivered after visiting vertex 𝑖.

𝑢2𝑖 is the amount of pizza type 2 delivered after visiting vertex 𝑖.

𝑢3𝑖 is the amount of pizza type 3 delivered after visiting vertex 𝑖.

𝑒𝑖 is the amount of distance covered by truck after visiting vertex 𝑖.

<img width="698" alt="image" src="https://user-images.githubusercontent.com/69724535/218639852-872382a5-18e5-451f-bcaa-dd9865c108b8.png">

In this formulation, the objective function seeks to minimize the total traveling distance covered by the delivery truck. Constraints (1) and (2) limit the truck to a single visit to each outlet. Constraints (3) to (9) are counting accumulated pizzas delivered to ensure that the number of pizzas delivered does not exceed the truck capacity. Constraints (3), (4), (9) are for hawaiian pizza flavour, (5), (6), (9) for pepperoni pizza flavour and (7), (8), (9) for cheesy pizza flavour. Constraint (9) limits the amount of pizzas the truck can carry according to capacity Q and the different pre-packed box sizes of different pizza types. Constraints (10), (11) and (12) are counting the distance traveled by the truck to ensure that the total distance covered does not exceed the travelling capacity. Finally, Constraint (13) limits x_ij to a binary variable.

### Conclusion and Limitations
- Refer to the jupyter notebook for optimal solution.
- The model assumes that the same transportation route is undertaken by the vehicles each time it goes from location i to j and traffic will not be a significant concern in affecting amount of fuel used.
- Fuel efficiency is assumed to be constant throughout despite the reduction in truck loads after each stop.
- It is assumed that the delivery truck can deliver all the goods in the same day.
