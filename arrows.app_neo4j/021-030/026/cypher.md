# CREATE

```sql
CREATE (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:SUPPORTED_BY]->(Business_Principle)<-[:SUPPORTS]-(Business_Capability:Business_Conceptual)<-[:SUPPORTED_BY]-(Business_Principle),
(Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:MOTIVATED_BY]-(Business_Objective)<-[:SUPPORTS]-(Business_Capability)<-[:SUPPORTED_BY]-(Business_Objective)<-[:STRATEGIC_OBJECTIVES]-(`Business_Domain `:Business_Conceptual)<-[:OBJECTIVE_FOR_BUSINESS_DOMAINS]-(Business_Objective),
(Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual),
(External_Business_Role_Type:Business_Conceptual)<-[:RAISED_BY]-(External_Conceptual_Business_Event:Business_Conceptual)<-[:RAISES]-(External_Business_Role_Type)-[:MEMBERS_OF]->(`Business_Role_Type `:Business_Conceptual)-[:PROVIDES]->(Business_Capability)-[:SUPERSEDES]->(Business_Capability)-[:SUPERSEDED_BY]->(Business_Capability)-[:REQUIRES]->(:Business_Conceptual)-[:REQUIRED_BY]->(Business_Capability)<-[:CONTAINS]-(`Business_Domain `)<-[:BELONGS_TO]-(Business_Capability)<-[:SUPPORTS]-(:Application_Conceptual)<-[:SUPPORTED_BY]-(Business_Capability)<-[:SUPPORTED_BY]-(Product_Concept:Business_Conceptual)<-[:REALIZES]-(Product_Type:Business_Logical)<-[:REALIZED_BY]-(Product_Concept),
(`Business_Domain `)-[:SUPERSEDES]->(`Business_Domain `)-[:SUPERSEDED_BY]->(`Business_Domain `),
(External_Conceptual_Business_Event)-[:MEMBERS_OF]->(:Business_Conceptual)<-[:MEMBERS_OF]-(:Business_Conceptual),
(Business_Capability_Chain:Business_Conceptual)<-[:DEFINED_BY]-(Business_Capability)<-[:DEFINES]-(Business_Capability_Chain)-[:MEMBERS_OF]->(:Business_Conceptual)<-[:MEMBERS_OF]-(Business_Capability_Chain_Type:Business_Conceptual)<-[:USES]-(Business_Capability_Chain)<-[:USED_BY]-(Business_Capability_Chain_Type),
(Value_Stream:Business_Conceptual)-[:TRIGGERED_BY]->(Business_Role:Business_Logical)-[:TRIGGERS]->(Value_Stream)-[:CONTRAINS]->(Value_Stage:Business_Conceptual)-[:BELONGS_TO]->(Value_Stream)<-[:TRIGGERS]-(`Business_Role_Type `)<-[:TRIGGERED_BY]-(Value_Stream)<-[:SUPPORTS]-(Product_Type)<-[:SUPPORTED_BY]-(Value_Stream),
(Business_Role)-[:PARTICIPATES]->(Value_Stage)-[:SUPERSEDES]->(Value_Stage)-[:SUPERSEDED_BY]->(Value_Stage)-[:REQUIRES]->(Business_Capability)-[:REQUIRED_BY]->(Value_Stage)<-[:PARTICIPATES]-(`Business_Role_Type `)<-[:PARTICIPATED_BY]-(Value_Stage)-[:PARTICIPATED_BY]->(Business_Role)-[:SUPERSEDES]->(Business_Role)-[:SUPERSEDED_BY]->(Business_Role)-[:RAISES]->(External_Business_Event:Business_Logical)-[:RAISED_BY]->(Business_Role)-[:OWNS]->(Business_Process_Type:Business_Logical)<-[:PERFORMS]-(Business_Role)<-[:OWNED_BY]-(Business_Process_Type)-[:PERFORMED_BY]->(Business_Role)-[:OPERATES_AT]->(:Business_Logical),
(Business_Role)-[:REALIZES]->(`Business_Role_Type `)-[:REALIZED_BY]->(Business_Role),
(:Business_Logical)-[:MEMBERS_OF]->(:Business_Logical)<-[:MEMBERS_OF]-(External_Business_Event),
(Product_Type)-[:INSTANCES]->(:Business_Logical)-[:INSTANCE_OF]->(Product_Type)<-[:PRODUCES]-(Business_Process_Type)<-[:PRODUCED_BY]-(Product_Type),
(:Business_Logical)-[:MEMBERS_OF]->(Business_Process_Type)-[:BELONGS_TO]->(:Business_Logical)-[:CONTAINS]->(Business_Process_Type)-[:SUPPORTS]->(Value_Stage)-[:SUPPORTED_BY]->(Business_Process_Type)<-[:MEMBERS_OF]-(Business_Process:Business_Logical)-[:REALIZES]->(Business_Capability)-[:REALIZED_BY]->(Business_Process)-[:SUPERSEDES]->(Business_Process)-[:SUPERSEDED_BY]->(Business_Process),
()-[:MEMBERS_OF]->(Business_Process_Type)
```

