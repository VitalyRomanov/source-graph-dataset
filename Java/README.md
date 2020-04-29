#### Download Latest

---

[Nodes](https://gitlab.com/v.romanov/java-source-graph/-/raw/master/02_largest_component/edges_component_0.csv.bz2)	[Edges](https://gitlab.com/v.romanov/java-source-graph/-/raw/master/02_largest_component/nodes_component_0.csv.bz2)

#### Usage Example

```python
>>> import pandas as pd
>>> nodes = pd.read_csv("nodes.bz2")
>>> edges = pd.read_csv("edges.bz2")
>>> nodes.head(5)
   id  type                serialized_name  component
0   4    32  edu.stanford.nlp.coref.hybrid          0
1   5    32         edu.stanford.nlp.coref          0
2   6    32               edu.stanford.nlp          0
3   7    32                   edu.stanford          0
4   8    32                            edu          0
```

#### Data Format
---

The file with nodes contains information in the format of compressed CSV file. Note that `Pandas` allows to load compressed CSV files by default using `read_csv`. 

Nodes entry format is 
```
id, type, serialized_name, component
```

The column `id` stores unique integer identifier for every node. The values in `component` column indicate to which component this node belongs. Currently all nodes belong to component `0`.

Edges entry format is 
```
id, type, source_node_id, target_node_id
```

`id` is a unique edge identifier. 

#### Types Description

Nodes and edges in the dataset have different types. Type description is given in the tables below

| Java Nodes | Description         |
| ---------- | ------------------- |
| 1          | Non-indexed         |
| 4          | Built-in type       |
| 32         | Non-indexed package |
| 128        | Class               |
| 256        | Interface           |
| 512        | Annotation          |
| 2048       | Field               |
| 8192       | Method              |
| 16384      | Enum                |
| 32768      | Enum constant       |
| 131072     | Type parameter      |

| Java Edges | Description         |
| ---------- | ------------------- |
| 1          | Function Definition |
| 2          | Type use            |
| 4          | Use                 |
| 8          | Function call       |
| 16         | Inheritance         |
| 32         | Override            |
| 64         | Type Argument       |
| 512        | Import              |
| 4096       | Annotation use      |

#### Dataset Details

| Node Type           | Count  |
| ------------------- | ------ |
| Method              | 287393 |
| Field               | 95983  |
| Class               | 42329  |
| Non-Indexed Symbol  | 30438  |
| Type Parameter      | 5885   |
| Enum Constant       | 4835   |
| Non-Indexed Package | 3792   |
| Interface           | 3366   |
| Annotation          | 1012   |
| Enum                | 919    |
| Built-In Type       | 9      |

| Edge Type      | Count  |
| -------------- | ------ |
| Type use       | 989725 |
| Call           | 817408 |
| Define/Contain | 475303 |
| Use            | 368910 |
| Annotation use | 168862 |
| Override       | 75186  |
| Inheritance    | 32018  |
| Is type        | 24105  |

#### Indexed Packages

A set of GitHub repositories was downloaded to create this dataset. A full list of repositories can be found in `source-graph-repositories.txt`. 

| Area                      | Java                           |
| ------------------------- | ------------------------------ |
| Web application framework | JHipster                       |
| Frameworks                | Spring Framework, Spring Boot, |
| HTTP client               | Apache HTTP Client, Unirest,   |
| Crawler                   | WebMagic, crawler4j            |
| Machine Learning          | Deeplearning4j, Mahout, Weka   |
| Tabular                   | Tablesaw                       |
| NLP                       | Opennlp, StanfordNLP,          |
| Visualization             | Thingsboard,                   |
| Logging                   | log4j                          |

#### 

