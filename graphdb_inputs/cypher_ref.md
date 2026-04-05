# Load Data into Graph DB
- [Load Data into Graph DB](#load-data-into-graph-db)
  - [Load from CSV - Source, Relation, Target with Label](#load-from-csv---source-relation-target-with-label)
  - [Show all Elements and Relations](#show-all-elements-and-relations)
  - [Show Graph Schema](#show-graph-schema)

## Load from CSV - Source, Relation, Target with Label

```SQL
LOAD CSV WITH HEADERS FROM 'file:///D:/github/EA_MetaModel/graphdb_inputs/meta-model.csv' AS row
MERGE (s:$(row.source) {
    Name: row.source
})
MERGE (t:$(row.target) {
    Name: row.target
})
SET
    s.Label = row.source_label,
    t.Label = row.target_label
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

## Show all Elements and Relations

```SQL
MATCH (n)-[r]-(m) return n, r, m
```

## Show Graph Schema

```SQL
call db.schema.visualization
```