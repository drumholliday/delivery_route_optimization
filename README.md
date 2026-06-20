# Delivery Route Optimization

## Dijkstra Branch

This branch implements **Dijkstra's algorithm** for route optimization in a simulated delivery system. The purpose of this branch is to calculate efficient delivery routes using a shortest-path algorithm designed for weighted graphs with non-negative edge weights.

## Overview

The project models a delivery network as a weighted graph. Delivery locations are represented as nodes, and routes between locations are represented as weighted edges. Dijkstra's algorithm is used to calculate the lowest-cost route between delivery points.

This branch is useful for studying how Dijkstra's algorithm performs in a delivery route optimization problem where route distances, travel times, or costs are represented as positive values.

## Algorithm Used

### Dijkstra's Algorithm

Dijkstra's algorithm is a shortest-path algorithm that finds the minimum-cost path from a starting node to other nodes in a weighted graph.

The algorithm works best when all edge weights are non-negative. This makes it well suited for delivery route problems because real-world distances and travel times are normally positive values.

In this project, Dijkstra's algorithm is used to:

* Evaluate delivery routes
* Calculate the shortest path between locations
* Determine route cost
* Support delivery assignment logic
* Measure route calculation performance
* Compare shortest-path behavior against other algorithm branches

## Dataset

The delivery network uses CSV files to simulate delivery routes, orders, and vehicles.

The route network should use non-negative edge weights. These weights may represent:

* Distance between delivery locations
* Estimated travel time
* Route cost
* Delivery path weight

Because Dijkstra's algorithm assumes non-negative edge weights, this branch is best used with route data that does not contain negative values.

## Functionality

This branch includes functionality to:

* Load delivery network data from CSV files
* Load delivery order data from CSV files
* Load delivery vehicle data from CSV files
* Build a weighted graph from the delivery network
* Calculate shortest paths using Dijkstra's algorithm
* Assign routes based on calculated path cost
* Display route path, route cost, and execution time
* Support comparison with other algorithm branches

## Features

* Implements Dijkstra's shortest-path algorithm
* Supports weighted graph route optimization
* Uses non-negative route weights
* Loads input data from CSV files
* Calculates efficient delivery routes
* Measures route calculation execution time
* Prints path and cost results
* Provides a comparison branch for algorithm analysis

## Files in This Branch

```text
delivery_route_optimization/
├── dijkstra.py
├── main.py
├── delivery_network.csv
├── delivery_orders.csv
└── delivery_vehicles.csv
```

### `dijkstra.py`

Contains the core Dijkstra shortest-path algorithm implementation.

### `main.py`

Runs the delivery route simulation, loads CSV data, calls the Dijkstra algorithm, and displays route and timing results.

### `delivery_network.csv`

Contains the simulated delivery route network, including locations and route weights.

### `delivery_orders.csv`

Contains delivery order information used by the simulation.

### `delivery_vehicles.csv`

Contains delivery vehicle information used by the simulation.

## How the Algorithm Works

Dijkstra's algorithm works by repeatedly selecting the unvisited node with the lowest known distance from the starting location.

The general process is:

1. Set the starting location distance to zero.
2. Set all other location distances to infinity.
3. Select the unvisited location with the lowest current distance.
4. Check each neighboring location.
5. Update a neighbor's distance if a shorter path is found.
6. Mark the current location as visited.
7. Repeat until the destination is reached or all reachable locations are processed.
8. Return the shortest path and total route cost.

## Big O Complexity

### Time Complexity

The time complexity depends on the implementation.

For a basic implementation using repeated scanning, the time complexity is commonly:

```text
O(V²)
```

For an implementation using a priority queue, the time complexity is commonly:

```text
O((V + E) log V)
```

Where:

* `V` is the number of vertices or locations
* `E` is the number of edges or routes

### Space Complexity

```text
O(V)
```

The algorithm stores distance values, visited locations, and path information for each vertex in the graph.

## Running the Project

From the project root directory, run:

```bash
python main.py
```

Depending on your Python environment, you may need to use:

```bash
python3 main.py
```

## Timing Test

The program measures execution time for the Dijkstra route calculation. Timing output can be used to compare performance against other algorithm branches, such as the Bellman-Ford branch.

Example timing output may include:

```text
Shortest Path: A -> C -> D
Total Cost: 12
Execution Time: 0.00018 seconds
```

Actual results will depend on the CSV data and route network used during the test.

## Branch Comparison

This repository includes separate branches for different shortest-path algorithm implementations.

```text
main
```

Primary stable branch.

```text
dijkstra_branch
```

Implements Dijkstra's algorithm for shortest-path routing with non-negative route weights.

```text
bellman_ford_branch
```

Implements Bellman-Ford for shortest-path routing with support for experimental negative edge weights.

## Dijkstra vs. Bellman-Ford

Dijkstra and Bellman-Ford both solve shortest-path problems, but they are useful in different situations.

Dijkstra is useful when:

* All edge weights are non-negative
* Faster performance is preferred
* The route network represents normal delivery distances, travel times, or costs
* The graph does not require support for negative edge weights

Bellman-Ford is useful when:

* The graph may contain negative edge weights
* Correctness with negative weights is required
* Algorithm comparison is the primary goal
* Slower performance is acceptable for the sake of flexibility

For most real-world delivery route systems, Dijkstra's algorithm is typically the better fit because distances and travel times are non-negative and performance is usually important.

## Future Enhancements

Possible future improvements include:

* Add a frontend route visualization dashboard
* Add a map-based route display
* Add support for additional routing algorithms
* Compare execution times across multiple route networks
* Add automated tests for shortest-path correctness
* Add input validation for CSV files
* Add database storage for delivery routes and orders
* Add a REST API for route calculations
* Add Docker support
* Add charts for algorithm performance comparison

## Academic and Portfolio Note

This project was created for learning and portfolio development. It demonstrates graph algorithms, shortest-path routing, CSV data processing, performance timing, and branch-based algorithm comparison.

## Author

Drum Holliday
