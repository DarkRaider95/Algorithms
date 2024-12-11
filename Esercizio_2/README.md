# Data Structures Implementation

This repository contains implementations of fundamental data structures in C, focusing on Binary Trees and Hash Tables. This was the second exercise in the Algorithm course of the Bachelor's degree program.

## Implemented Data Structures

### 1. Binary Tree
- Complete implementation of a binary search tree with the following operations:
  - Insertion
  - Deletion
  - Search
  - Node creation and destruction
- Generic implementation using void pointers
- Support for different data types through comparison function pointers

### 2. Hash Table
- Implementation of a hash table with:
  - Dynamic resizing (grows when half full, shrinks when quarter full)
  - Collision resolution using chained hashing (linked lists)
  - Generic key/value storage using void pointers
  - Customizable hash and comparison functions
- Operations supported:
  - Insertion
  - Deletion
  - Search
  - Table creation and destruction

## Project Structure

```
.
├── Alberi_semplici/           # Binary Tree implementation
│   ├── alberi_semplici.c
│   ├── alberi_semplici.h
│   ├── stress_testing/        # Performance testing
│   └── unit_testing/          # Unit tests
│
└── Hash_table/               # Hash Table implementation
    ├── hash_table.c
    ├── hash_table.h
    ├── hash_list.c           # Linked list for collision handling
    ├── hash_list.h
    ├── stress_testing/       # Performance testing
    └── unit_testing/         # Unit tests
```

## Performance Analysis

Testing was performed with different data types (integers, floats, and strings) for both data structures:

### Insertion Times
| Structure    | Integers     | Floats      | Strings     |
|--------------|-------------|-------------|-------------|
| Binary Tree  | 43.82s      | 54.78s      | 4.86s       |
| Hash Table   | 9.66s       | 53.77s      | 2.00s       |

### Search Times
| Structure    | Integers     | Floats      | Strings     |
|--------------|-------------|-------------|-------------|
| Binary Tree  | 2.49s       | 3.30s       | 0.45s       |
| Hash Table   | 0.66s       | 10.96s      | 0.40s       |

### Deletion Times
| Structure    | Integers     | Floats      | Strings     |
|--------------|-------------|-------------|-------------|
| Binary Tree  | 2.98s       | 3.40s       | 0.10s       |
| Hash Table   | 0.68s       | 21.45s      | 0.31s       |

### Key Observations

1. **Hash Table Performance**:
   - Generally faster for insertions
   - Performance degrades with frequent resizing
   - Hash function quality significantly impacts performance (notably with floats)

2. **Binary Tree Performance**:
   - More consistent performance across data types
   - No resizing overhead
   - Performance depends on tree balance

## Building and Testing

```bash
# For Binary Tree tests
cd Alberi_semplici/stress_testing
make
./alberi_semplici_test [file_path] (int|str|float)

# For Hash Table tests
cd Hash_table/stress_testing
make
./hash_stress_test [file_path] (int|str|float)
```

## Requirements
- GCC compiler
- Make build system
- Unity testing framework (for unit tests)