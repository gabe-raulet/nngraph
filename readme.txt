** Nearest neighbor graph construction study **

The idea behind the code in this repository is to study (by implementation) different algorithms and ideas that construct
Nearest neighbor graphs from point cloud data. In this problem, we are given a set S of n points from d-dimensional Euclidean
space. We are then also given a scale parameter epsilon > 0. The goal is to construct an undirected graph G=(V,E) where V
is the set of vertices corresponding one-to-one to each point in S, and E contains the set of all pairs of vertices whose
corresponding points in S are within a distance of epsilon of each other under the euclidean metric (Note: the goal will later be
to extend this to arbitrary metric spaces and arbitrary distance functions, but for now I'm just going to focus on the metric
induced by the 2-norm of the difference between two vectors). To put it more formally, we have the following problem definition:

    Problem (Computing a neighborhood graph).

        Input: Finite set S of points from R^d and scale epsilon > 0.
        Output: Neighborhood graph (G,w).


A neighborhood graph also has a formal definition:

    Definition (Neighborhood graph).

        A neighorhood graph is (G,w), where G=(V,E) is an undirected graph and w : E -> R is its
        weight function.

The specific neighborhood graph we are interested in here is called the VR neighborhood graph. This graph has edges
between any two points whose distance is less than or equal to epsilon (and only these edges), and each such edge
has a weight equal to that distance.
