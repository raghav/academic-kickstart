---
title: "Sparse Matrix Multiplication"
# subtitle: Learn how to blog in Acdfsademic using Jupyter notebooks
# summary: Learn how to blog in Academic using Jupyter notebooksnjlkklj
date: 2020-05-09
#lastMod: 2019-06-30T00:00:00Z
# date: "2019-02-05T00:00:00Z"
# lastMod: "2019-09-05T00:00:00Z"
authors:
- admin
markup: mmark
# image:
#   placement: 3
#   caption: 'Image credit: [**John Moeses Bauan**](https://unsplash.com/photos/OGZtQF8iC0g)'
---

<h4><a style="color:navy"; font-weight:normal; href="https://arxiv.org/pdf/1906.00327.pdf"><u>Paper Referred</u></a>: Sparse Matrix to Matrix Multiplication: A Representation and Architecture for Acceleration</h4>
<h4><span style="color:navy"; font-weight:normal>Authors</span>: Pareesa Ameneh Golnari, Sharad Malik</h4>
<br>
<h2><span style="color:navy">Why this research?</span></h2>
With the increasing demand of neural networks in new application areas and large no. of training features required for better accuracy, it is becoming increasingly important to reduce the memory required to store this data. Though the sparse matrix is an efficient way to store this data more efficiently, there is no efficient way for the sparse matrix to matrix multiplication. This paper proposes a new representation for sparse matrices and an architecture for their multiplication. A speedup of 14-49 times in accessing the data and of 9-30 times in multiplication is demonstrated.

<h2><span style="color:navy">The Paper</span></h2>
The paper compares the random data access cost of various sparse formats with compressed row storage (CRS) being one of the most efficient formats. This paper proposes an Indexed CRS format to reduce the complexity of accessing a non-zero data. Each row of the matrix is divided into sections and each section is further divided into blocks. Each section is represented by a counter vector which contains no. of non-zero values before this section followed by no. of non-zero values in each of its blocks. Any values in this representation can be transformed into the corresponding matrix index (and vice-versa) using the information in section counter vectors. To locate an element at (i, j), the corresponding section no. is ⌊*j/S*⌋ and block no. is ⌊*(j%s)/b*⌋ where S and b are the lengths of the section and block respectively. Thus, for searching an element (i,j), we need to see only the corresponding block, reducing the random memory access to (*b/2 + 1*). Comparing this with the conventional CRS format, memory access reduces by a factor of *ND/(b+2)* and required storage increases by a factor of *(2DS+1)/(2DS)*, where N is the no. of rows and D is density (ratio of no. of non-zeros to dataset size). 

Next, this paper proposes a new architecture for implementing the sparse matrix multiplication (SpMM) represented in the format described above. In this direction, the paper discusses an algorithm for a dot product of the 1st matrix’s row a with 2nd matrix’s column b. Comparing elements of these two vectors, if the index of a’s ith element equals b’s jth element in the original matrices (found using section counter vector), the product of their values is added to the dot product and both operands are incremented. Else, only the vector with the smaller index is checked for the next element. While this algorithm serves its purpose, it suffers from a slower movement of operands because operand with larger index is not incremented and stalling where the inputs are shared across multiple nodes. 

To account for these drawbacks, a synchronized mesh architecture is proposed. Each node of the mesh has a comparator, a buffer and a flag located before the MAC unit. Unlike the previous algorithm, if the indices of two operands at hand do not match, the operand with a larger index is stored in the buffer and the corresponding flag is set, thus avoiding stalling of the data and using two operands per cycle. During the next comparison of indices, the flag is read to indicate if a value is stored in the buffer. If the operand with the smaller index can be matched with a buffered value, buffered value is used for multiplication. Synchronization is performed at the end of every R elements and buffers are erased to ensure that operand buffers are most R (depth of operand) element in size, thus preventing any stall. 

Next, the proposed sparse format and multiplication algorithm are evaluated against various datasets. It is observed that this architecture’s acceleration increases (i.e., latency reduces) as the density (i.e., the ratio of no. of non-zero elements with dataset size) reduces. This architecture is then compared with previous approaches for the given range of densities. The proposed SpMM architecture shows a 15-39 times improvement over conventional matrix multiplication and 2-30 times improvement over FPIC. 

<h2><span style="color:navy"></span></h2>


