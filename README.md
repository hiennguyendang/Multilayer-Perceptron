# Multilayer Perceptron (MLP) — C++ Data Structures & Algorithms Project

![C++](https://img.shields.io/badge/language-C++-blue.svg)
![Algorithm](https://img.shields.io/badge/algorithm-Graph%20%26%20Backpropagation-green.svg)
![Status](https://img.shields.io/badge/status-academic--project-success.svg)

## 📌 Overview
This academic project builds a modular C++ library that demonstrates how custom data structures and algorithms can be used to implement a Multi-Layer Perceptron (MLP) with training capability. The main goals:

1. Implement generic list data structures (`XArrayList`, `DLinkedList`).
2. Build dataset and dataloader utilities for batching and streaming.
3. Implement `xMap` (hash map) and a generic `Heap`.
4. Provide modular components for neural nets: layers, losses, metrics, model, and optimizers.
5. Implement directed & undirected graph structures and utilities (used later for computational graphs / topological sorting).
6. Implement forward and backward passes (backpropagation) and a topological sorter for DAG execution.

---

## 🚀 Project Structure (suggested)
mlp-project/
├── include/
│ ├── containers/
│ │ ├── IList.h
│ │ ├── XArrayList.h
│ │ └── DLinkedList.h
│ ├── map_heap/
│ │ ├── IMap.h
│ │ └── xMap.h
│ │ └── IHeap.h
│ │ └── Heap.h
│ ├── data/
│ │ ├── IDataset.h
│ │ ├── TensorDataset.h
│ │ └── DataLoader.h
│ ├── nn/
│ │ ├── ILayer.h
│ │ ├── FCLayer.h
│ │ ├── Activations.h
│ │ ├── ILoss.h
│ │ ├── CrossEntropyLoss.h
│ │ └── Model.h
│ ├── optim/
│ │ ├── IOptimizer.h
│ │ ├── SGD.h
│ │ └── Adam.h
│ └── graph/
│ ├── IGraph.h
│ └── DGraphModel.h
├── src/
│ └── (implementation *.cpp)
├── examples/
│ ├── train_mlp_classification.cpp
│ └── train_mlp_regression.cpp
├── tests/
│ └── unit_tests.cpp
├── tools/
│ └── compilation-command.sh
└── README.md

---

## 📚 Key Components (summary)

### 1. Containers
- `IList<T>`: abstract list API.
- `XArrayList<T>`: dynamic array list with random-access, iterators, `reserve()`, `shrink_to_fit()`.
- `DLinkedList<T>`: doubly-linked list with forward and backward iterators.

### 2. Dataset & DataLoader
- `IDataset`: returns `(input, target)` per index, supports transforms.
- `DataLoader`: batching, shuffle, drop-last, `collate_fn`. Iterator-compatible for training loops.

### 3. Map & Heap
- `xMap<K,V>`: separate-chaining hash map with customizable hash/equality callbacks, rehashing on loadFactor.
- `Heap<T>`: binary heap with comparator for min/max behavior, `push/pop/peek/heapify`, optional index map for fast `remove`.

### 4. Neural Network Components
- `ILayer` + implementations (FCLayer, ReLU, Sigmoid, Softmax).
- `ILoss` + `CrossEntropyLoss`, `MSELoss`.
- `IModel` + `MLPClassifier` that composes layers, runs forward/backward, and trains via `IOptimizer`.
- `IOptimizer` + `SGD`, `Adam`.
  
## 🔹 Task 5: Graph Data Structure
### Main Classes
- `IGraph<T>`: defines the common API for graphs.  
- `AbstractGraph<T>`: abstract class with adjacency list.  
- `DGraphModel<T>`: implementation of a **directed graph**.  
- `UGraphModel<T>`: implementation of an **undirected graph**.  

### Features
- Add and remove vertices/edges.  
- Get in-degree / out-degree.  
- Check connectivity.  
- Traverse vertices and print the graph.  

---

## 🔹 Task 6: Multilayer Perceptron & Backpropagation
### Components
- **Forward Pass**: compute outputs based on weights.  
- **Backward Pass**: propagate gradients and update weights.  
- **Topological Sorting (Topo Sort)**: determines the computation order in the DAG.  

### Implementation
- `TopoSorter<T>`: supports **DFS** and **BFS** topo sort.  
- Data structures supported: **Stack**, **Queue**, **DLinkedListSE**.    

---

## 🔧 Build & Run
   ```bash
   ./compilation-command.sh
