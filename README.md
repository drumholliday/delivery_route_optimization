# Delivery Route Optimization

## Bellman-Ford Branch

This branch implements the **Bellman-Ford algorithm** for route optimization in a simulated delivery system. The purpose of this branch is to compare Bellman-Ford against other shortest-path approaches and demonstrate how it handles weighted graph data, including experimental negative edge weights.

## Overview

The project models a delivery network as a weighted graph. Delivery locations are represented as nodes, and routes between locations are represented as weighted edges. The Bellman-Ford algorithm is used to calculate the shortest path between delivery points and evaluate route costs.

This branch is useful for studying how Bellman-Ford behaves compared to algorithms such as Dijkstra's algorithm, especially when the graph includes negative edge weights for experimentation.

## Algorithm Used

### Bellman-Ford Algorithm

The Bellman-Ford algorithm is a shortest-path algorithm that calculates the minimum cost path from a starting node to all other nodes in a weighted graph.

Unlike Dijkstra's algorithm, Bellman-Ford can handle graphs with negative edge weights, as long as the graph does not contain a negative-weight cycle.

In this project, Bellman-Ford is used to:

* Evaluate possible delivery routes
* Calculate the lowest-cost path
* Handle experimental negative edge weights
* Compare shortest-path behavior against other routing algorithms
* Measure route calculation performance

## Dataset

The delivery network uses CSV files to simulate delivery routes, orders, and vehicles.

Some route weights may include negative values for learning and testing purposes. In a real delivery system, physical distances would not be negative. In this project, negative weights are used to represent experimental cost adjustments, such as:

* Return handling adjustments
* Wrong-delivery correction offsets
* Priority rerouting incentives
* Cost-based route modifications

This allows the Bellman-Ford implementation to demonstrate behavior that Dijkstra's algorithm is not designed to handle correctly.

## Functionality

This branch includes functionality to:

* Load delivery network data from CSV files
* Load delivery order data from CSV files
* Load delivery vehicle data from CSV files
* Build a weighted graph from the delivery network
* Calculate shortest paths using Bellman-Ford
* Assign routes based on calculated path cost
* Display route path, route cost, and execution time
* Support comparison with other algorithm branches

## Features

* Implements the Bellman-Ford shortest-path algorithm
* Supports weighted graph route optimization
* Handles experimental negative edge weights
* Loads input data from CSV files
* Calculates shortest paths for delivery simulation
* Measures route calculation execution time
* Prints path and cost results
* Provides a comparison branch for algorithm analysis

## Files in This Branch

```text
delivery_route_optimization/
├── bellman_ford.py
├── main.py
├── delivery_network.csv
├── delivery_orders.csv
└── delivery_vehicles.csv
```

### `bellman_ford.py`

Contains the core Bellman-Ford algorithm implementation.

### `main.py`

Runs the delivery route simulation, loads CSV data, calls the Bellman-Ford algorithm, and displays timing results.

### `delivery_network.csv`

Contains the simulated delivery route network, including locations and route weights.

### `delivery_orders.csv`

Contains delivery order information used by the simulation.

### `delivery_vehicles.csv`

Contains delivery vehicle information used by the simulation.

## How the Algorithm Works

Bellman-Ford works by repeatedly relaxing every edge in the graph.

The general process is:

1. Set the starting location distance to zero.
2. Set all other location distances to infinity.
3. Review every route in the graph.
4. Update a location's distance if a lower-cost path is found.
5. Repeat the relaxation process for the required number of passes.
6. Check for negative-weight cycles.
7. Return the shortest path and total route cost.

## Big O Complexity

### Time Complexity

```text
O(V × E)
```

Where:

* `V` is the number of vertices or locations
* `E` is the number of edges or routes

Bellman-Ford is generally slower than Dijkstra's algorithm, but it is more flexible because it can handle negative edge weights.

### Space Complexity

```text
O(V)
```

The algorithm stores distance values and path information for each vertex in the graph.

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

The program measures execution time for the Bellman-Ford route calculation. Timing output can be used to compare performance against other algorithm branches, such as the Dijkstra branch.

Example timing output may include:

```text
Shortest Path: A -> C -> D
Total Cost: 12
Execution Time: 0.00042 seconds
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

Implements Dijkstra's algorithm for shortest-path routing.

```text
bellman_ford_branch
```

Implements Bellman-Ford for shortest-path routing with support for experimental negative edge weights.

## Bellman-Ford vs. Dijkstra

Bellman-Ford and Dijkstra both solve shortest-path problems, but they are useful in different situations.

Bellman-Ford is useful when:

* The graph may contain negative edge weights
* Algorithm correctness with negative weights is important
* The project is comparing shortest-path approaches

Dijkstra is useful when:

* All edge weights are non-negative
* Faster performance is preferred
* The route network represents normal delivery distances or travel times

For most real-world delivery networks with only positive distances or travel times, Dijkstra is typically more efficient. Bellman-Ford is included in this project for comparison and to demonstrate support for negative edge-weight scenarios.

## Future Enhancements

Possible future improvements include:

* Add a frontend route visualization dashboard
* Add a map-based route display
* Add support for additional algorithms
* Compare execution times across multiple route networks
* Add automated tests for shortest-path correctness
* Add validation for negative-weight cycles
* Add database storage for delivery routes and orders
* Add a REST API for route calculations
* Add Docker support
* Add charts for algorithm performance comparison

## Academic and Portfolio Note

This project was created for learning and portfolio development. It demonstrates graph algorithms, shortest-path routing, CSV data processing, performance timing, and branch-based algorithm comparison.

## Author

Drum Holliday
