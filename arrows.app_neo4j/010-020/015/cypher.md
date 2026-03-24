# CREATE

```sql
CREATE (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:IS_SUPPORTED_BY]->(Business_Principle)<-[:SUPPORTS]-(Business_Capability:Business_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Principle),
(Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:IS_SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:IS_MOTIVATED_BY]-(Business_Objective)<-[:SUPPORTS]-(Business_Capability)<-[:IS_SUPPORTED_BY]-(Business_Objective)<-[:STRATEGIC_OBJECTIVES]-(`Business_Domain `:Business_Conceptual)<-[:OBJECTIVE_FOR_BUSINESS_DOMAINS]-(Business_Objective),
(Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual),
(Business_Capability)-[:SUPERSEDES]->(Business_Capability)-[:IS_SUPERSEDED_BY]->(Business_Capability)-[:REQUIRES]->(:Business_Conceptual)-[:IS_REQUIRED_BY]->(Business_Capability)<-[:CONTAINS]-(`Business_Domain `)<-[:BELONGS_TO]-(Business_Capability)<-[:SUPPORTS]-(:Application_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Capability),
(`Business_Domain `)-[:SUPERSEDES]->(`Business_Domain `)-[:IS_SUPERSEDED_BY]->(`Business_Domain `)
```

# MATCH

```sql
MATCH path0 = (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:IS_SUPPORTED_BY]->(Business_Principle)<-[:SUPPORTS]-(Business_Capability:Business_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Principle),
path1 = (Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:IS_SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:IS_MOTIVATED_BY]-(Business_Objective)<-[:SUPPORTS]-(Business_Capability)<-[:IS_SUPPORTED_BY]-(Business_Objective)<-[:STRATEGIC_OBJECTIVES]-(`Business_Domain `:Business_Conceptual)<-[:OBJECTIVE_FOR_BUSINESS_DOMAINS]-(Business_Objective),
path2 = (Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual),
path3 = (Business_Capability)-[:SUPERSEDES]->(Business_Capability)-[:IS_SUPERSEDED_BY]->(Business_Capability)-[:REQUIRES]->(:Business_Conceptual)-[:IS_REQUIRED_BY]->(Business_Capability)<-[:CONTAINS]-(`Business_Domain `)<-[:BELONGS_TO]-(Business_Capability)<-[:SUPPORTS]-(:Application_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Capability),
path4 = (`Business_Domain `)-[:SUPERSEDES]->(`Business_Domain `)-[:IS_SUPERSEDED_BY]->(`Business_Domain `)
RETURN path0, path1, path2, path3, path4
```

# MERGE

```sql
MERGE (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:IS_SUPPORTED_BY]->(Business_Principle)<-[:SUPPORTS]-(Business_Capability:Business_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Principle)
MERGE (Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:IS_SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:IS_MOTIVATED_BY]-(Business_Objective)<-[:SUPPORTS]-(Business_Capability)<-[:IS_SUPPORTED_BY]-(Business_Objective)<-[:STRATEGIC_OBJECTIVES]-(`Business_Domain `:Business_Conceptual)<-[:OBJECTIVE_FOR_BUSINESS_DOMAINS]-(Business_Objective)
MERGE (Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual)
MERGE (Business_Capability)-[:SUPERSEDES]->(Business_Capability)-[:IS_SUPERSEDED_BY]->(Business_Capability)-[:REQUIRES]->(:Business_Conceptual)-[:IS_REQUIRED_BY]->(Business_Capability)<-[:CONTAINS]-(`Business_Domain `)<-[:BELONGS_TO]-(Business_Capability)<-[:SUPPORTS]-(:Application_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Capability)
MERGE (`Business_Domain `)-[:SUPERSEDES]->(`Business_Domain `)-[:IS_SUPERSEDED_BY]->(`Business_Domain `)
```