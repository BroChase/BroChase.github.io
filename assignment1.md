---
layout: default
---

## Welcome to Assignment 1

Chase Brown

Assignment 1

Over the past few weeks of class we have began to discuss different architectures and algorithms for parallel and distributed systems. Primarily we have been focusing on the differences between sequential problems such as prefix summation and the use of SIMD and MIMD architectures for parallelization of the problem. The basic understandings gained is that different computer architectures and hardware along with algorithms can allow for a speed up in computation along with higher efficiency in operations such as prefix summation and matrix multiplication thus far.

The problem of sum prefix computation that we have discussed in depth has helped to give a basic understanding of why paying attention to how an algorithm or code is written can make a large difference. While much of the optimization is done by the compiler not everything can be optimized by the compiler and must be thought of when writing an algorithm. The two algorithms we looked at for the sum prefix being the parallel prefix algorithms Upper/Lower and Odd/Even, seem to be straight forward with a simple problem. The simple recursive nature of the diagrams allowed for a simple understanding of their design. The combination of these two algorithms into the Ladner and Fisher&#39;s parallel prefix was something I found very interesting. In order to come up with a better algorithm the use of Upper/Lower (P

# 0
) combined with Odd/Even (P
# 1
­) generates a better overall algorithm. The use of the Upper/Lower algorithm because of its kN/2 size and k depth and Odd/Even with increased depth of 2k – 2 but reduced size of 2N – K – 2, they can be combined using the Fisher&#39;s parallel prefix to keep a depth of k and a size of 4N – 4.96N
# 0.69
 + 1 for N = 2
# k
.

The problem of matrix multiplication and avoiding an explicit reduction operation was another problem that we have been interested in. This was a straightforward problem that I had already covered in numerical analysis. The idea that you can perform matrix multiplication via column or row wise and still avoid the explicit reduction operation in order to perform in parallel the computation of matrix C if matrix A and B are your input matrix. In the most recent class, we have begun discussing how this happens using the Control Unit and Processing Elements given assembly level code for loading and performing arithmetic operations.

In the coming classes I am looking forward to understanding more about the control unit and processing elements. I am very interested to see more about CUDA programming to expand my knowledge and understanding of GPU programming.

[Main](./)
