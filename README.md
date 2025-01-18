 # __<center>Optimsed R-Tree Implementation for Spatial Querying</center>__


## __<center>Overview</center>__

Implementing an R-tree data structure to optimize spatial querying of 2D points, comparing its efficiency to sequential scanning and incorporating a divide-and-conquer approach to further enhance performance.

## __<center>Dataset and Range Query</center>__
- **Dataset:** A collection of 2D points, each with unique IDs and (x, y) coordinates, provided in [`R_tree_Construction.txt`](https://github.com/VivianNg9/Optimised-R-Tree-Implementation-for-Spatial-Querying/blob/main/R_tree_construction.txt).
``` 
id_1 x_1 y_1
id_2 x_2 y_2
...
id_n x_n y_n
```


- **Range Query:** Set of 200 queries, each specifying a rectangular range [x, x'] x [y, y'], provided in [`200Range.txt`](https://github.com/VivianNg9/Optimised-R-Tree-Implementation-for-Spatial-Querying/blob/main/200Range.txt).
``` 
id_1 x_1 x'_1 y_1 y'_1
id_2 x_2 x'_2 y_2 y'_2
...
id_200 x_200 x'_200 y_200 y'_200
```

## __<center>Project Workflow</center>__

**Squential-Scan Based Method:** 
Implementing the sequential scan method to process spatial range queries. Reading points from dataset and 200 set of queries , performs a sequential scan to count points within each query range, and outputs the results, along with total and average query processing times, to [`Squential_output.txt`](https://github.com/VivianNg9/Optimised-R-Tree-Implementation-for-Spatial-Querying/blob/main/Squential_output.txt).
- Total time: 3.33951997756958 seconds
- Average time per query: 0.0166975998878479 seconds
- Points count:
  9
  12
  10
  5
  6
  ....

<details>
  <summary>Click to view full code for sequential scan</summary>

```python
import time

# Load the points from the dataset file
points = [] # Create a blank list to store data points
n=0
with open("R_tree_construction.txt", "r") as file:
    # Iterate over each line in the file
    for data in file.readlines():
        data = data.split()
        # Append a dictionary to 'points' with id, x, and y from the line, converting strings to integers
        points.append( 
            {
                "id": int(data[0]),  
                "x": int(data[1]),   
                "y": int(data[2])    
            }
        )


# Load the range queries
queries = [] # Create a blank list to store query ranges
with open("200Range.txt","r") as range:
    for r in range.readlines():
        r = r.split()  
        # Append a dictionary to 'queries' with x1, x2, y1, and y2 from the line, converting strings to integers
        queries.append({ 
            "x1": int(r[1]),  
            "x2": int(r[2]),  
            "y1": int(r[3]),  
            "y2": int(r[4])   
        })

# List to store the results of each query
results = []
start_time = time.time()  # Record the start time of the query processing

# Iterate through each query in 'queries'
for query in queries:
    count = 0  
    # Iterate through each point in 'points'
    for point in points:
        # Check if the point lies within the bounds of the query box
        if query["x1"] <= point["x"] <= query["x2"] and query["y1"] <= point["y"] <= query["y2"]:
            count += 1  # Increment counter if the point is within the query box
    results.append(count)  # Append the count of points in the query box to 'results'

end_time = time.time()  # Record the end time of the query processing
total_time = end_time - start_time  # Calculate total time taken for processing
average_time_per_query = total_time / len(results)  # Calculate average time per query

# Export the results to an output file
with open('Squential_output.txt', 'w') as f:
    f.write('Total time: ' + str(total_time) + ' seconds' + '\n') 
    f.write('Average time per query: ' + str(average_time_per_query) + ' seconds' + 2*'\n')
    f.write('Points count: ' + "\n")
    for count in results:
        f.write(str(count) + '\n')
</details>
```

**Squential-Scan Based Method:** 
Implementing the sequential scan method to process spatial range queries. Reading points from dataset and 200 set of queries , performs a sequential scan to count points within each query range, and outputs the results, along with total and average query processing times, to [`Squential_output.txt`](https://github.com/VivianNg9/Optimised-R-Tree-Implementation-for-Spatial-Querying/blob/main/Squential_output.txt).
- Total time: 3.33951997756958 seconds
- Average time per query: 0.0166975998878479 seconds
- Points count:
  9
  12
  10
  5
  6
  ....

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





