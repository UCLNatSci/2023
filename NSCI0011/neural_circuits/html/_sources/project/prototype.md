# Prototype

Submit your answers to the following questions to the 'Prototype' link in the Assessments section of Moodle.

## Part 1: Background

The list `x` is the adjacency list of an undirected graph:

```
x = [[3], [11, 6, 5], [4, 11, 5], [0], [2, 6, 6], [12, 19, 2, 1],
    [4, 17, 1, 4, 8], [14, 11], [6], [], [15, 11], [10, 2, 1, 16, 15, 7],
    [5], [], [7], [10, 11], [11], [6, 19], [], [5, 17]]
```

1\. The adjacency list of an undirected graph has the property that for any two nodes `i` and `j`, if `i` is a neighbour of `j` then `j` is a neighbour of `i`. Show that `x` is the adjacency list of an undirected graph.

2\. Find a pair of nodes that are not connected by a path.

3\. Determine the node pair(s) with the maximum path distance in the graph.

4\. Determine all connected components in the graph (full marks if you use a technique which would work for *any* undirected graph regardless of size).

*NB while it might be possible to answer these questions using pen and paper, you should determine your answers using Python code and the computational techniques studied in class. Full marks will be given for answers which use techniques which could work for an undirected graph of ANY size (not just `x`). You should include sufficient text (in the form of Python comments) to explain how your code determines the answer to each question.*

Submit your answers to Part 1 as a single `.py` file.

## Part 2: Prototype

### Step 1

Generate a NetworkX object representing the directed graph of the *C Elegans* egg-laying circuit. Then use NetworkX to plot a network diagram of the graph.

### Step 2

Write Python code to generate the two [degree distributions](https://mathinsight.org/degree_distribution) of a general directed graph. Then plot histograms of the in-degree and out-degree distributions of the *C Elegans* egg-laying circuit.

### Step 3

Write Python code which calculates the motif-frequency spectrum of a general directed graph. For example, write a function which given a NetworkX graph object `G` returns an array of motif frequencies.

Suggested steps:

1. Determine adjacency matrices of the 13 distinct order-3 connected graphs.
2. Write a function `motif_number(H)` which checks whether graph `H` is isomorphic to any of the 13 order-3 graphs, and if so returns its motif number.
3. Write a function `motif_spectrum(G)` which samples all order-3 subgraphs of `G`, determines the motif number of each, then returns the motif frequency spectrum.

Plot the motif-frequency spectrum of the *C Elegans* egg-laying circuit.

### Step 4

Generate a [random graph](https://en.wikipedia.org/wiki/Erd%C5%91s%E2%80%93R%C3%A9nyi_model) with the same number of edges and vertices as the *C Elegans* egg-laying circuit. Plot its two degree histograms and its motif frequency spectrum.



