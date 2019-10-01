# Extended Colored Traveling Salesperson (ECTSP)

ECTSP in its core is a variation of the classical Traveling Salesman Problem. ECTSP formulation includes multiple salespersons (salesman), limitation in the accessibility of cities to salespersons (colors), precedence constraints between cities, multiple source and destination depots (open TSP), and salespersons can be heterogeneous (different velocities, colors, etc.) 

### Mapping between Multi-Robot Task Allocation (MRTA) and ECTSP
In MRTA, cities and salespersons correspond to tasks and agents, respectively. A salesperson's colors map to an equipment type of an agent, e.g., camera, gripper, and different types of sensory equipment. Following the same rules, a color, which is associated with a task, indicates the required equipment, i.e., equipment an agent should have in order to successfully complete that task. In contrast to the classical TSP formulation, tasks are neither instantaneous nor have a predefined duration. The duration of a task is estimated based on the agent's capabilities. Moreover, equipment heterogeneity is not the sole determinant for the differences between the agents. Every agent may have a different {speed}, therefore the duration of task execution may depend on the selected agent. In addition to equipment requirements and duration, tasks may have an additional parameter, i.e., precedence constraints. Some tasks might need to be completed before or after some other task in a mission. Precedence constraints in ECTSP are essentially an ordering constraint. This means that interrelated tasks will be allocated to the same agent. It can be concluded that ECTSP has only intra-schedule dependencies. Although actions are durative, they are ordered, and no concurrent actions are possible. An illustration of the ECTSP can be seen in the image below.

![An illustration of ECTSP ](https://github.com/mdh-planner/ECTSP/blob/master/ECTSP_Illustration2.png)
## Benchmark instances for the ECTSP
10 Benchmark instances are randomly generated and provided for download. Each instance has 3 files (Cities, Depots, and Salespersons). 

City file consists of the information about cities and columns are organized as follows:

 1. ID of the city 0,1, ..., n;
 2. X coordinate [m];
 3. Y coordinate [m];
 4. City "duration" (E.g., Task duration) [s];
 5. Color required;
 6. Precedence, i.e., the ID of the city that needs to be visited after the city in the first column of that row

Depots file consists of the information about destination Depots and columns are organized as follows:

 1. ID of the depot;
 2. X coordinate [m];
 3. Y coordinate [m];

Salespersons file consists of the information about salespersons and columns are organized as follows:

 1. ID of the salesperson
 2. X coordinate of the location of the salesperson [m];
 3. Y coordinate of the location of the salesperson [m];
 4. Colors that salesperson has;
 5. Velocity of the salesperson [m/s]*;
 6. A source depot from which a salesperson starts**


*(Note that in these benchmarks, each salesperson has the same velocity).

**(Note that in these benchmarks, each salesperson starts from a different depot).

### Best known solutions
|Instance| Cost  |
|--|--|
| 0 |  79094.9* |
|1|98128.7*|
| 2 | 93944.3 |
|3|135250|
| 4 | 110024 |
|5|133621|
| 6 | 260920 |
|7|224962|
| 8 | 237912 |
|9|222007|

*(Known Optimal Solution)

## Objective Function

![Obj. Function](https://github.com/mdh-planner/ECTSP/blob/master/eq1.png)

Where w_1 = 1 and w_2 = 0.1 and:

![minMax](https://github.com/mdh-planner/ECTSP/blob/master/eq2.png)

and

![minSum](https://github.com/mdh-planner/ECTSP/blob/master/eq3.png)

# Contact
If you have a question, suggestion or you have a problem to report, please contact me via Email: branko.miloradovic@mdh.se
