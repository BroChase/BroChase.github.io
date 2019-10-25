---
layout: default
---

## Welcome to Assignment 3
Chase Brown

Over the last several classes we have switched our focus from SIMD to multiple instruction multiple data (MIMD). MIMD computers give the ability to run multiple instruction sets or control streams unlike SIMD computers which require the same instruction for each parallel thread. This give the ability to a MIMD machine to run multiple instructions using multiple data streams allowing for different operations in parallel throughout a program unlike SIMD where you have one operation that you want to perform at a large scale over and over allowing you to do it in parallel for a speedup.

The main question that is raised in chapter 4 is what makes an MIMD machine different then having multiple machines running simultaneously and a multiprocessor. This really comes down to the interconnection inside the machines and how thee multiprocessors are able to communicate and the access to the data streams. MIMD topologies and the way that the message passing between multiprocessors happens given them the edge over multiple computers. Work distribution with a multiprocessor while possible I believe to work out with multiple computers working together multiprocessors excel at scheduling and doing work distribution. We have spent time going over both block and cyclic mapping examples and prescheduled and dynamic work distribution.

We have also spent time discussing openMP and different ways that parallelism is achieved. Part of the main focus is the difference between spawning all of the threads at the beginning of a program and doing a /do which will spawn threads and kill causing threads to be consistently allocated and killed. The main difference is the overhead of being able to use synchronization methods on a program that spawns all of the threads at the beginning just like having a pool of threads to use. Using the method of spawning threads once and killing them at the end saves overtime of creating and deletion. 
