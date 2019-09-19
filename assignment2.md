---
layout: default
---

## Welcome to Assignment 2

Chase Brown

Assignment 2

Application areas for the prefix problems.

Research 1 Parallel Prefix Sum (Scan) with CUDA


One application that I am interested in is the use of GPU's for parallel processing. This led me to the document I ready about parallel Scan [1]. The document is an overview explanation of how a basic algorithm can be expanded using techniques to up performance using NVIDIA CUDA.

In the document the all-prefix-sums is used as an example because it is inherently sequential referencing the use in sorting, lexical analysis, string comparison, polynomial evaluation, stream compaction, and building histograms and data structures in parallel. The topic seemes very relevant to the discussions that we have been having in class and problems that we have been looking at and solving.

Four different algorithms are discussed and reviewed for performance given the problem of all-prefix-sums operation of an array of n elements. Sequential Scan, Naïve Parallel Scan, Double-buffered versions of Naïve Parallel Scan, and work-efficient Parallel Scan.

The Sequential Scan algorithm is implemented by simply looped over the array adding the value of the previous element in the array using two arrays the input and output arrays where the sum is written to the output array. This operation takes O(n) operations to complete. The sequential scan is used as the base case for what a parallel algorithm should be able to beat or in their description be work-efficient.

The first parallel algorithm that is discussed is the Naïve Parallel Scan. This scan is not work-efficient because it performs O(nlog2n) addition operations. The algorithm bases its performance on the idea that there are as many processors as there are data elements but with CUDA the tasks are divided into small parallel batches that it calls warps. The use of G80 GPU which has warps of 32 threads in parallel is used as an example. This causes a problem because if the array is of significant size then the algorithm will not work because warps will be overridden.

The second parallel algorithm is nothing more then the first parallel algorithm, but it has an added feature which allows for data to be stored called double-buffered version. This requires two temp arrays of size n. Using this algorithm an array of 512 elements can be processed on a G80 GPU.

The third parallel algorithm discussed is based on the idea that you can use the knowledge behind how a balanced tree works. This allows the algorithm to make two passes on the data which are referred to in the paper as up-sweep phase and down-sweep phase. This allows the algorithm to reduce the data in the first phase and in the second phase finish traverse back up the tree using the partial sums from the first sweet to build the scan. This algorithm allows for a work-efficient algorithm that allows for a G80 GPU to work on arrays of 1024 elements.

Avoiding Bank Conflicts. The algorithm that is described in the third algorithm performs approximately the same amount of work as the optimal sequential algorithm. This causes it to not be as efficient on the GPU because of memory access patterns. It is described that for the G80 GPU which executes 16 threads in parallel in a half-warp the worst case is a degree-16 bank conflict. Bank conflicts cause serialization of the bank. Accessing of banks is referred to as the degree of a bank conflict. This slows down penalization because the degree-n bank conflicts require n times as many cycles to process compared to access with no conflicts. These conflicts can be avoided by most CUDA computations by padding the 2D array to a width not evenly divisible by the number of shared memory banks.



Bibliography

1. M. Harris. Parallel Prefix Sum (Scan) with CUDA. (2009). [Online]. Available: [http://developer.download.nvidia.com/compute/cuda/2\_2/sdk/website/projects/scan/doc/scan.pdf](http://developer.download.nvidia.com/compute/cuda/2_2/sdk/website/projects/scan/doc/scan.pdf)

[Main](./)
