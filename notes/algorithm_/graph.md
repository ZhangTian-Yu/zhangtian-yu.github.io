# Graph

A graph consists of vertices $V$ and edges $E\subseteq V^2$ . The edges can be undirected or directed, resulting in undirected graphs or directed graph.

The data structure of a graph can be an adjacent matrix of size ${|V|}^2$ or an adjacent list of size $|V||E|$.

The reachability of a vertex in graph can be computed by depth-first search (DFS).

DFS maintains a adjacent list with boolean value and a stack which can be replaced by recursion of the algorithm.

It 