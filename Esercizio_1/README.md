# Sorting Algorithms Implementation

This repository contains implementations of five fundamental sorting algorithms in C, developed as part of the Algorithms course in the Bachelor's degree program. Each algorithm is implemented to work with generic data types through void pointers and comparison functions.

## Implemented Algorithms

1. **Selection Sort**: Implementation of the classic selection sort algorithm
2. **Insertion Sort**: Classic insertion sort implementation
3. **Merge Sort**: Divide-and-conquer merge sort implementation
4. **Quick Sort**: Enhanced quicksort with three-way partitioning
5. **Heap Sort**: Binary heap-based sorting implementation

## Key Features

- Generic implementation using void pointers
- Support for custom comparison functions
- Comprehensive unit testing
- Stress testing capabilities
- Support for sorting different data types (integers, floats, strings)

## Implementation Notes

### Quick Sort Optimization
- Implemented three-way partitioning to handle duplicates efficiently
- Uses middle element as pivot to improve performance on partially sorted arrays
- Partitions array into:
  - Elements less than pivot
  - Elements equal to pivot
  - Elements greater than pivot

### Merge Sort Enhancement
- Initial recursive implementation faced stack overflow with large datasets (~150,000 elements)
- Reimplemented iteratively to handle larger datasets efficiently

## Performance Comparison

Testing performed on large datasets (1 milion elements):

| Algorithm    | Integer Data  | Float Data    | String Data   |
|-------------|---------------|---------------|---------------|
| Selection   | > 10 minutes  | > 10 minutes  | > 10 minutes  |
| Insertion   | > 10 minutes  | > 10 minutes  | > 10 minutes  |
| Merge       | 10.07 seconds | 10.59 seconds | 12.04 seconds |
| Quick       | 9.31 seconds  | 10.61 seconds | 8.51 seconds  |
| Heap        | 33.13 seconds | 28.31 seconds | 29.02 seconds |

## Project Structure

```
├── heap_sort/
│   ├── heap_sort.c
│   ├── heap_sort.h
│   ├── stress_testing/
│   └── unit_testing/
├── insertion_sort/
│   ├── insertion_sort.c
│   ├── insertion_sort.h
│   ├── stress_testing/
│   └── unit_testing/
├── merge_sort/
│   ├── merge_sort.c
│   ├── merge_sort.h
│   ├── stress_testing/
│   └── unit_testing/
├── quick_sort/
│   ├── quick_sort.c
│   ├── quick_sort.h
│   ├── stress_testing/
│   └── unit_testing/
└── selection_sort/
    ├── selection_sort.c
    ├── selection_sort.h
    ├── stress_testing/
    └── unit_testing/
```

## Testing

Each algorithm includes two types of tests:

1. **Unit Tests**: Basic functionality testing using Unity testing framework
2. **Stress Tests**: Performance testing with large datasets
   - Tests sorting of integers, floating-point numbers, and strings
   - Measures execution time
   - Verifies correctness of sorted output

## Build Instructions

Each sorting algorithm can be built separately. Navigate to the desired algorithm's directory and use the provided Makefile:

```bash
# For unit tests
cd algorithm_name/unit_testing
make
./algorithm_name_test

# For stress tests
cd algorithm_name/stress_testing
make
./algorithm_name_test input_file.txt (int|str|float)
```