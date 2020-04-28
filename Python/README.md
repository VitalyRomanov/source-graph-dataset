#### Download Latest

---

[Nodes]()	[Edges]()

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