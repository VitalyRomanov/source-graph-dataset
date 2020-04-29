#### Usage

1. Index source code using Sourcetrail
2. Extract graph information
```bash
sqlite sourcetrail_project.srctrldb < extract.sql
```
3. Normalize node names
```bash
python sourcetrail-node-name-merge.py nodes.csv
```