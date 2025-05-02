Dijkstra Grid Pathfinding
=========================

This project implements Dijkstra's algorithm for pathfinding on a 2D grid, similar to a warehouse layout. It includes different cell types (normal path, priority path, obstacles) and visualizes the path using matplotlib.

Features
--------

- Dijkstra’s algorithm for shortest path
- Supports:
  - S: Start
  - D: Destination
  - .: Normal path (cost 1)
  - P: Priority path (cost 0.5)
  - X: Obstacle (not walkable)
- Grid and path visualized with matplotlib
- Prints grid with * showing the path

How It Works
------------

- The algorithm finds the shortest-cost path from S to D, avoiding obstacles.
- Costs are based on the type of cell.
- It uses a simple set to track unvisited nodes and selects the one with the lowest cost at each step.
- The path is reconstructed using parent pointers.

Requirements
------------

- Python 3.x
- matplotlib
- numpy

Install dependencies:

    pip install matplotlib numpy

Usage Example
-------------

    warehouse_map = [
        ['S', '.', '.', '.', '.'],
        ['X', 'X', '.', 'X', '.'],
        ['.', 'P', 'P', '.', '.'],
        ['.', 'X', '.', '.', 'D'],
        ['.', '.', '.', 'X', '.']
    ]

    start, end = find_start_end(warehouse_map)
    pathfinder = DijkstraPathfinder(warehouse_map)
    total_cost, path = pathfinder.dijkstra(start, end)

    if path:
        print_grid_with_path(warehouse_map, path)
        grid_path_visualization(warehouse_map, path)
    else:
        print("No path found.")

Test Cases
----------

The script includes several test cases:
- Grid with no obstacles
- Grid with obstacles
- Grid with priority paths
- Grid with no valid path

Each case prints the original grid, path, total cost, and a visual map.

License
-------

This project is open-source and free to use.
