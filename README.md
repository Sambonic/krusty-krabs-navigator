# Krusty Krabs Navigator

The customers dropped their money and went on a rampage to find who stole it. This is the theme of this project where we designed an intelligent robot agent inspired by Mr. Krabs from SpongeBob SquarePants that collects money dropped by customers at the Krusty Krab restaurant. Mr.Krabs and his robot clone need to gather the money quickly before the angry customers find him. To achieve this, our agents map their environments, implement key AI path-planning algorithms, and account for dynamic rerouting, obstacle avoidance, and multi-agent coordination. 

#### Last Updated: December 23rd, 2024
## Table of Contents

1. [Introduction](#introduction)
2. [Objectives](#objectives)
3. [Environment Design](#environment-design)
4. [Design Approach](#design-approach)
5. [Implementation Details](#implementation-details)
6. [Challenges and Solutions](#challenges-and-solutions)
7. [Testing and Results](#testing-and-results)
8. [Installation](#installation)

## Introduction

This project simulates Mr. Krabs and his robot clone collecting money in the Krusty Krab restaurant while avoiding angry customers. The agents must map their environment, implement path-planning algorithms, and coordinate to efficiently gather the money while avoiding dynamic obstacles.

## Objectives

- Implement inverse range sensor algorithm for environment mapping
- Develop dynamic navigation using A* and Dijkstra's algorithms
- Handle real-time dynamic obstacle avoidance
- Create inter-agent communication protocol for task coordination
- Implement value-based prioritization for target collection

## Environment Design

The environment is designed as a lore-accurate replica of the Krusty Krabs restaurant, featuring:
- Custom-designed assets using Ibis Paint X
- Dynamic obstacles (angry customers)
- Static obstacles (tables, chairs, walls)
- Environment dimensions: 2616 × 1816 pixels (scaled by 2.2)
- Cell-based grid system for navigation

## Design Approach

### 1. Mapping

![Env during mapping](https://github.com/Sambonic/krusty-krabs-navigator/blob/main/images/misc/mapping_stage.PNG)

- 2D occupancy grid representation
- Inverse sensor model for probability calculation
- Real-time grid updates based on robot sensing
- Visual feedback of explored areas and obstacles

### 2. Path Planning Algorithms

![Env after mapping](https://github.com/Sambonic/krusty-krabs-navigator/blob/main/images/misc/running_stage.PNG)

#### A* Algorithm
- Heuristic-based pathfinding
- Dynamic obstacle avoidance capabilities
- Priority queue implementation for path exploration
- Real-time path recalculation

#### Dijkstra's Algorithm
- Complete path search implementation
- Cost-based path optimization
- Dynamic environment handling
- Obstacle avoidance integration

### 3. Obstacle Avoidance
- Dynamic obstacle movement patterns with 90-degree rotations
- Random direction changes for unpredictability
- Static obstacle detection and avoidance
- Agent sensing with configured maximum range

### 4. Task Management
- Priority-based target assignment
- Cost-based path optimization
- Multi-agent workload distribution

### 5. Protocol Compliance
- Coordinated multi-agent operation
- Reward division system
- Collision avoidance between agents

## Implementation Details

### Technologies Used
- Python with PyGame for simulation
- NumPy for occupancy grid management
- Priority Queues for pathfinding algorithms
- Custom asset design with Ibis Paint X

### Key Components
- Robot class for agent behavior
- Environment mapping system
- Pathfinding algorithm implementations
- Dynamic obstacle management
- Multi-agent coordination system

## Challenges and Solutions

| Challenge | Solution |
|-----------|----------|
| Slow mapping | Optimized agent speed and sensing range parameters |
| Agent getting stuck | Implemented retry mechanism with maximum attempts |
| Agent collisions | Treated other agents as obstacles in pathfinding |

## Testing and Results

Performance comparison between A* and Dijkstra's algorithms in different scenarios:

| Scenario | A* (seconds) | Dijkstra (seconds) |
|----------|--------------|-------------------|
| Normal (4 obstacles) | 12.29 | 11.74 |
| High Traffic (8 obstacles) | 14.08 | 13.76 |
| Emergency (12 obstacles) | 16.00 | 16.27 |

Results indicate that A* performs slightly better in most cases, while Dijkstra's algorithm shows marginal advantages in high-complexity scenarios.

## Installation


Make sure you have [Python](https://www.python.org/downloads/) installed.

Follow these steps to set up the environment and run the application:

1. Clone the Repository:
   ```bash
   git clone https://github.com/Sambonic/krusty-krabs-navigator
   ```
   ```bash
   cd krusty-krabs-navigator
   ```

2. Create a Python Virtual Environment:
```bash
python -m venv env
```

3. Activate the Virtual Environment:
- On Windows:
  ```
  env\Scripts\activate
  ```

- On macOS and Linux:
  ```
  source env/bin/activate
  ```
4. Ensure Pip is Up-to-Date:
  ```
  python.exe -m pip install --upgrade pip
  ```
5. Install Dependencies:

   ```bash
   pip install .
   ```
Or simply run the pip install line in the notebook
