# Temporal-k-Core-Query-Project

## ABSTRACT

Querying cohesive subgraphs on temporal graphs with time constraints is valuable since it reveals underlying communities that emerge during specific meaningful time intervals. In this paper, we study a general Temporal k-Core Query (TCQ) problem: find all distinct k-cores that exist within a given time interval in a temporal graph, which can be extended to many interesting applications. This problem is challenging due to the massive number of subintervals that possibly induce different k-cores. For that, we propose a novel Temporal Core Decomposition (TCD) algorithm that decrementally induces temporal k-cores from the previously induced ones and thus reduces **intra-core** redundant computation significantly. Then, we introduce an intuitive property named Tightest Time Interval (TTI) of temporal k-core, and design an optimization technique that leverages TTI to predict which subintervals will induce identical k-cores and safely prunes the subintervals in advance, thereby eliminating **inter-core** redundant computation. The complexity of optimized TCD (OTCD) algorithm no longer depends on the span of query time interval but only the scale of final results, which means OTCD algorithm is scalable. Moreover, we propose a compact in-memory data structure named Temporal Edge List (TEL) to implement OTCD algorithm efficiently in physical level. TEL can be updated instantly with new incoming temporal edges, and thus our approach can also deal with dynamic temporal graphs. We compare OTCD algorithm with the latest historical k-core query on several real-world temporal graphs, and observe that OTCD algorithm outperforms it by three orders of magnitude, while OTCD algorithm needs none precomputed index.

## File Description
1. TCD.cpp: Source code of TCD, OTCD
2. i-PHC.cpp: Source code of iPHC-TCQ

## Documentation
Experiments are conducted on Windows10 x64 with 64GB memory with Visual Studio 2019. At least 32GB memory is recommended. The code is implemented with pure C++ including C++17 features, so a compiler supporting latest C++ feature is recommended. The confirmed steps of compiling the source code are provided below:

1. Create a VS 2019 project and add the source code(i-PHC.cpp OR TCD.cpp) to the project.
2. Build the project with x64 configuration and generate the executable file.
3. Add the graph file and testcase file for testing to the directory of executable file.
4. Run the executable file with command.

The command for running the executable file is set as follows:```.\[exe file] [graph file] [testcase file]```, where graph file should only contain the edge set in form of "u v t", with **SPACE** as separator, and testcase file should only contain a group of queries line by line, in form of "ts te k" with **TAB** as separator. Please refer to the given example: graph-format.txt, query-format.txt.

After running the executable file, queries in the testcase file will be processed one by one through TCD and OTCD. For each processed query, multiple lines containing information of the query will be printed:
1. The name of graph
2. The processed query
3. The time consumed by TCD
4. The time consumed by OTCD
5. Total number of obtained temporal k-core in query

## Reproduction
To facilitate reproduction of experiments in paper, we create two customized packages which contains VS2019 project and testcases for experiments. The link is shared below:
link: https://pan.baidu.com/s/1cCG0jOofbi1jW1-2XmGxbw
password: dn3s


## Contact
If you have any questions, contact us by sending an email to clock@whu.edu.cn / thomasyang@whu.edu.cn
