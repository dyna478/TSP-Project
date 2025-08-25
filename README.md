This project provides a comprehensive, object-oriented Python toolkit for solving the Traveling Salesman Problem (TSP). It implements a wide range of algorithms, from classic heuristics and approximation algorithms to advanced metaheuristics and an optimal dynamic programming solver for small instances.

The TSPSolver class is a self-contained framework designed for experimentation, benchmarking, and visualization, making it an excellent tool for both academic and practical exploration of TSP solutions.

![Image](https://github.com/user-attachments/assets/706053a8-113a-4bc0-ac0f-51d5aac188ff)

Core Features

This solver is not a single pipeline but a collection of powerful, independent, and combinable TSP algorithms:

1. Construction Heuristics:

Nearest Neighbor: A fast, greedy heuristic for generating a baseline tour.

Multi-Start Nearest Neighbor: Improves upon the basic NN by running it from multiple random start points to avoid being trapped by a poor initial choice.

2. Approximation Algorithm:

Christofides Algorithm: A well-known 1.5-approximation algorithm for metric TSPs. The implementation includes all necessary components:

Minimum Spanning Tree (MST) via Prim's algorithm.

Minimum Weight Perfect Matching on odd-degree vertices (using a fast greedy approach).

Eulerian circuit finding and conversion to a Hamiltonian tour.

3. Metaheuristic Solvers:

Simulated Annealing (SA): An advanced metaheuristic that intelligently explores the solution space to escape local optima, inspired by the annealing process in metallurgy.

Genetic Algorithm (GA): A population-based solver that evolves solutions over generations using selection (tournament), crossover (Order Crossover - OX), and mutation.

4. Local Search / Improvement Heuristics:

2-Opt: An effective and widely used algorithm for removing simple edge crossings in a tour.

3-Opt: A more powerful (and computationally intensive) version of k-opt that considers swapping three edges to find better tour configurations.

5. Decomposition Strategy:

K-Means Clustering: A "divide-and-conquer" approach that partitions cities into clusters, solves each cluster's sub-problem (using optimal or strong heuristic methods), and merges the results with an advanced, cost-aware insertion heuristic.

6. Optimal Solver (for small instances):

Held-Karp Dynamic Programming: An exact, optimal solver for small TSP instances (typically N ≤ 12-15). This is used within the clustering approach for small clusters and can be called directly.

7. Comprehensive Solver & Benchmarking:

solve_comprehensive(): A master method that intelligently runs a portfolio of algorithms within a given time limit, applying local search improvements and returning the best solution found.

Built-in Benchmarking: The script includes a robust framework to benchmark multiple algorithms against each other on various problem instances (e.g., berlin52, random, clustered, circular).

Rich Visualization: A visualize_tour method generates clear, annotated plots of the final tour, including city labels and the start/end point.

