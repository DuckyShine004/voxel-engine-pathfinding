# voxel-engine-pathfinding

# Overview
This project evaluates and compares three pathfinding algorithms for traversing 3D voxel-based environments. The goal is to determine which algorithm performs best under different spatial conditions. The algorithms tested are:
1. A*
2. Theta*
3. Lazy Theta*

The agent is a cuboid-shaped entity affected by gravity, occupying a volume of 2 voxels in height and 1 voxel in both width and depth. It is assigned a target location and attempts to navigate toward it. If a valid path exists, the agent actively tracks and moves to the target; otherwise, it remains idle.

# Testing

## Test Conditions
The following environment types will be used to evaluate the algorithms:
1. Sparse voxel grid
2. Dense voxel grid
3. Sparse/Dense maze traversal
4. Sparse/Dense height traversal

The voxel count range for each condition will be defined in future stages of the project.

## Evaluation Metrics
Each algorithm will be assessed using the following performance metrics:
- **Accuracy:** Whether the agent successfully finds and reaches the target
- **Solution Efficiency:** Time taken to compute a valid path to the target, excluding traversal time
- **Overall Efficiency:** The total time required for the agent to reach the target, assuming a valid path exists

## Test Environment
To maintain fairness and consistency across all test cases, the following parameters must remain constant for every algorithm run:
- Total number of voxels in the environment
- Agent's initial position
- Target's position
- Fixed frame rate, to eliminate performance variation across different hardware

# Optimisations
While all algorithms perform adequately in sparse voxel grids, performance may degrade in dense grids. Therefore, to improve efficiency, the following optimisations will be considered for this project:
- Testing alternative cost functions, sepcifically, the heuristic cost function `h(x)`
- Using an octree to reduce the search space and improve traversal efficiency
