# 網路科學作業四

## 簡介

- **ID:** &nbsp; &nbsp; 105下「網路科學」第四次作業
- **Due:** &nbsp; 08:00 @ June 4 (Sunday), 2017 

---
## 說明

 **percolation** 與 **epidemics** 的簡單模擬。
percolation模擬包含不同removal方式，epidemics模擬則是模擬均勻感染能力和非均勻感染能力的病毒之擴散動態。


**工具:** &nbsp; networkx, graph_tool, numpy

---
## Todo
- [x] Find a network of autonomous system
- [x] Proprocess to get readable format
- [x] Network properties
    - [x] Type、Nodes、Edges
- [x] Statistics
    - [x] Average degree、Density、transitivity、clustering coefficient
- [x] 1. Percolation with uniform removal of nodes
    - [x] Plot S versus number of nodes remaining
    - [x] Observation
- [x] 2. Percolation with non-uniform removal(in descending order of their degrees)
    - [x] Plot S versus number of nodes remaining
    - [x] Observation and compare the result to 1.
- [x] 3. Other removal approaches
    - [x] First approach
    - [x] Second approach
    - [x] Ovservation
- [x] 4. Epidemics 1
    - [x] coding
    - [x] observation
- [x] 5. Epidemics 2
    - [x] coding
    - [x] observation
- [ ] Bug
    - [x] NetworkXError: cannot tokenize u'graph' at (2, 1)

---
## 作業參考資料

### 講義
- [Percolation](https://ceiba.ntu.edu.tw/course/acbe31/content/percolation.pdf)


### Import modules
- [AttributeError: 'module' object has no attribute 'vertex_percolation'](https://stackoverflow.com/questions/28178705/graph-draw-missing-from-graph-tool-osx)
    
    要把import graph_tool as gt 改成import graph_tool.all as gt 才對


### Preprocessing
- [NetworkXError: cannot tokenize u'graph' at (2,1)](https://stackoverflow.com/questions/32895291/unexpected-error-reading-gml-graph/32897276#32897276)
  
  Makan的回答才是正解，因爲GML檔的格式不對，可以用sed來轉檔。
Run this command: &nbsp; 
    
        sed 'N;s/\s\+\[/ \[/g;P;D'  <XXX.gml  >XXX-new.gml 


### Load network
- [Load graph (graph_tool)](https://graph-tool.skewed.de/static/doc/quickstart.html#graph-i-o)


### Description of the network
- [Directed? &nbsp;&nbsp;&nbsp; nx.is_directed(G)](https://stackoverflow.com/questions/33620839/testing-if-a-graph-is-directed-or-undirected-graph-from-edgelist-file)



### Statistics

- [Density](https://networkx.github.io/documentation/networkx-1.9/reference/generated/networkx.classes.function.density.html)

- [Transitivity](https://networkx.github.io/documentation/networkx-1.10/reference/generated/networkx.algorithms.cluster.transitivity.html#networkx.algorithms.cluster.transitivity)

- [Clustering coefficient](https://networkx.github.io/documentation/networkx-1.10/reference/generated/networkx.algorithms.cluster.average_clustering.html#networkx.algorithms.cluster.average_clustering)


### 第一小題

- [vertex percolation (graph_tool)](https://graph-tool.skewed.de/static/doc/topology.html#graph_tool.topology.vertex_percolation)

- [Numpy random shuffle](https://docs.scipy.org/doc/numpy/reference/generated/numpy.random.shuffle.html)


### 第二小題

- [v.out_degree()](https://graph-tool.skewed.de/static/doc/graph_tool.html#graph_tool.Vertex.out_degree)


### 第三小題

- [eigenvector centrality (graph_gool)](https://graph-tool.skewed.de/static/doc/centrality.html#graph_tool.centrality.eigenvector)

- [graph deep copy (graph tool)](https://graph-tool.skewed.de/static/doc/graph_tool.html#graph_tool.Graph)
    
    g.copy()

- [Remove vertex (graph_tool)](https://graph-tool.skewed.de/static/doc/graph_tool.html#graph_tool.Graph.remove_vertex)
    
    g.remove_vertex(node)


- [Getting “ValueError: invalid vertex descriptor” when removing vertices](https://stackoverflow.com/questions/33614542/getting-valueerror-invalid-vertex-descriptor-when-removing-vertices)
    
    必須先deep copy一個graph，才能做remove的動作，否則原先的vertices被移除之後就不屬於該graph，會導致此error

- 註：不能用remove vertex的方法，因為vertex的index會重排，要用remove edge的方法，但是因為時間緊迫，所以將錯就錯了＠＠


### 第四小題

- [Epdemics 1 (lecture slide)](https://ceiba.ntu.edu.tw/course/acbe31/content/epidemics-1.pdf)

- [Epdemics 2 (lecture slide)](https://ceiba.ntu.edu.tw/course/acbe31/content/epidemics-2.pdf)
 
- [Get the neighbors of a node (networkx)](https://networkx.github.io/documentation/networkx-1.10/reference/generated/networkx.Graph.neighbors.html)
    G.neighbors(node)

- [Sum of all values in a Python dict](https://stackoverflow.com/questions/4880960/sum-of-all-values-in-a-python-dict)


### 第五小題



---
## 資源連結
- [作業檔](https://ceiba.ntu.edu.tw/course/acbe31/hw/Homework-4.pdf)

- [Data Source](http://www-personal.umich.edu/~mejn/netdata/)


