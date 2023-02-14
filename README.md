# Optimisation Problem Python Project

Notations:
𝑁 is the outlets, where 𝑁 = {1, 2, . . . , 𝑛}
is the set of nodes with 𝑉 𝑉 = [0]∪ 𝑁
is the set of arcs, with 𝐴 𝐴 = {(𝑖, 𝑗) ∈ 𝑉2: 𝑖 ≠ 𝑗}
is the distance to travel over the arc 𝐶𝑖𝑗 (𝑖, 𝑗) ∈ 𝐴
is the capacity of the truck 𝑄
is the total travelling capacity of the truck 𝐻
is the amount that has to be delivered to the customer, 𝑞𝑖 𝑖 ∈ 𝑁
Decision Variables:
is a binary variable taking value 1 if the vehicle travels from Node i to j. Otherwise, 𝑥𝑖𝑗 𝑥𝑖𝑗
takes value 0
The amount of pizza type 1 delivered after visiting vertex 𝑢𝑖 𝑖
The amount of pizza type 2 delivered after visiting vertex 𝑢2𝑖 𝑖
The amount of pizza type 3 delivered after visiting vertex 𝑢3𝑖 𝑖
The amount of distance covered by truck after visiting vertex 𝑒𝑖 𝑖
Objective min
𝑖,𝑗∈𝐴
Σ 𝑐𝑖𝑗𝑥𝑖𝑗
Subject to
(1)
𝑗∈𝑉 𝑗≠𝑖
Σ 𝑥𝑖𝑗 = 1 𝑖 ∈ 𝑁
(2)
𝑖∈𝑉 𝑖≠𝑗
Σ 𝑥𝑖𝑗 = 1 𝑗 ∈ 𝑁
𝑖𝑓 𝑥 (3) 𝑖𝑗 = 1 ⇒ 𝑢𝑖 + 𝑞𝑗 = 𝑢𝑗 𝑖, 𝑗 ∈ 𝐴: 𝑗 ≠ 0, 𝑖 ≠ 0
𝑢 (4) 𝑖 ≥ 𝑞𝑖 𝑖 ∈ 𝑁
𝑖𝑓 𝑥 (5) 𝑖𝑗 = 1 ⇒ 𝑢2𝑖 + 𝑞2𝑗 = 𝑢2𝑗 𝑖, 𝑗 ∈ 𝐴: 𝑗 ≠ 0, 𝑖 ≠ 0
𝑢2 (6) 𝑖 ≥ 𝑞2𝑖 𝑖 ∈ 𝑁
𝑖𝑓 𝑥 (7) 𝑖𝑗 = 1 ⇒ 𝑢3𝑖 + 𝑞3𝑗 = 𝑢3𝑗 𝑖, 𝑗 ∈ 𝐴: 𝑗 ≠ 0, 𝑖 ≠ 0
𝑢3 (8) 𝑖 ≥ 𝑞3𝑖 𝑖 ∈ 𝑁
3500𝑢 (9) 𝑖 + 2800𝑢2𝑖 + 2450𝑢3𝑖 ≤ 𝑄 𝑖 ∈ 𝑁
𝑖𝑓 𝑥 (10) 𝑖𝑗 = 1 ⇒ 𝑒𝑖 + 𝑐𝑖𝑗 = 𝑒𝑗 𝑖, 𝑗 ∈ 𝐴: 𝑗 ≠ 0, 𝑖 ≠ 0
𝑒 (11) 𝑖 ≥ 𝑐𝑖𝑗 𝑖 ∈ 𝑁, 𝑖, 𝑗 ∈ 𝐴
𝑒 (12) 𝑖 ≤ 𝐻 𝑖 ∈ 𝑁
𝑥 (13) 𝑖𝑗 ∈ {0, 1} 𝑖, 𝑗 ∈ 𝐴
14
In this formulation, the objective function seeks to minimize the total traveling distance
covered by the delivery truck. Constraints (1) and (2) limit the truck to a single visit to each
outlet.
