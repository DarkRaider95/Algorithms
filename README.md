# Algorithm Course Projects

This repository contains three major projects developed as part of the Algorithms course during my Bachelor's degree program. Each project focuses on implementing fundamental data structures and algorithms in C, with an emphasis on generic programming and efficient implementation.

## Project Overview

### Exercise 1: Sorting Algorithms
Implementation of five fundamental sorting algorithms with generic data type support:
- Selection Sort
- Insertion Sort
- Merge Sort (iterative implementation)
- Quick Sort (with three-way partitioning)
- Heap Sort

Key features:
- Generic implementation using void pointers
- Support for custom comparison functions
- Comprehensive testing suite
- Performance optimization for large datasets

### Exercise 2: Data Structures
Implementation of fundamental data structures:
- Binary Search Tree
  - Complete implementation with standard operations
  - Generic data type support
  - Balance-dependent performance
- Hash Table
  - Dynamic resizing capabilities
  - Chained hashing for collision resolution
  - Generic key/value storage
  - Customizable hash functions

### Exercise 3: Graph Implementation
Advanced graph data structure implementation featuring:
- Efficient adjacency list representation using hash tables
- Support for both directed and undirected graphs
- Implementation of key algorithms:
  - Dijkstra's shortest path algorithm
  - Depth-First Search (DFS)
  - Strongly Connected Components detection
- Priority queue implementation for optimization

## Common Features Across Projects

All projects share these characteristics:
- Written in C with C99 standard compliance
- Generic implementation using void pointers
- Comprehensive testing suites including:
  - Unit tests using Unity framework
  - Stress tests for performance evaluation
- Support for multiple data types (integers, floats, strings)
- Detailed performance analysis and optimization

## Repository Structure

```
.
├── Esercizio_1/
│   ├── heap_sort/
│   ├── insertion_sort/
│   ├── merge_sort/
│   ├── quick_sort/
│   └── selection_sort/
├── Esercizio_2/
│   ├── Alberi_semplici/
│   └── Hash_table/
└── Esercizio_3/
    ├── graph/
    ├── priority_queue/
    └── testing/
```

## Building and Testing

Each project includes its own build system using Make. To build and test any component:

```bash
# Navigate to the desired component
cd ExerciseN/component_name

# Build the project
make

# Run unit tests
cd unit_testing
make
./component_test

# Run stress tests
cd stress_testing
make
./component_stress_test [file_path] [options]
```

## Performance Highlights

### Sorting Algorithms (1M elements)
- Quick Sort: Best overall performance (8-10 seconds)
- Merge Sort: Consistent performance (10-12 seconds)
- Heap Sort: Moderate performance (28-33 seconds)
- Selection/Insertion Sort: Not suitable for large datasets (>10 minutes)

### Data Structures Operations
Hash Table vs Binary Tree comparison:
- Hash Table excels in most operations but performance depends on hash function quality
- Binary Tree provides more consistent performance across data types
- Hash Table generally faster for insertions and searches

### Graph Implementation
Successfully tested with real-world data:
- Efficient pathfinding between cities (e.g., Turin to Catania: 1207.68 km)
- Robust handling of disconnected components
- Effective strongly connected component detection

## Requirements
- C99 compliant compiler
- Make build system

## Additional Notes
Each project includes detailed documentation in its respective directory, including:
- Implementation details
- Performance analysis
- Usage examples
- Testing procedures

For specific details about each project, please refer to the README files in their respective directories.