# MATCH

```sql
MATCH path0 = (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:SUPPORTED_BY]->(Business_Principle)<-[:SUPPORTS]-(Business_Capability:Business_Conceptual)<-[:SUPPORTED_BY]-(Business_Principle),
path1 = (Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:MOTIVATED_BY]-(Business_Objective)<-[:SUPPORTS]-(Business_Capability)<-[:SUPPORTED_BY]-(Business_Objective)<-[:STRATEGIC_OBJECTIVES]-(`Business_Domain `:Business_Conceptual)<-[:OBJECTIVE_FOR_BUSINESS_DOMAINS]-(Business_Objective),
path2 = (Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual),
path3 = (External_Business_Role_Type:Business_Conceptual)<-[:RAISED_BY]-(External_Conceptual_Business_Event:Business_Conceptual)<-[:RAISES]-(External_Business_Role_Type)-[:MEMBERS_OF]->(`Business_Role_Type `:Business_Conceptual)-[:PROVIDES]->(Business_Capability)-[:SUPERSEDES]->(Business_Capability)-[:SUPERSEDED_BY]->(Business_Capability)-[:REQUIRES]->(:Business_Conceptual)-[:REQUIRED_BY]->(Business_Capability)<-[:CONTAINS]-(`Business_Domain `)<-[:BELONGS_TO]-(Business_Capability)<-[:SUPPORTS]-(:Application_Conceptual)<-[:SUPPORTED_BY]-(Business_Capability)<-[:SUPPORTED_BY]-(Product_Concept:Business_Conceptual)<-[:REALIZES]-(Product_Type:Business_Logical)<-[:REALIZED_BY]-(Product_Concept),
path4 = (`Business_Domain `)-[:SUPERSEDES]->(`Business_Domain `)-[:SUPERSEDED_BY]->(`Business_Domain `),
path5 = (External_Conceptual_Business_Event)-[:MEMBERS_OF]->(:Business_Conceptual)<-[:MEMBERS_OF]-(:Business_Conceptual),
path6 = (Business_Capability_Chain:Business_Conceptual)<-[:DEFINED_BY]-(Business_Capability)<-[:DEFINES]-(Business_Capability_Chain)-[:MEMBERS_OF]->(:Business_Conceptual)<-[:MEMBERS_OF]-(Business_Capability_Chain_Type:Business_Conceptual)<-[:USES]-(Business_Capability_Chain)<-[:USED_BY]-(Business_Capability_Chain_Type),
path7 = (Value_Stream:Business_Conceptual)-[:TRIGGERED_BY]->(Business_Role:Business_Logical)-[:TRIGGERS]->(Value_Stream)-[:CONTRAINS]->(Value_Stage:Business_Conceptual)-[:BELONGS_TO]->(Value_Stream)<-[:TRIGGERS]-(`Business_Role_Type `)<-[:TRIGGERED_BY]-(Value_Stream)<-[:SUPPORTS]-(Product_Type)<-[:SUPPORTED_BY]-(Value_Stream),
path8 = (Business_Role)-[:PARTICIPATES]->(Value_Stage)-[:SUPERSEDES]->(Value_Stage)-[:SUPERSEDED_BY]->(Value_Stage)-[:REQUIRES]->(Business_Capability)-[:REQUIRED_BY]->(Value_Stage)<-[:PARTICIPATES]-(`Business_Role_Type `)<-[:PARTICIPATED_BY]-(Value_Stage)-[:PARTICIPATED_BY]->(Business_Role)-[:SUPERSEDES]->(Business_Role)-[:SUPERSEDED_BY]->(Business_Role)-[:RAISES]->(External_Business_Event:Business_Logical)-[:RAISED_BY]->(Business_Role)-[:OWNS]->(Business_Process_Type:Business_Logical)<-[:PERFORMS]-(Business_Role)<-[:OWNED_BY]-(Business_Process_Type)-[:PERFORMED_BY]->(Business_Role)-[:OPERATES_AT]->(:Business_Logical),
path9 = (Business_Role)-[:REALIZES]->(`Business_Role_Type `)-[:REALIZED_BY]->(Business_Role),
path10 = (:Business_Logical)-[:MEMBERS_OF]->(:Business_Logical)<-[:MEMBERS_OF]-(External_Business_Event),
path11 = (Product_Type)-[:INSTANCES]->(:Business_Logical)-[:INSTANCE_OF]->(Product_Type)<-[:PRODUCES]-(Business_Process_Type)<-[:PRODUCED_BY]-(Product_Type),
path12 = (:Business_Logical)-[:MEMBERS_OF]->(Business_Process_Type)-[:BELONGS_TO]->(:Business_Logical)-[:CONTAINS]->(Business_Process_Type)-[:SUPPORTS]->(Value_Stage)-[:SUPPORTED_BY]->(Business_Process_Type)<-[:MEMBERS_OF]-(Business_Process:Business_Logical)-[:REALIZES]->(Business_Capability)-[:REALIZED_BY]->(Business_Process)-[:SUPERSEDES]->(Business_Process)-[:SUPERSEDED_BY]->(Business_Process),
path13 = ()-[:MEMBERS_OF]->(Business_Process_Type)
RETURN path0, path1, path2, path3, path4, path5, path6, path7, path8, path9, path10, path11, path12, path13
```

