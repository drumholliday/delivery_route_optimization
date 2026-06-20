# Delivery Dispatch Optimization

## Main Branch

This project simulates a package delivery dispatch system using graph-based routing concepts. It demonstrates how delivery networks can be modeled with locations, routes, vehicles, and customer orders in preparation for shortest-path algorithm testing.

The `main` branch serves as the base version of the project. Algorithm-specific implementations are maintained in separate branches.

## Overview

The project models a delivery network as a weighted graph. Delivery addresses are represented as nodes, and the routes between addresses are represented as weighted edges. The system loads delivery data from CSV files and provides a foundation for comparing route optimization algorithms such as Dijkstra's algorithm and Bellman-Ford.

This branch focuses on the shared project structure, data loading, and baseline dispatch setup.

## Purpose

The purpose of the `main` branch is to provide the core setup for the delivery dispatch simulation.

It includes:

* The base project structure
* CSV files for the delivery network, vehicles, and orders
* A `main.py` file for loading and verifying data
* Shared data used by the algorithm branches
* A starting point for route optimization experiments

## Features

* Loads delivery network data from CSV files
* Loads delivery order data from CSV files
* Loads delivery vehicle data from CSV files
* Provides a base structure for route optimization
* Supports branch-based algorithm comparison
* Models delivery locations as a graph
* Allows future comparison of shortest-path algorithms
* Provides a foundation for timing and performance analysis

## Dataset Overview

The project uses CSV files to simulate a delivery network, delivery orders, and delivery vehicles.

The dataset may include:

* Delivery locations
* Route distances or route costs
* Delivery orders
* Vehicle information
* Starting locations for vehicles
* Delivery constraints or timing information

Some experimental route weights may include negative values for algorithm comparison. In a real delivery system, physical distances would not be negative. In this project, negative weights can be used to represent cost adjustments, rerouting incentives, returns, or correction scenarios.

Negative weights are mainly useful for testing the Bellman-Ford branch. Dijkstra's algorithm assumes non-negative edge weights and should be used with data that does not contain negative route values.

## Files in This Branch

```text
delivery_route_optimization/
├── main.py
├── delivery_network.csv
├── delivery_orders.csv
└── delivery_vehicles.csv
```

### `main.py`

Entry point for the base project. This file loads and verifies the delivery data used by the simulation.

### `delivery_network.csv`

Contains the graph representation of the delivery network, including locations and route weights.

### `delivery_orders.csv`

Contains delivery order information, including delivery destinations and any related order details.

### `delivery_vehicles.csv`

Contains delivery vehicle information, including vehicle identifiers and starting locations.

## Branch Structure

This repository uses separate branches to compare different shortest-path algorithm implementations.

### `main`

The base branch containing the shared project structure and CSV data.

### `dijkstra_branch`

Implements Dijkstra's algorithm for delivery route optimization.

Dijkstra's algorithm is best suited for graphs with non-negative edge weights, such as normal distances, travel times, or route costs.

### `bellman_ford_branch`

Implements the Bellman-Ford algorithm for delivery route optimization.

Bellman-Ford can handle negative edge weights as long as there are no negative-weight cycles, making it useful for comparison and experimentation.

## Algorithm Implementations

The main branch does not contain the final algorithm comparison logic. Instead, each algorithm is implemented in its own branch so the behavior, performance, and structure of each approach can be evaluated separately.

| Branch                | Algorithm              | Purpose                                                              |
| --------------------- | ---------------------- | -------------------------------------------------------------------- |
| `main`                | Base setup             | Shared structure and data loading                                    |
| `dijkstra_branch`     | Dijkstra's algorithm   | Fast shortest-path routing for non-negative weights                  |
| `bellman_ford_branch` | Bellman-Ford algorithm | Shortest-path routing with support for experimental negative weights |

## How the System Works

The base project follows this general process:

1. Load delivery network data from `delivery_network.csv`.
2. Load delivery order data from `delivery_orders.csv`.
3. Load delivery vehicle data from `delivery_vehicles.csv`.
4. Verify that the input data is available and structured correctly.
5. Provide the data foundation used by the algorithm branches.
6. Allow each algorithm branch to calculate route paths, route costs, and timing metrics.

## Running the Project

From the project root directory, run:

```bash
python main.py
```

Depending on your Python environment, you may need to use:

```bash
python3 main.py
```

## Expected Output

The base branch is intended to verify that the project data loads correctly. Output may include information such as:

* Loaded delivery network records
* Loaded delivery orders
* Loaded delivery vehicles
* Basic confirmation that the simulation data is ready for use

Algorithm-specific route results and timing metrics are handled in the `dijkstra_branch` and `bellman_ford_branch`.

## Timing Metrics

Timing and performance measurements are maintained in the algorithm-specific branches.

The purpose of the timing metrics is to compare:

* Route calculation speed
* Algorithm performance
* Behavior with different graph data
* Suitability of each algorithm for delivery route optimization

## Screenshots

Screenshots may be added later to show:

* Data loading output
* Algorithm test results
* Timing comparisons
* Future route visualization screens

## Future Enhancements

Possible future improvements include:

* Add a frontend dashboard for route visualization
* Add map-based delivery route display
* Add support for additional algorithms
* Add automated tests for CSV loading and route calculations
* Add validation for input data
* Add performance comparison charts
* Add database storage for delivery orders and vehicles
* Add a REST API for route calculations
* Add Docker support
* Add a full-stack version with a web interface

## Academic and Portfolio Note

This project was created for learning and portfolio development. It demonstrates graph-based data modeling, CSV file processing, delivery route simulation, and branch-based comparison of shortest-path algorithms.

## Author

Drum Holliday
