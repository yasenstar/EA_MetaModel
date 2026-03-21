# Load Data into Graph DB

- [Load Data into Graph DB](#load-data-into-graph-db)
  - [Load from CSV](#load-from-csv)

## Load from CSV

```SQL
LOAD CSV WITH HEADERS FROM 'file:///D:/github/EA_MetaModel/graphdb_inputs/meta-model.csv' AS row
MERGE (s:$(row.source) {
    Name: row.source
})
MERGE (t:$(row.target) {
    Name: row.target
})
MERGE (s)-[r:$(row.relation)]->(t)
ON CREATE SET 
    s.createdAt = datetime(),
    r.createdAt = datetime(),
    t.createdAt = datetime()
ON MATCH SET
    s.updatedAt = datetime(),
    r.updatedAt = datetime(),
    t.updatedAt = datetime()
```