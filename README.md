# Algos-in-giraph
This repository contains the famous algorithmic code of graphs that are implemented in Apache Giraph.
Algorithms implemented

1. Label Propagation Algorithm
2. Stochastic Gradient Descend (Used Agrregrator Class)

###Following are the screenshots and the conceots describing the above algorithms


#### Stochastic Gradient Descend
The formula used in SGD is 
![](https://raw.githubusercontent.com/LakshayNagpal/Algos-in-giraph/master/images/SGD.png)

A sample input for SGD :

[0,53,[[5,3],[7,2]]]<br />
[2,26,[[1,3],[3,4]]]<br />
[4,50,[[3,5],[5,1]]]<br />
[6,12,[[7,3]]]<br />
[1,57,[[2,3]]]<br />
[3,14,[[2,4],[4,5]]]<br />
[5,79,[[0,3],[4,1]]]<br />
[7,85,[[0,2],[6,3]]]<br />

The Output is as follows :

0	61.490045658068404<br />
1	57.792721810904986<br />
2	27.353103488114787<br />
3	14.395696686140393<br />
4	56.53684400949615<br />
5	86.14754281050081<br />
6	15.487349502178727<br />
7	89.81843043854076<br />

The concept used is:

![](https://raw.githubusercontent.com/LakshayNagpal/Algos-in-giraph/master/images/SGD1.png)
![](https://raw.githubusercontent.com/LakshayNagpal/Algos-in-giraph/master/images/SGD2.png)

#### Label Propagation Algorithm

Each vertex has a label, initially its own ID, that it sends to its direct
neighbors through messages. The simple heuristic that each vertex applies is to acquire the label that is
occurring most frequently among its neighbors, breaking ties randomly (that is, if two labels occur most
frequently across neighbors and have the same frequency, choose randomly). When a vertex acquires a new
label, it sends the label to its neighbors. This is why the algorithm is called the label propagation algorithm.
For example, Lady Gaga initially propagates the string “Lady Gaga”, which is her ID. At each iteration, each
vertex acquires a new label if it finds a label that occurs more frequently across its neighbors than its current
one. In the case of Lady Gaga, after some iterations, the label appears more frequently in the neighborhood
of her fans should be “Lady Gaga”. In that case, the vertex propagates the label to its neighbors through a
message. The algorithm halts when no vertex changes label. At the end of the computation, each vertex
holds the label representing its community. This label corresponds to the ID of a vertex in its community—a
vertex that is more “central” to the community it represents (in this example, “Lady Gaga”).

A sample Input :

[1,1,[[3,0],[11,0],[16,0]]]<br />
[3,1,[[1,0],[16,0]]]<br />
[16,16,[[1,0],[11,0],[3,0],[13,0],[10,0],[12,0]]]<br />
[11,1,[[1,0],[16,0],[13,0]]]<br />
[13,1,[[11,0],[16,0]]]<br />
[6,6,[[10,0],[14,0]]]<br />
[10,10,[[6,0],[14,0],[7,0],[15,0],[16,0],[12,0]]]<br />
[14,6,[[7,0],[10,0],[6,0]]]<br />
[7,6,[[15,0],[10,0],[14,0]]]<br />
[15,15,[[10,0],[7,0]]]<br />
[12,3,[[16,0],[4,0],[2,0],[8,0],[9,0],[5,0],[10,0]]]<br />
[4,4,[[2,0],[12,0]]]<br />
[2,2,[[4,0],[12,0],[8,0]]]<br />
[8,8,[[12,0],[2,0],[9,0]]]<br />
[9,9,[[8,0],[2,0],[5,0]]]<br />
[5,5,[[2,0],[9,0]]]<br />

The Output is as follows

1	1.0<br />
2	2.0<br />
3	1.0<br />
4	2.0<br />
5	2.0<br />
6	6.0<br />
7	6.0<br />
8	2.0<br />
9	2.0<br />
10	6.0<br />
11	1.0<br />
12	2.0<br />
13	1.0<br />
14	6.0<br />
15	6.0<br />
16	1.0<br />

The right hand side denotes the new label acquired by the node !!

![](https://raw.githubusercontent.com/LakshayNagpal/Algos-in-giraph/master/images/LPA1.png)
![](https://raw.githubusercontent.com/LakshayNagpal/Algos-in-giraph/master/images/LPA2.png)
![](https://raw.githubusercontent.com/LakshayNagpal/Algos-in-giraph/master/images/LPA3.png)
![](https://raw.githubusercontent.com/LakshayNagpal/Algos-in-giraph/master/images/LPA4.png)