# MERGE

```sql
MERGE (Business_Principle:Business_Conceptual)-[:SUPPORTS]->(Business_Objective:Business_Conceptual)-[:SUPPORTED_BY]->(Business_Principle)<-[:SUPPORTS]-(Business_Capability:Business_Conceptual)<-[:SUPPORTED_BY]-(Business_Principle)
MERGE (Business_Objective)-[:SUPERSEDES]->(Business_Objective)-[:SUPERSEDED_BY]->(Business_Objective)<-[:MOTIVATES]-(Business_Driver:Business_Conceptual)<-[:MOTIVATED_BY]-(Business_Objective)<-[:SUPPORTS]-(Business_Capability)<-[:SUPPORTED_BY]-(Business_Objective)<-[:STRATEGIC_OBJECTIVES]-(`Business_Domain `:Business_Conceptual)<-[:OBJECTIVE_FOR_BUSINESS_DOMAINS]-(Business_Objective)
MERGE (Business_Driver)-[:HAS_APPLICATION_IMPLICATIONS]->(:Application_Conceptual)
MERGE (External_Business_Role_Type:Business_Conceptual)<-[:RAISED_BY]-(External_Conceptual_Business_Event:Business_Conceptual)<-[:RAISES]-(External_Business_Role_Type)-[:MEMBERS_OF]->(`Business_Role_Type `:Business_Conceptual)-[:PROVIDES]->(Business_Capability)-[:SUPERSEDES]->(Business_Capability)-[:SUPERSEDED_BY]->(Business_Capability)-[:REQUIRES]->(:Business_Conceptual)-[:REQUIRED_BY]->(Business_Capability)<-[:CONTAINS]-(`Business_Domain `)<-[:BELONGS_TO]-(Business_Capability)<-[:SUPPORTS]-(:Application_Conceptual)<-[:SUPPORTED_BY]-(Business_Capability)<-[:SUPPORTED_BY]-(Product_Concept:Business_Conceptual)<-[:REALIZES]-(Product_Type:Business_Logical)<-[:REALIZED_BY]-(Product_Concept)
MERGE (`Business_Domain `)-[:SUPERSEDES]->(`Business_Domain `)-[:SUPERSEDED_BY]->(`Business_Domain `)
MERGE (External_Conceptual_Business_Event)-[:MEMBERS_OF]->(:Business_Conceptual)<-[:MEMBERS_OF]-(:Business_Conceptual)
MERGE (Business_Capability_Chain:Business_Conceptual)<-[:DEFINED_BY]-(Business_Capability)<-[:DEFINES]-(Business_Capability_Chain)-[:MEMBERS_OF]->(:Business_Conceptual)<-[:MEMBERS_OF]-(Business_Capability_Chain_Type:Business_Conceptual)<-[:USES]-(Business_Capability_Chain)<-[:USED_BY]-(Business_Capability_Chain_Type)
MERGE (Value_Stream:Business_Conceptual)-[:TRIGGERED_BY]->(Business_Role:Business_Logical)-[:TRIGGERS]->(Value_Stream)-[:CONTRAINS]->(Value_Stage:Business_Conceptual)-[:BELONGS_TO]->(Value_Stream)<-[:TRIGGERS]-(`Business_Role_Type `)<-[:TRIGGERED_BY]-(Value_Stream)<-[:SUPPORTS]-(Product_Type)<-[:SUPPORTED_BY]-(Value_Stream)
MERGE (Business_Role)-[:PARTICIPATES]->(Value_Stage)-[:SUPERSEDES]->(Value_Stage)-[:SUPERSEDED_BY]->(Value_Stage)-[:REQUIRES]->(Business_Capability)-[:REQUIRED_BY]->(Value_Stage)<-[:PARTICIPATES]-(`Business_Role_Type `)<-[:PARTICIPATED_BY]-(Value_Stage)-[:PARTICIPATED_BY]->(Business_Role)-[:SUPERSEDES]->(Business_Role)-[:SUPERSEDED_BY]->(Business_Role)-[:RAISES]->(External_Business_Event:Business_Logical)-[:RAISED_BY]->(Business_Role)-[:OWNS]->(Business_Process_Type:Business_Logical)<-[:PERFORMS]-(Business_Role)<-[:OWNED_BY]-(Business_Process_Type)-[:PERFORMED_BY]->(Business_Role)-[:OPERATES_AT]->(:Business_Logical)
MERGE (Business_Role)-[:REALIZES]->(`Business_Role_Type `)-[:REALIZED_BY]->(Business_Role)
MERGE (:Business_Logical)-[:MEMBERS_OF]->(:Business_Logical)<-[:MEMBERS_OF]-(External_Business_Event)
MERGE (Product_Type)-[:INSTANCES]->(:Business_Logical)-[:INSTANCE_OF]->(Product_Type)<-[:PRODUCES]-(Business_Process_Type)<-[:PRODUCED_BY]-(Product_Type)
MERGE (:Business_Logical)-[:MEMBERS_OF]->(Business_Process_Type)-[:BELONGS_TO]->(:Business_Logical)-[:CONTAINS]->(Business_Process_Type)-[:SUPPORTS]->(Value_Stage)-[:SUPPORTED_BY]->(Business_Process_Type)<-[:MEMBERS_OF]-(Business_Process:Business_Logical)-[:REALIZES]->(Business_Capability)-[:REALIZED_BY]->(Business_Process)-[:SUPERSEDES]->(Business_Process)-[:SUPERSEDED_BY]->(Business_Process)
MERGE ()-[:MEMBERS_OF]->(Business_Process_Type)
```