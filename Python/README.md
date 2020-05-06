#### Download Latest

---

[Nodes](https://github.com/VitalyRomanov/source-graph-dataset/blob/master/Python/nodes.bz2?raw=true)	[Edges](https://github.com/VitalyRomanov/source-graph-dataset/blob/master/Python/edges.bz2?raw=true)

---

#### Usage Example

```python
>>> import pandas as pd
>>> nodes = pd.read_csv("nodes.bz2")
>>> edges = pd.read_csv("edges.bz2")
>>> nodes.head(5)
        id  type                                    serialized_name  component
0   100010  4096  ansible.module_utils.network.exos.facts.legacy...          0
1   100140  4096     ansible.module_utils.network.f5.common.fq_name          0
2  1004266  4096               django.utils.dateformat.DateFormat.b          0
3  1005754  4096           django.utils.html.MLStripper.handle_data          0
4  1005943  1024                           urllib.parse.uses_params          0
```
#### Data Format

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

| Python Nodes | Description     |
| ------------ | --------------- |
| 1            | Non-indexed     |
| 8            | Module          |
| 128          | Class           |
| 1024         | Global Variable |
| 2048         | Field           |
| 4096         | Function        |
| 8192         | Class Method    |

| Python Edges | Description                  |
| ------------ | ---------------------------- |
| 1            | Class Member / Module Member |
| 2            | Type use                     |
| 4            | Use                          |
| 8            | Function call                |
| 16           | Inheritance                  |
| 512          | Import                       |

#### Dataset Details

| Node Type          | Count  |
| ------------------ | ------ |
| Function           | 221822 |
| Class field        | 83077  |
| Class              | 35798  |
| Module             | 18097  |
| Class method       | 14953  |
| Non-indexed symbol | 853    |

| Edge Type      | Count  |
|----------------|--------|
| Call           | 614621 |
| Define/Contain | 431115 |
| Type Use       | 239543 |
| Import         | 121752 |
| Inheritance    | 26525  |

#### Indexed Packages

To create a pool of repositories we installed the following packages with dependencies using pip. In the result,  we had over 100 packages installed. The full list of packages is available in `source-graph-packages.txt`.

| Area                      | Python              |
| ------------------------- | ------------------- |
| Web application framework | Flask, Django       |
| Frameworks                | -                   |
| HTTP client               | Requests            |
| Crawler                   | Scrapy              |
| Machine Learning          | Sklearn, Tensorflow |
| Tabular                   | Pandas              |
| NLP                       | Spacy               |
| Visualization             | Bokeh, matplotlib   |
| Logging                   | Fabric              |
