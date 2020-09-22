# Parse_Graph

This program receives an undirected graph,
and divides it into clusters such that the overwhelming
majority of edges are within cluster wrather the between clusters.

The algorithm takes a group of vertices and splits the group into two,
then continues splitting recursively until it is no longer a good idea.

The method of splitting a group is to find the leading eigenvector of the
adjacency matrix of the group and splitting according to the sign.
Meaning, if the i'th element in the eigenvector is positive then the i'th
vertex goes to group 1, otherwise it goes to group 2.
We decide if splitting is a good idea based on the difference in modularity
where the modularity is defined to be the sum 0.5 * v_i * v_j * s_i,j
where s_i,j is 1 if i and j are in the same group and -1 if not.

The input to the program should the name of a binary file of the following format:
first element is an integer - the number of vertices
then the number of neighbors the next vertex has and then the indices of those neighbors
The output will be a binary file of the following format:
first element is an integer - the number of clusters
then the size of the next cluster and then the indices of the elements in the cluster

The program needs two arguments: the name of the input file, the wanted name of the output file.
