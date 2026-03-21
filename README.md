# Enterprise Architecture (EA) MetaModel

Master EAS Meta-Model from Ontology and Graph Perspective

- [Enterprise Architecture (EA) MetaModel](#enterprise-architecture-ea-metamodel)
  - [About EAS Meta-Model](#about-eas-meta-model)
  - [Why this Repository?](#why-this-repository)
  - [Approaching of Modeling](#approaching-of-modeling)
  - [Toolsets for Modeling](#toolsets-for-modeling)
  - [Contents for the Meta-Model](#contents-for-the-meta-model)

## About EAS Meta-Model

EAS stands for [Enterprise Architecture Solution](https://enterprise-architecture.org/), founded in 2000, and launched its first open source EA tool - The Essential Project - in March 2009, which is the tool I've ever touched base for playing from 2023 till now.

When I met Essential Open Source EA Tool, I, and our architecture team, had already adopted several other commercial EA Tools, and had decided adopting the Archi (Open Source ArchiMate Modeling Tool) from 2021, Archi is lightweighted, flexible tool which can support our team's EA Repository in a collaborative approach, but you had to build it from sctrach, while, Essential tool attracted me so much from its out-of-the-box rich meta-model.

[![Check here for Essential Meta Model Overview in Essential University](img/Essential-Meta-Model-Logo.png)](https://enterprise-architecture.org/university/essential-meta-model-overview/#)

From learning and practicing the Essential Meta-Model into our real enterprise architecture repository, I can feel deeply on the philosophy of how Essential view Enterprise Architecture, which are listed as below
- the scope of enterprise architecture in an enterprise is the enterprise itself, not any part of it
- enterprise is living in the industrial eco-system, so does enterprise architecture
- it is everyone's enterprise architecture, everyone plays modeler, contributor, player and reviewer roles in variable stages
- no any single EA tool fits all, the key is multiple tools are working jointly, and Essential tool offers extendable meta-model for building common repository
- EA tool is not the boring "spreadsheet", it must be easy of input/output and connecting the 'dots" which meaningful to the stakeholders

## Why this Repository?

If you intend to play with Essential Open Source (OS) EA Tool edition, from here https://enterprise-architecture.org/products/essential-open-source/, you can download and setup, once configured well, you may start to enjoy the pre-defined meta model for your EA repository.

However, since the open sourse tool was started from 2009, it's still locked in certain "old" software versions:

| Required Components | Essential OS Version | Latest Available Version |
| --- | --- | --- |
| Java Runtime Environment | Java 1.8 | openjdk 21.0.5 2024-10-15 LTS |
| Protege Ontology Editor  | 3.5 | 5.6.9 |
| Apache Tomcat | 8.5 or 9.0 ONLY | 11.0.18 |

*Note: as of date 2026/03/17*

For Java, we can keep both Java version co-exist in one machine, similar to Protege, but for Tomcat, as I had to leave it to v9, there're specific vulnerabilities need to be handled since our company are already in the higher version for years, that's in more challenge since the Essential Viewer is deployed in the server end.

Furthermore, the Essential meta-model is so richness on its coverage, even I've tried to add more and more aspect of our EA repository elements, I believe I only utilize the small portion of its full scope.

Thus, I'd like to use this repository to record my practice step-by-step, on

1. Deep-dive Essential Meta-Model Structure, analyze its relationships among every layer, view and element
2. Build this meta-model in ontology view, using latest Protege ontology editor (current v5.6.7)
3. Build the meta-model into graph view, using Neo4j graph database, and
4. Document lessons learnt from Essential University on Meta-Model into the detail chapters

After the practice, I hope there will be one re-usable ontology meta-model RDF/OWL file as the template for any enterprise architect using, in their latest Protege version, and having one graph to be viewed visually on the relationship.

It would be a long journey, I'll keep tracking any updated changes from EAS, and will record the hands-on activities into one video series (let's target within 1000 lectures :slightly_smiling_face:)

## Approaching of Modeling

1. Build `Class` hierarchy in Protege v5.6+, base on `Class Browser` in EAS
2. For every `Class` in EAS, examine detail from `Classes Editor` for modeling its `Documentation`, `Role`, and especially `Template Slots` (mapping to `Object Property` or `Data Property`)
3. Create `Element` and `Relationship` concepts into a CSV file
4. Load CSV into Neo4j graph database
5. Learn by typing everything, no Copy and Paste!

## Toolsets for Modeling

- [Essential Open Source EA Tool](https://enterprise-architecture.org/products/essential-open-source/)
- [Protege / Protégé Desktop](https://protege.stanford.edu/software.php#desktop-protege)
- [Neo4j Graph Database](https://neo4j.com/product/neo4j-graph-database/)
  - [Neo4j Deployment Center](https://neo4j.com/deployment-center/)
  - [Graph prototyping - arrows.app](https://arrows.app/)
- [Visual Studio Code](https://code.visualstudio.com/download)

## Contents for the Meta-Model

- [Meta Model in wikipedia](https://en.wikipedia.org/wiki/Metamodeling)
- [Metamodels in ISO 42010](./ref/Hilliard-On-Metamodels-in-42010.pdf): Check here for [ISO 42010](https://www.iso.org/standard/74393.html)
- [Enterprise Architecture Reference Frameworks](./eaframeworks/README.md)

---

Stay tunes, feel free to raise your comments and suggestions! 
Thanks for supporting me!

Last updated by Xiaoqi Zhao, 3/21/2026