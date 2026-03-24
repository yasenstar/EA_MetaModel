# CREATE

```sql
CREATE (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:IS_SUPPORTED_BY]->(Business_Principle)<-[:SUPPORTS]-(Business_Capability:Business_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Principle),
(Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:IS_SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:IS_MOTIVATED_BY]-(Business_Objective)<-[:SUPPORTS]-(Business_Capability)<-[:IS_SUPPORTED_BY]-(Business_Objective)<-[:STRATEGIC_OBJECTIVES]-(`Business_Domain `:Business_Conceptual)<-[:OBJECTIVE_FOR_BUSINESS_DOMAINS]-(Business_Objective),
(Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual),
(External_Conceptual_Business_Event:Business_Conceptual)<-[:RAISES]-(:Business_Conceptual)-[:MEMBERS_OF]->(:Business_Conceptual)-[:PROVIDES]->(Business_Capability)-[:SUPERSEDES]->(Business_Capability)-[:IS_SUPERSEDED_BY]->(Business_Capability)-[:REQUIRES]->(:Business_Conceptual)-[:IS_REQUIRED_BY]->(Business_Capability)<-[:CONTAINS]-(`Business_Domain `)<-[:BELONGS_TO]-(Business_Capability)<-[:SUPPORTS]-(:Application_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Capability)<-[:IS_SUPPORTED_BY]-(:Business_Conceptual),
(`Business_Domain `)-[:SUPERSEDES]->(`Business_Domain `)-[:IS_SUPERSEDED_BY]->(`Business_Domain `),
(External_Conceptual_Business_Event)-[:MEMBERS_OF]->(:Business_Conceptual)<-[:MEMBERS_OF]-(:Business_Conceptual)
```

# MATCH

```sql
MATCH path0 = (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:IS_SUPPORTED_BY]->(Business_Principle)<-[:SUPPORTS]-(Business_Capability:Business_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Principle),
path1 = (Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:IS_SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:IS_MOTIVATED_BY]-(Business_Objective)<-[:SUPPORTS]-(Business_Capability)<-[:IS_SUPPORTED_BY]-(Business_Objective)<-[:STRATEGIC_OBJECTIVES]-(`Business_Domain `:Business_Conceptual)<-[:OBJECTIVE_FOR_BUSINESS_DOMAINS]-(Business_Objective),
path2 = (Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual),
path3 = (External_Conceptual_Business_Event:Business_Conceptual)<-[:RAISES]-(:Business_Conceptual)-[:MEMBERS_OF]->(:Business_Conceptual)-[:PROVIDES]->(Business_Capability)-[:SUPERSEDES]->(Business_Capability)-[:IS_SUPERSEDED_BY]->(Business_Capability)-[:REQUIRES]->(:Business_Conceptual)-[:IS_REQUIRED_BY]->(Business_Capability)<-[:CONTAINS]-(`Business_Domain `)<-[:BELONGS_TO]-(Business_Capability)<-[:SUPPORTS]-(:Application_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Capability)<-[:IS_SUPPORTED_BY]-(:Business_Conceptual),
path4 = (`Business_Domain `)-[:SUPERSEDES]->(`Business_Domain `)-[:IS_SUPERSEDED_BY]->(`Business_Domain `),
path5 = (External_Conceptual_Business_Event)-[:MEMBERS_OF]->(:Business_Conceptual)<-[:MEMBERS_OF]-(:Business_Conceptual)
RETURN path0, path1, path2, path3, path4, path5
```

# MERGE

```sql
MERGE (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:IS_SUPPORTED_BY]->(Business_Principle)<-[:SUPPORTS]-(Business_Capability:Business_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Principle)
MERGE (Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:IS_SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:IS_MOTIVATED_BY]-(Business_Objective)<-[:SUPPORTS]-(Business_Capability)<-[:IS_SUPPORTED_BY]-(Business_Objective)<-[:STRATEGIC_OBJECTIVES]-(`Business_Domain `:Business_Conceptual)<-[:OBJECTIVE_FOR_BUSINESS_DOMAINS]-(Business_Objective)
MERGE (Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual)
MERGE (External_Conceptual_Business_Event:Business_Conceptual)<-[:RAISES]-(:Business_Conceptual)-[:MEMBERS_OF]->(:Business_Conceptual)-[:PROVIDES]->(Business_Capability)-[:SUPERSEDES]->(Business_Capability)-[:IS_SUPERSEDED_BY]->(Business_Capability)-[:REQUIRES]->(:Business_Conceptual)-[:IS_REQUIRED_BY]->(Business_Capability)<-[:CONTAINS]-(`Business_Domain `)<-[:BELONGS_TO]-(Business_Capability)<-[:SUPPORTS]-(:Application_Conceptual)<-[:IS_SUPPORTED_BY]-(Business_Capability)<-[:IS_SUPPORTED_BY]-(:Business_Conceptual)
MERGE (`Business_Domain `)-[:SUPERSEDES]->(`Business_Domain `)-[:IS_SUPERSEDED_BY]->(`Business_Domain `)
MERGE (External_Conceptual_Business_Event)-[:MEMBERS_OF]->(:Business_Conceptual)<-[:MEMBERS_OF]-(:Business_Conceptual)
```