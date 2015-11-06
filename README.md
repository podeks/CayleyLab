# CayleyLab
A Linux/Windows application, founded upon the podeks/MathLibraries module suite, for creating, analyzing, and storing Cayley graph structures on various finite groups.

Assuming 4 gigabytes of RAM, this application is capable of producing Cayley graphs of size up to 5 million vertices and 10 million edges (one can push a little higher than this).  The construction of a Cayley graph proceeds at a rate of about 50,000-100,000 edges per second.

Click on 'Download ZIP' to download this application. After unzipping the repository folder CayleyLab-master, open it and move the folder 'cayleylab' anywhere you like. The zip file and repository folder can then be discarded. To run the application, double click on cayleylab.exe (32 bit) or cayleylab64.exe (64 bit) inside the 'bin' folder.

#### Screenshot:
![image 01](/screenshots/img01.jpg)

#### Features:
-A utility for creating a set of randomly selected elements from any of the finite groups provided by this application (which includes all finite simple non-abelian groups of order less than six million; see the list below), from which the Cayley graph can be created.

-A display of basic structural data pertaining to the graph, including the diameter, girth, expected path-distance of a random vertex from the root (which is equal to the expected path distance between two random vertices of the graph by symmetry), and tables displaying the sizes of the sets S(n) of vertices of path-distance n from the root vertex (identity element), and the sizes of the edge sets E(n) between them and T(n) within them.

-The option of computing the second largest eigenvalue in magnitude of the graph.  This functionality is provided by the Matrix Toolbox Java ([MTJ](https://github.com/fommil/matrix-toolkits-java.git)) library, in particular the ArpackSym interface to ARPACK sparse matrix library.  Note, that although this is the same library used by the eigs() command in MATLAB and Octave to compute the eigenvalues of a large sparse matrix, the ArpackSym interface will sometimes fail in cases where the eigs command wouldn’t (because of trickiness in avoiding numerical instabilities that can arise in the underlying Arnoldi/Lanczos algorithm).  Also note, that this is a very expensive computation, especially for graphs with over 100,000 vertices, that typically takes several times longer to compute than the time it takes to construct the graph.

-Upon creating a Cayley graph, one has the option to:
  (i) save the generating set to a file, which can later be loaded by the application.
 (ii) save the eigenvalue (if it was computed), together with the vertex and edge shell data (from which the other quantities are easily retrieved) to a file.
(iii) save the graph as a sparse color-matrix file.  This file is in a format that can be read by software packages such as MATLAB or Octave that handle sparse matrices.

-A color graph file created by this application can subsequently be loaded within the application for use as an alternate geometric/combinatorial implementation of the the group operation (*), by which further Cayley graphs can be created.
If you save a generating set in this context, then the file will contain as its header the name of the file containing the graph.  If you then load this generating set from file, then the graph will also automatically be loaded (so long as it is in the same directory).

-Also included is a catalog of predefined generating sets, which at present contains only the well known Lubotzky-Phillips-Sarnak Ramanujan Cayley graphs.

(*) Cayley graphs can be characterized as being vertex-transitive color-graphs (in the sense of having an involutive edge-coloring) .  Given such a graph, the group operation can be recovered by picking any vertex as the identity, and defining the product ab of two vertices a and b as the endpoint of the path defined by walking along the graph, starting at vertex a, according to the same color sequence of any path from the root vertex to b.

####Available Groups:
#####Matrix groups and projective groups over a finite field:<br>
GL<sub>n</sub>, SL<sub>n</sub>, PGL<sub>n</sub>, PSL<sub>n</sub> (General and Special linear groups and their projective groups) for n>=2.<br>
GSp<sub>n</sub>, Sp<sub>n</sub>, PGSp<sub>n</sub>, PSp<sub>n</sub> (Symplectic Similitude and Symplectic groups and their projective groups) for n>=4 even.<br>
U<sub>n</sub>, SU<sub>n</sub>, PU<sub>n</sub>, PSU<sub>n</sub> (Unitary and Special Unitary groups and their projective groups) for n>=3.<br>
The Suzuki group Sz(8)<br> 
The Dickson group G<sub>2</sub>(3)<br>
<br>
#####Symmetric and Alternating groups:<br>
S<sub>n</sub> and A<sub>n</sub><br>
<br>
#####The five sporadic simple groups of order less than five million (all less than one million):<br>
M<sub>11</sub> (order 7,920)<br>
M<sub>12</sub> (order 95,040)<br>
M<sub>22</sub> (order 443,520)<br>
J<sub>1</sub> (order 175,560)<br>
J<sub>2</sub> (order 604,800) <br>
