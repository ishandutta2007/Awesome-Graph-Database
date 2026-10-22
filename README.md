# Awesome-Graph-Database

## Top Graph Database Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Property Graph Traversal, RDF/SPARQL Reasoning & Self-Hosted Graph Engines*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Graph Databases**. These systems store data as nodes and edges, enabling efficient traversal of complex relationships—powering recommendation engines, fraud detection, knowledge graphs, and GraphRAG pipelines for LLM applications.



**Examples** include Neo4j Aura, Amazon Neptune, TigerGraph Cloud, ArangoDB Oasis (now AMP), Memgraph Cloud, Azure Cosmos DB Gremlin, Stardog, and TerminusDB (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, Cypher compatibility, and transparent graph storage—ideal for teams that need data sovereignty, avoid per-seat or per-GB SaaS pricing, and require auditable graph infrastructure. The open-source landscape is anchored by **Neo4j Community** (the ecosystem standard with Cypher), **Memgraph** (in-memory speed with Cypher compatibility), **Apache AGE** (graph queries inside PostgreSQL), and **JanusGraph** (distributed scale via the Linux Foundation), with **Kuzu** and **FalkorDB** targeting embedded and GraphRAG use cases respectively.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[Neo4j Aura](https://neo4j.com/cloud/platform/aura-graph-database/)**  

  Fully managed graph database from the category leader. **AuraDB Free** tier available; **Professional** starts at $65/GB/month; Business Critical and Virtual Dedicated tiers for enterprise workloads . **September 2026 release** improved quantized vector search latency by ~5x and introduced native full-text search via the `SEARCH` clause . Neo4j holds the top spot in DB-Engines graph DBMS ranking with a score of 48.88, far ahead of competitors . Proprietary (Aura is managed; Community Edition is GPL v3).



- **[Amazon Neptune](https://aws.amazon.com/neptune/)**  

  AWS's fully managed graph database supporting Gremlin, SPARQL, and openCypher. Consumption-based pricing (instance-hours or serverless capacity units) . **Neptune Analytics** adds in-memory analytics and vector search for GraphRAG . Engine 1.4.8.0 deployed across regions in July 2026; dual-stack IPv6 support added June 2026 . Best for AWS-native architectures requiring managed graph without self-hosting.



- **[TigerGraph Cloud (Savanna)](https://www.tigergraph.com/)**  

  Distributed native graph database built for deep multi-hop traversal. **Important transition**: TigerGraph Cloud Classic (TG Cloud V3) reaches **end of life September 30, 2026**, with all customers migrated to **Savanna**, the next-generation cloud-native platform . Savanna managed pricing starts at **$45/GB/month**; self-managed Community is free up to 300GB single-server . Vendor-reported performance advantages are for specific 2-hop path queries and should be independently verified . GSQL is the primary query language (openCypher also supported).



- **[ArangoDB Oasis (now Arango Managed Platform / AMP)](https://arango.ai/)**  

  Multi-model database as a service, handling graphs, JSON documents, and key-values in a single engine. **Renamed from Oasis to AMP** . Runs on GCP or AWS with 24/7 monitoring, automatic updates, encryption, and audit logs . DB-Engines score of 3.29 (multi-model, rank 4) . Best for teams that need graph capabilities alongside document storage without managing infrastructure.



- **[Memgraph Cloud](https://memgraph.com/cloud)**  

  Fully managed in-memory graph database with a **14-day free trial**, hosted on AWS across 6 regions . Cypher-compatible and optimized for real-time streaming analytics. Best for prototyping and early-stage projects that may later self-host the open-source core.



- **[Azure Cosmos DB (Gremlin API)](https://azure.microsoft.com/en-us/services/cosmos-db/)**  

  Microsoft's globally distributed multi-model database with Gremlin API support for graph workloads. Consumption-based pricing with guaranteed low latency. DB-Engines score of 21.38 (multi-model, rank 2) . Best for Azure-native architectures requiring global distribution.



- **[Stardog](https://www.stardog.com/)**  

  Enterprise knowledge graph platform with SPARQL 1.1, federated virtual graphs, and reasoning. **Stardog Free** offers a renewable 1-year license for commercial use but **no HA, caching, backups, or LDAP**; Enterprise pricing is custom . Best for ontology-heavy, regulated environments requiring RDF/OWL reasoning.



- **[TerminusDB](https://terminusdb.com/)**  

  Open-source document-graph database with git-like versioning, branching, and collaboration features. Best for applications requiring full data lineage and time-travel queries.



## Open-Source GitHub Projects



- **[Neo4j Community Edition](https://github.com/neo4j/neo4j)**  

  The open-source core of the category leader. **Cypher** query language, ACID transactions, and the largest graph ecosystem (APOC, Graph Data Science library, Bloom visualization). **GPL v3 licensed**—note that Enterprise features (clustering, hot backups, RBAC) are commercial . DB-Engines score of 48.88 confirms its dominance . Best for teams that want the standard graph database with the deepest tooling and talent pool, accepting the GPL license and single-instance limitation.



- **[Memgraph](https://github.com/memgraph/memgraph)**  

  Ultra-fast, **in-memory** graph database built for real-time applications and streaming analytics. **Cypher-compatible** with the Neo4j ecosystem, reducing migration friction . Core engine is **Business Source License (BSL)**—free for development and standard production use, with commercial licensing for larger deployments . Best for real-time use cases (fraud detection, recommendation) where in-memory performance matters and Cypher familiarity is valued.



- **[Apache AGE](https://github.com/apache/age)**  

  PostgreSQL extension that adds **native graph database functionality** to PostgreSQL. Run openCypher graph queries **side-by-side with SQL** on the same data—no separate database to manage. **Apache 2.0** licensed . Best for teams already running PostgreSQL that want graph capabilities without introducing a new system, or applications where relational and graph queries need to coexist.



- **[JanusGraph](https://github.com/JanusGraph/janusgraph)**  

  Highly scalable distributed graph database optimized for **hundreds of billions of vertices and edges**. **Apache 2.0**, governed by the Linux Foundation . Supports multiple storage backends (Cassandra, HBase, BerkeleyDB) and indexing backends (Elasticsearch, Solr). **Trade-off**: operational complexity—you manage the storage and index layers separately. Best for massive-scale graphs where a single-server database cannot fit the data.



- **[Kuzu](https://github.com/kuzudb/kuzu)**  

  **Embedded** property graph database built for speed, with **vector search and full-text search built in**. Implements Cypher. Embedded architecture means no server to manage—the database runs inside your application process, similar to SQLite . Best for local analytics, GraphRAG pipelines, and applications where embedding the graph engine simplifies deployment.



- **[FalkorDB](https://github.com/FalkorDB/FalkorDB)**  

  Graph database using **GraphBLAS** under the hood for sparse adjacency matrix representation. Positioned explicitly as the best knowledge graph for **LLM and GraphRAG** use cases . Best for teams building retrieval-augmented generation systems that need graph traversal with vector search.



- **[NebulaGraph](https://github.com/vesoft-inc/nebula)**  

  Distributed, scalable native graph database designed for **super large-scale data** with millisecond latencies. **Apache 2.0** licensed . DB-Engines score of 1.68 (rank 13) . Best for enterprise network visualization and large-scale graph analytics where horizontal scalability is mandatory.



### Additional Strong Open-Source Options



- **Dgraph** — Native distributed graph database with GraphQL-native interface. Apache 2.0 for standalone version. Best for GraphQL-centric applications .

- **ArangoDB Community Edition** — The open-source core of ArangoDB's multi-model database. Free and open-source, handling graphs, documents, and key-values in one engine .

- **RedisGraph** — Graph database as a Redis module. **Note**: RedisGraph was discontinued; consider FalkorDB (built by the RedisGraph team) as the successor for Redis-based graph workloads.

- **Frameworks for building custom systems**: Use **Neo4j Community** for the deepest ecosystem and Cypher standard. Choose **Memgraph** when in-memory speed and Cypher compatibility are priorities. Use **Apache AGE** when you want graph queries inside existing PostgreSQL. Choose **Kuzu** or **FalkorDB** for embedded/GraphRAG workloads. Use **JanusGraph** or **NebulaGraph** when horizontal scale beyond a single server is required.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- **License matters**: Neo4j Community is GPL v3 (copyleft); Memgraph uses BSL (free for most production but with commercial restrictions); Apache AGE, JanusGraph, and NebulaGraph are Apache 2.0 . Verify license compatibility before deployment.

- **TigerGraph Cloud Classic is EOL September 30, 2026**—existing users are being migrated to Savanna with application changes required . Do not select Classic for new projects.

- Published benchmark comparisons often test specific query patterns; vendor-reported advantages (e.g., TigerGraph's multi-hop claims) should be validated against your actual schema and traversal depth before relying on them .



---



**Made for data engineers, knowledge graph architects, and developers building relationship-aware applications.**  

Let's make graph databases more open, accessible, and understandable.
