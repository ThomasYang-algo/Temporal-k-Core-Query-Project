# Temporal-k-Core-Query-Project

***

## ABSTRACT

Querying cohesive subgraphs on temporal graphs with time constraints is valuable since it reveals underlying communities that emerge during specific meaningful time intervals. In this paper, we study a general Temporal $k$-Core Query (TCQ) problem: find all distinct $k$-cores that exist within a given time interval in a temporal graph, which can be extended to many interesting applications. This problem is challenging due to the massive number of subintervals that possibly induce different $k$-cores. For that, we propose a novel Temporal Core Decomposition (TCD) algorithm that decrementally induces temporal $k$-cores from the previously induced ones and thus reduces ``intra-core'' redundant computation significantly. Then, we introduce an intuitive property named Tightest Time Interval (TTI) of temporal $k$-core, and design an optimization technique that leverages TTI to predict which subintervals will induce identical $k$-cores and safely prunes the subintervals in advance, thereby eliminating ``inter-core'' redundant computation. The complexity of optimized TCD (OTCD) algorithm no longer depends on the span of query time interval but only the scale of final results, which means OTCD algorithm is scalable. Moreover, we propose a compact in-memory data structure named Temporal Edge List (TEL) to implement OTCD algorithm efficiently in physical level. TEL can be updated instantly with new incoming temporal edges, and thus our approach can also deal with dynamic temporal graphs. We compare OTCD algorithm with the latest historical $k$-core query on several real-world temporal graphs, and observe that OTCD algorithm outperforms it by three orders of magnitude, while OTCD algorithm needs none precomputed index.

***

## File Description

