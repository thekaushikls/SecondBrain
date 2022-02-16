# DCEL Topology
Created : 16-02-2022 10:13

* DCEL is a data structure logic for planar complex shapes. It handles sub-divisions in a geometric surface.
* The surface is divided into Points / Vertices, Edges, and Faces.
* **Planar graphs** do not have intersecting / overlapping edges. (Ex: Triangulated mesh)
* **Complexity** is the sum of the (number of faces, number of vertices, and number of edges)
* Face and it's edges are **Incident**. So are Edges and their respective vertices.
* Two copies of edges are stored: One for each direction.
* Each face can be constructed by moving clockwise through the edges.
* This results in all the faces (including the outer / entire) being clockwise.
* The outer face is made up of counter-clockwise edges because it is outside.
* Every edge is a pointer to the face it surrounds. 
* Can find one face from another using the common edge.
* Can find all edges at a vertex.
* So, even if an edge seems to be shared by two faces, since we have two copies, since the directions are different, they are different objects.
* Each edge also points to its twin (edge in oposite direction)
* Edges around a face are in a linked-list, to understand the previous, and next objects.
* Each face points to only one edge. Since a face can have unspecified number of edges, it becomes unfeasible to store/point to all edges. Since edges can be traversed (previous/next), the entire face can be identified from just s single edge.
* Each edge is a combination of two half-edges, in opposite directions called twins.
* when transversing, the face the edge represents is always on it's left (clockwise).
* Consider convention: Inside -> Clockwise, Outside -> Counter-clockwise.

`Edge(startPoint, endPoint, *twinEdge, *prevEdge, *nextEdge, *refFace*)`

## References
1. https://www.youtube.com/watch?v=enb13mZ7Pq4&list=PLtTatrCwXHzEqzJMaTUFgqoCNllgwk4DH
2. https://www.youtube.com/watch?v=iyU6UVrg__o
3. https://github.com/t1jsh111/2IMA15
4. https://github.com/Gimly/DoublyConnectedEdgeList