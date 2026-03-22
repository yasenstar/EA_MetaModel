# CREATE

```sql
CREATE (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:IS_SUPPORTED_BY]->(Business_Principle),
(Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:IS_SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:IS_MOTIVATED_BY]-(Business_Objective),
(Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual)
```

# MATCH

```sql
MATCH path0 = (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:IS_SUPPORTED_BY]->(Business_Principle),
path1 = (Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:IS_SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:IS_MOTIVATED_BY]-(Business_Objective),
path2 = (Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual)
RETURN path0, path1, path2
```

# MERGE

```sql
MERGE (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:IS_SUPPORTED_BY]->(Business_Principle)
MERGE (Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:IS_SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:IS_MOTIVATED_BY]-(Business_Objective)
MERGE (Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual)
```