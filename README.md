# SPLITZI - Cash Flow Application

#### Objective
Our aim is to develop a platform which uses an algorithm to restructure cash transactions within groups of people. The algorithm does not aim to change the total amount that any of the participants owes, but it makes it easier to pay people back by minimizing the total number of transactions.

#### Algorithm
The problem statement in technical terms we were dealing with is stated as, given a Directed Graph representing transaction, change (if needed) the weights on the existing edges without introducing newer ones. The algorithm that we have developed aligned to the given problem statement is described below,

1. Feed the debts in the form of a directed graph (let's represent it by G) to the algorithm.
2. Select one of the non-visited edges, say (u, v) from the directed graph G.
3. Now with u as source and v as sink, run a maxflow algorithm (possibly Dinic’s maxflow algorithm, since it’s one of the optimal implementations) to determine the maximum flow of money possible from u to v.
4. Also, compute the Residual Graph (let's represent it by G'), which indicates the additional possible flow of debts in the input graph after removing the flow of debts between u and v.
5. If maximum flow between u and v (let’s represent it by max-flow) is greater than zero, then add an edge (u, v) with weight as max-flow to the Residual Graph.
6. Now go back to Step 1 and feed it the Residual Graph G’.
7. Once all the edges are visited, the Residual Graph G’ obtained in the final iteration will be the one that has the minimum number of edges(i.e. transactions).

It outputs the final sequence of transactions to be made after simplifying debts. The algorithm has a complexity of O(V²E²), where V is the number of vertices in the graph and E is the number of edges in the graph. Here, O(V²E) is the complexity of the Dinic's implementation of the Maximum flow Problem and the extra O(E) is due to the algorithm iterating over all the edges in the graph.

#### Project Screenshots
|   | Screenshot |
| :------------: | :------------: |
| Landing Page | ![image](https://user-images.githubusercontent.com/55807508/142859819-30ef4741-12b0-48ec-93ac-410f8ba26ef4.png) |
| After Generating Solution | ![image](https://user-images.githubusercontent.com/55807508/142859711-8dc1edce-b9f1-4aa3-8f6f-dc2bbfc77a55.png) |
| About Splitzi Screen | ![image](https://user-images.githubusercontent.com/55807508/142859762-af361db1-40a3-4932-ac0a-5f0e3c4e73fd.png) |
