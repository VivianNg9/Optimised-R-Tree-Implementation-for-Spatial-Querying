 # __<center>Optimsed R-Tree Implementation for Spatial Querying</center>__


## __<center>Overview</center>__

Implementing an R-tree data structure to optimize spatial querying of 2D points, comparing its efficiency to sequential scanning and incorporating a divide-and-conquer approach to further enhance performance.

## __<center>Dataset and Query Specification</center>__
- **Dataset:** A collection of 2D points, each with unique IDs and (x, y) coordinates, provided in [`R_tree_Construction.txt`](https://github.com/VivianNg9/Optimised-R-Tree-Implementation-for-Spatial-Querying/blob/main/R_tree_construction.txt).
``` python
id_1 x_1 y_1
id_2 x_2 y_2
...
id_n x_n y_n
```


- **Range Queries:** Set of 200 queries, each specifying a rectangular range, provided in [`200Range.txt`](https://github.com/VivianNg9/Optimised-R-Tree-Implementation-for-Spatial-Querying/blob/main/200Range.txt).

## __<center>Project Workflow</center>__



## __<center>Analysing the working of R-Tree</center>__




## Key Components of the Project
- **Sequential Scan:** Implemented in [`Sequential_Scan.py`](https://github.com/VivianNg9/Data-Mining/blob/main/R-tree/Sequential_Scan.py), this script processes spatial range queries sequentially and outputs the results.
- **R-Tree Construction and Querying:** Implemented in [`Rtree.py`](https://github.com/VivianNg9/Data-Mining/blob/main/R-tree/Rtree.py) and [`Rtree_DC.py`](https://github.com/VivianNg9/Data-Mining/blob/main/R-tree/Rtree_DC.py), these scripts construct R-trees and process queries utilizing a divide-and-conquer approach for improved efficiency.
- **Classes:** `Node` and `RTree`, essential for building and managing the R-tree structure.

## Output Files:
1. **Sequential Scan Output [`Sequential_output.txt`](https://github.com/VivianNg9/Data-Mining/blob/main/R-tree/Squential_output.txt):**
   - Contains the results of processing range queries using the sequential scan method.
   - Includes the total number of points within each query range.
   - Records the total and average query processing times.

2. **R-Tree Query Output [`Rtree_output.txt`](https://github.com/VivianNg9/Data-Mining/blob/main/R-tree/Rtree_output.txt):**
   - Results of the range queries processed using the R-tree.
   - Similar to the sequential output, it details the number of points per query range.
   - Provides insights into the efficiency of the R-tree method by listing total and average processing times.

3. **Divide-and-Conquer R-Tree Output [`Rtree_DC_output.txt`](https://github.com/VivianNg9/Data-Mining/blob/main/R-tree/Rtree_DC_output.txt):**
   - Output from processing queries using the R-tree with a divide-and-conquer approach.
   - Highlights the performance improvement over the standard R-tree method.
   - Contains the count of points within each range query and the corresponding processing times.

4. **Report [`R tree Report.pdf`](https://github.com/VivianNg9/Data-Mining/blob/main/R-tree/R-tree.pdf):**
   A comprehensive document detailing program functions, execution requirements, and a thorough analysis of R-Tree's construction and searching mechanism.





