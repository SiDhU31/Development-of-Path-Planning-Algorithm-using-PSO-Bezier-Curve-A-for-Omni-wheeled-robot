# Development-of-Path-Planning-Algorithm-using-PSO-Bezier-Curve-A-for-Omni-wheeled-robot
This work optimizes motion planning for a omni-directional robot in a grid-based environment. A* generates an initial obstacle-free path, Bézier curves smoothen the trajectory, and PSO optimizes control points and velocity profiles to minimize travel time and enhance maneuverability.This approach ensures smoother, more efficient navigation, reducing energy consumption and improving real-world applicability in autonomous robotics.
Here is a draft for a GitHub repository README based on the optimization review PDF you provided. It summarizes the project, methodology, implementation, results, and future work clearly for a GitHub audience.

***

# Path Planning Optimization for Omni-Wheeled Robot

This project develops an optimized path planning algorithm for a 3-wheeled omni-directional robot navigating a grid-based environment by combining the A* algorithm, Bézier curve smoothing, and Particle Swarm Optimization (PSO).

***

## Project Overview

- **Goal:** Generate smooth, efficient, and obstacle-free trajectories for an omni-wheeled robot in a grid environment.
- **Approach:** 
  1. Generate initial shortest path using A* algorithm.
  2. Smooth path using Bézier curves to reduce sharp turns.
  3. Optimize Bézier control points and velocity profiles with PSO to minimize travel time and path curvature while avoiding obstacles.

***

## Key Components

### A* Algorithm
- Generates initial obstacle-free paths on grid maps.
- Cost function balances cost from start node and heuristic to goal.

### Bézier Curves
- Parametric curves defined by control points smoothing the A* path.
- Ensures continuous and smooth robot trajectories.

### Particle Swarm Optimization (PSO)
- Optimizes control points of Bézier curve to minimize path length and curvature.
- Uses swarm intelligence with particles updating positions based on personal and global best fitness.
- Fitness accounts for path length and obstacle clearance penalties.

***

## Mathematical Model

- Objective function combines travel distance and curvature with weighting factors.
- Constraints include workspace boundary, obstacle avoidance, start/end points, and proximity margins.
- Bézier curve formula:  
  $$
  B(t) = \sum_{i=0}^n \binom{n}{i} (1 - t)^{n-i} t^i P_i
  $$
- PSO update equations for velocity and position ensure convergence to optimal control points within constraints.

***

## Implementation Details

- Environment represented as a 2D occupancy grid map.
- PSO parameters: swarm size 30, iterations 100-500, inertia weight 0.4, cognitive coefficient 2, social coefficient 1.5.
- PSO ensures start and end control points remain fixed.
- Functions implemented for:
  - A* search for initial path.
  - Bézier curve generation and smoothing.
  - PSO optimization with collision penalties.
  - Metrics calculation (path length, smoothness, computation time).

***

## Results

| Metric          | A* Path | Bézier Path | PSO Path   |
|-----------------|---------|-------------|------------|
| Path Length     | 152.02  | 144.47      | 140.90     |
| Path Smoothness | 3.19    | 4.35        | 2.02       |
| Computation Time| 0.01    | 0.00        | 30.88      |
| Number of Nodes | 129     | 100         | 100        |

- PSO paths achieved the shortest and smoothest trajectories.
- PSO outperformed A* and Bézier alone in 100/100 test runs.
- Visualization includes grid maps with paths and obstacle representations.

***

## How to Use

1. Clone the repository.
2. Prepare a grid map and define obstacles.
3. Run A* to get initial path.
4. Apply Bézier curve smoothing.
5. Optimize with PSO using provided scripts.
6. Visualize results with matplotlib.

***

## Future Work

- Extend algorithm for dynamic environments with moving obstacles.
- Integrate real-time replanning for adaptive navigation.
- Publish detailed methodology and results in peer-reviewed journals.

***
![![WhatsApp Image 2025-10-07 at 21 20 39_4cead8cd](https://github.com/user-attachments/assets/e8849102-fef3-4f20-985c-8a686500e566)
![WhatsApp Image 2025-10-07 at 21 20 38_a5c92784](https://github.com/user-attachments/assets/7cc6f052-74a2-47ed-83a0-06d03f35f18c)
![WhatsApp Image 2025-10-07 at 21 20 38_839951b4](https://github.com/user-attachments/assets/2490850e-871a-402a-bdd6-338e6da8de79)
![WhatsApp Image 2025-10-07 at 21 20 37_8c86d5a5](https://github.com/user-attachments/assets/0966d8bb-c47e-4bc5-994a-e44401a6b78b)
