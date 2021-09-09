# UMAST

-----
About
-----
UMAST is a tool for calculating maximum agreement subtree for two phylogenetic 
trees. It provides fast command-line interface for calculating maximum agreemet subtrees 
for rooted and unrooted trees based on (Gordon, 1980).

In addition, UMAST can also compute agreement subtree-based distance between two trees 
("l-distance") as described in (Dong and Kraemer, 2004). It is defined as follows: for two unrooted trees,
A and B, with equal sets of leaves, let C be their maximum agreement subtree. For each leaf that is not present
in C, append it to C according to two different topologies, A and B, and compute the number of nodes in C between
two alternative positions of this leaf. The distance is the sum of these numbers for all extra leaves.
However, the procedure described in (Dong and Kraemer, 2004) contained a bug leading to inconsistent result, 
which was fixed in this version.

------------
Installation
------------
Run makefile.

-----
Input
-----
Two trees in Newick format.

------
Output
------
stdout: size of a resulting maximum agreement subtree 
or (when called with -d argument) l-distance between input trees.

umast.tre: file containing maximum agreement subtree in Newick format.

umast.log: text file containing log information about run.

----------------------
Command line arguments
----------------------
-1 first tree file

-2 second tree file

-r use this option if trees are rooted

-o path to resulting (u)mast tree file, default ./umast.tre

-l path to log file, default ./umast.log

-d Print l-distance to stdout instead of agreement subtree size.

./umast -1 tree1_path -2 tree2_path [-r] [-o outtreefile] [-l logfile] [-d]
