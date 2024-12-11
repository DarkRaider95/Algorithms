# Graph Implementation Exercise

This repository contains an implementation of a graph data structure in C, developed as part of the Algorithms course (Exercise 3). The implementation focuses on creating an efficient graph structure using hash tables for adjacency lists and includes algorithms for finding shortest paths and strongly connected components.

## Features

- Graph representation using hash tables for efficient adjacency lists
- Support for both directed and undirected graphs
- Implementation of key algorithms:
  - Dijkstra's algorithm for shortest paths
  - Depth-First Search (DFS)
  - Strongly Connected Components detection
- Priority queue implementation for Dijkstra's algorithm
- Comprehensive testing suite including both unit tests and stress tests

## Implementation Details

### Core Components

- `graph.c`: Main graph implementation with core functionality
- `priority_queue.c`: Priority queue implementation for Dijkstra's algorithm
- Hash table implementation (referenced from Exercise 2) for efficient vertex storage

### Key Data Structures

```c
typedef struct graph {
  HashTable_p vertex_table;  // Hash table storing vertices
  Gtype type;               // Graph type (directed/undirected)
  size_t vertex_num;        // Number of vertices
} Graph_t, *Graph_p;
```

### Major Algorithms

1. **Shortest Path (Dijkstra)**
   - Finds the shortest path between two vertices
   - Uses a priority queue for efficient vertex selection
   - Supports custom weight types through function pointers

2. **Strongly Connected Components**
   - Implements depth-first search
   - Identifies groups of vertices that are mutually reachable

## Example Usage

```c
// Create a graph
Graph_p graph = graph_create(NOT_DIRECTED);

// Insert edges
graph_insert(graph, source, destination, size, weight, hash_function, compare_function);

// Find shortest path
void* distance = min_walk(graph, src, dst, size, minDist, maxDist, 
                         hash_function, compare_vertex, compare_dist, 
                         sum_function, print_function);

// Find strongly connected components
unsigned int num_components = StrongConnected(graph, size, hash_function, 
                                            compare_function, print_flag);
```

## Testing

The project includes two types of tests:

1. **Unit Tests** (`unit_testing/`)
   - Tests individual components
   - Verifies correctness of graph operations
   - Uses Unity testing framework

2. **Stress Tests** (`stress_testing/`)
   - Tests performance with large datasets
   - Includes file parsing for test data
   - Verifies behavior under load

## Build Instructions

```bash
# Build main project
cd Grafi
make

# Build and run unit tests
cd unit_testing
make
./graph_test

# Build and run stress tests
cd stress_testing
make
./graph_stress_test [file_path] (min city1 city2|con)
```

## Example Results

The implementation was tested with real-world data, including:

1. Path finding between Turin and Catania:
   - Successfully found path of 1207.68 km
   - Traced through multiple intermediate cities

2. Connectivity testing:
   - Successfully identified when paths don't exist (e.g., Turin to Borsoi)
   - Correctly handled disconnected components

## Dependencies

- C99 compliant compiler
- Hash table implementation from Exercise 2