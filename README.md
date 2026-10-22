# Awesome Graph Database [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of leading **Graph Database** platforms, engines, and developer tools. Spanning cloud-native SaaS services, high-performance open-source graph engines, GraphRAG systems, RDF/SPARQL semantic stores, and distributed property graph databases.

---

## Sector Overview & Market Dynamics

The global graph database market is valued at approximately **$4.2B to $4.3B in 2026** (growing at a compound annual growth rate of 24–30% from ~$3.4B in 2025, and projected to exceed $18B by the early 2030s). The market is **moderately fragmented**: hyperscalers (AWS, Microsoft Azure) and category-defining pure-play leaders (Neo4j) anchor enterprise adoption, while specialized engines target high-growth niches like vector-graph hybrid retrieval (GraphRAG), real-time in-memory streaming, and embedded architectures.

---

## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS / Managed Cloud Platforms](#saas--managed-cloud-platforms)
- [Open-Source Graph Databases](#open-source-graph-databases)
- [Comparison & Architecture Selection](#comparison--architecture-selection)
- [How to Contribute](#how-to-contribute)
- [License & Disclaimer](#license--disclaimer)

---

## SaaS / Managed Cloud Platforms

Curated list of fully managed Graph Database-as-a-Service (DBaaS) offerings. Sorted by company scale (market cap / valuation / estimated revenue, descending).

| Product | Provider | Company Scale (Market Cap / Valuation / Est. ARR) | Starting Tier Pricing | Free Tier / Trial Limits | Primary Query Interface & Architecture |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **[Azure Cosmos DB (Gremlin API)](https://azure.microsoft.com/en-us/services/cosmos-db/)** | Microsoft | ~$3.1T Market Cap | **$0.008 per 100 RU/s / hour** (~$5.84 / 100 RU/s / month standard provisioned) | **Free forever**: First 1,000 RU/s throughput + 25 GB storage free every month per subscription | Gremlin (Apache TinkerPop), multi-model global distribution with multi-region replication |
| **[Amazon Neptune](https://aws.amazon.com/neptune/)** | Amazon Web Services (AWS) | ~$2.0T Market Cap | **$0.093 / hour** (`db.t4g.medium` instance) | **30-day free trial**: 750 hours of `db.t4g.medium` or `db.t3.medium`, 1 GB storage, 1 GB backup, 10M I/O requests | openCypher, Apache TinkerPop Gremlin, W3C SPARQL 1.1; Neptune Analytics for vector/GraphRAG |
| **[Neo4j Aura](https://neo4j.com/cloud/platform/aura-graph-database/)** | Neo4j, Inc. | ~$2.1B+ Valuation ($200M+ ARR) | **$0.09 / GB-RAM / hour** (~$65.70 / GB / month on AuraDB Professional) | **Free forever (AuraDB Free)**: 1 instance capped at 200,000 nodes & 400,000 relationships (auto-pauses after 3 days of write inactivity) | Cypher query language, native labeled property graph (LPG), integrated vector search index |
| **[TigerGraph Cloud (Savanna)](https://www.tigergraph.com/)** | TigerGraph | ~$476M Valuation (~$15M–$30M ARR) | **$45 / GB / month** (on next-gen Savanna platform) | **Free forever (Savanna Free Workspace)**: 1 R/W workspace + 2 read-only workspaces, capped at 32 vCPUs & 256 GB RAM, manual snapshots (auto-pause on inactivity) | GSQL, openCypher, ISO GQL support; deep multi-hop native graph compute engine |
| **[ArangoDB AMP](https://arango.ai/)** | ArangoDB (now Arango Managed Platform) | ~$60M Total Funding (~$15M–$21M ARR) | **$0.20 / hour** (small cluster baseline on AWS/GCP) | **14-day free trial**: 1 project with 1 small deployment (up to 4 GB RAM) and 1 data science notebook; self-hosted Community Edition is free up to 100 GB | AQL (ArangoDB Query Language), multi-model (graph, JSON document, key-value, search) |
| **[Stardog Cloud](https://www.stardog.com/)** | Stardog Union | ~$32.5M Total Funding (~$13M–$14M ARR) | **$5.553 / hour** (pay-as-you-go software rate via AWS Marketplace + EC2 compute) | **Free forever (Stardog Cloud Free)**: Up to 1,000,000 stored edges/triples and up to 3 databases with community support | SPARQL 1.1, RDF/OWL ontology reasoning, virtual graph data virtualization layer |
| **[Memgraph Cloud](https://memgraph.com/cloud)** | Memgraph Ltd. | ~$14M Total Funding (~$4.7M ARR) | **$16 / month** (starter tier with 1 GB RAM, ~$0.022 / hour) | **14-day free trial**: 1 active project capped at 2 GB RAM with full Cypher streaming capabilities | openCypher, C++ in-memory real-time graph engine, Kafka/Pulsar streaming integrations |
| **[TerminusDB Cloud](https://terminusdb.com/)** | TerminusDB | ~$5.7M Total Funding (<$1M ARR) | **$0.00 / month** (Free developer tier; custom enterprise quotes for private cloud SLAs) | **Free forever (Developer Tier)**: Full schema & collaboration features on open-source core; self-hosted Docker has no software limits | WOQL (Web Object Query Language), GraphQL, git-style versioning and branch-merge primitives |

---

## Open-Source Graph Databases

Curated self-hosted and open-source graph engines. Sorted by GitHub stars (descending). Each repository includes an official social star badge directly linking to its stargazers list.

### 1. [SurrealDB](https://github.com/surrealdb/surrealdb) [![GitHub stars](https://img.shields.io/github/stars/surrealdb/surrealdb?style=social&color=white)](https://github.com/surrealdb/surrealdb/stargazers)
* **License**: Business Source License (BSL 1.1) / Apache 2.0 (client libraries)
* **Architecture**: Multi-model database (document, graph, relational, time-series, vector) written in Rust. Treats record pointers as bidirectional edges for direct pointer traversals without JOIN operations.
* **Best for**: End-to-end fullstack development, serverless apps, and modern multi-model backends requiring realtime live queries.

### 2. [Dgraph](https://github.com/dgraph-io/dgraph) [![GitHub stars](https://img.shields.io/github/stars/dgraph-io/dgraph?style=social&color=white)](https://github.com/dgraph-io/dgraph/stargazers)
* **License**: Apache 2.0
* **Architecture**: Native distributed transactional graph database written in Go. Executes queries natively in GraphQL and DQL (GraphQL+-). Scales horizontally across clusters with Raft consensus.
* **Best for**: GraphQL-native microservice architectures, deeply nested social networks, and horizontally sharded applications.

### 3. [Neo4j Community Edition](https://github.com/neo4j/neo4j) [![GitHub stars](https://img.shields.io/github/stars/neo4j/neo4j?style=social&color=white)](https://github.com/neo4j/neo4j/stargazers)
* **License**: GPL v3 (Enterprise features are closed-source/commercial)
* **Architecture**: Native property graph engine with index-free adjacency. Standard-bearer for the Cypher query language with the largest ecosystem of tools (APOC library, Neo4j Browser, Bloom visualization).
* **Best for**: General-purpose graph analytics, enterprise knowledge graphs, and teams wanting the standard graph developer talent pool.

### 4. [Cayley](https://github.com/CayleyGraph/cayley) [![GitHub stars](https://img.shields.io/github/stars/CayleyGraph/cayley?style=social&color=white)](https://github.com/CayleyGraph/cayley/stargazers)
* **License**: Apache 2.0
* **Architecture**: Open-source graph database written in Go inspired by Freebase and Google Knowledge Graph. Pluggable backend storage (LevelDB, BoltDB, PostgreSQL, MongoDB).
* **Best for**: Fast Linked Data / RDF graph applications and lightweight semantic web services.

### 5. [ArangoDB Community Edition](https://github.com/arangodb/arangodb) [![GitHub stars](https://img.shields.io/github/stars/arangodb/arangodb?style=social&color=white)](https://github.com/arangodb/arangodb/stargazers)
* **License**: ArangoDB Community License (Source Available / Free up to 100 GB)
* **Architecture**: Native multi-model database unifying graphs, JSON documents, full-text search, and key-values under the declarative AQL language.
* **Best for**: Applications requiring complex joins and document stores with graph traversal across unified collections.

### 6. [NebulaGraph](https://github.com/vesoft-inc/nebula) [![GitHub stars](https://img.shields.io/github/stars/vesoft-inc/nebula?style=social&color=white)](https://github.com/vesoft-inc/nebula/stargazers)
* **License**: Apache 2.0
* **Architecture**: Distributed, shared-nothing native graph engine in C++ with separate compute and storage layers. Designed to handle tens of billions of vertices and trillions of edges with millisecond response times.
* **Best for**: Super large-scale enterprise graph analytics, financial fraud detection networks, and high-concurrency traversals.

### 7. [FalkorDB](https://github.com/FalkorDB/FalkorDB) [![GitHub stars](https://img.shields.io/github/stars/FalkorDB/FalkorDB?style=social&color=white)](https://github.com/FalkorDB/FalkorDB/stargazers)
* **License**: Server Side Public License (SSPL)
* **Architecture**: Ultra-low-latency graph database powered by GraphBLAS sparse matrix linear algebra and vector indexing. Built by the former RedisGraph team to deliver sub-millisecond multi-hop graph queries.
* **Best for**: GraphRAG (Retrieval-Augmented Generation) for LLMs, real-time agent memory, and vector-graph hybrid queries.

### 8. [JanusGraph](https://github.com/JanusGraph/janusgraph) [![GitHub stars](https://img.shields.io/github/stars/JanusGraph/janusgraph?style=social&color=white)](https://github.com/JanusGraph/janusgraph/stargazers)
* **License**: Apache 2.0 (Linux Foundation Project)
* **Architecture**: Distributed property graph database leveraging pluggable storage (Apache Cassandra, Apache HBase, ScyllaDB) and pluggable search indexing (Elasticsearch, OpenSearch, Apache Solr). Supports Apache TinkerPop Gremlin.
* **Best for**: Big Data pipelines and massively distributed graphs spanning hundreds of billions of nodes.

### 9. [Apache AGE](https://github.com/apache/age) [![GitHub stars](https://img.shields.io/github/stars/apache/age?style=social&color=white)](https://github.com/apache/age/stargazers)
* **License**: Apache 2.0
* **Architecture**: Native PostgreSQL extension implementing the openCypher graph query specification. Queries graph topologies side-by-side with relational SQL data inside existing PostgreSQL tables.
* **Best for**: Teams with existing PostgreSQL infrastructure who want native graph queries without deploying a separate database.

### 10. [Memgraph](https://github.com/memgraph/memgraph) [![GitHub stars](https://img.shields.io/github/stars/memgraph/memgraph?style=social&color=white)](https://github.com/memgraph/memgraph/stargazers)
* **License**: Business Source License (BSL 1.1)
* **Architecture**: High-performance in-memory property graph engine written in C++. Fully Cypher-compatible and ACID compliant with native streaming connectors (Kafka, Redpanda, Apache Pulsar).
* **Best for**: Real-time fraud detection, live cybersecurity telemetry, streaming recommendation engines, and Cypher migrations.

### 11. [TypeDB](https://github.com/typedb/typedb) [![GitHub stars](https://img.shields.io/github/stars/typedb/typedb?style=social&color=white)](https://github.com/typedb/typedb/stargazers)
* **License**: Apache 2.0
* **Architecture**: Strongly-typed database with an expressive polymorphic type system (Entity-Relation-Attribute model) and TypeQL query language. Features automatic deductive reasoning and inference.
* **Best for**: Complex domains, semantic knowledge bases, drug discovery, and ontology-driven data modeling.

### 12. [CozoDB](https://github.com/cozodb/cozo) [![GitHub stars](https://img.shields.io/github/stars/cozodb/cozo?style=social&color=white)](https://github.com/cozodb/cozo/stargazers)
* **License**: MPL 2.0
* **Architecture**: General-purpose transactional graph database using Datalog for queries. Runs in embedded mode (via Rust, Python, NodeJS, Wasm) or standalone with RocksDB, SQLite, or S3 backends. Supports vector search and time-travel.
* **Best for**: Embedded applications, algorithmic graph computations, and hybrid relational-graph-vector pipelines.

### 13. [Kùzu](https://github.com/kuzudb/kuzu) [![GitHub stars](https://img.shields.io/github/stars/kuzudb/kuzu)?style=social&color=white](https://github.com/kuzudb/kuzu/stargazers)
* **License**: MIT
* **Architecture**: Embedded property graph database optimized for analytical workloads (OLAP) and GraphRAG. In-process execution (like DuckDB/SQLite), openCypher query interface, columnar storage, vectorized query execution, and built-in vector search.
* **Best for**: Local data science pipelines, in-memory LLM GraphRAG workflows, and zero-management embedded graph storage.

### 14. [TerminusDB](https://github.com/terminusdb/terminusdb) [![GitHub stars](https://img.shields.io/github/stars/terminusdb/terminusdb?style=social&color=white)](https://github.com/terminusdb/terminusdb/stargazers)
* **License**: Apache 2.0
* **Architecture**: Document-graph database featuring succinct data structures and git-like revision control (branch, merge, rebase, diff, and time-travel querying).
* **Best for**: Collaborative data mesh, data versioning, compliance audits, and regulatory data lineage tracking.

### 15. [Apache HugeGraph](https://github.com/apache/incubator-hugegraph) [![GitHub stars](https://img.shields.io/github/stars/apache/incubator-hugegraph?style=social&color=white)](https://github.com/apache/incubator-hugegraph/stargazers)
* **License**: Apache 2.0 (Apache Incubator)
* **Architecture**: Highly scalable distributed graph database compliant with Apache TinkerPop Gremlin. Backed by RocksDB, Cassandra, or HBase with multi-level caching.
* **Best for**: Billion-to-trillion edge enterprise graphs requiring integration with the Apache TinkerPop stack.

### 16. [TuGraph-DB](https://github.com/TuGraph-family/tugraph-db) [![GitHub stars](https://img.shields.io/github/stars/TuGraph-family/tugraph-db?style=social&color=white)](https://github.com/TuGraph-family/tugraph-db/stargazers)
* **License**: Apache 2.0 (Co-developed by Ant Group & Tsinghua University)
* **Architecture**: High-throughput distributed graph database engine supporting terabyte-scale data with Cypher and Gremlin querying, built-in graph analytics algorithms, and stored procedures.
* **Best for**: Financial risk control, transaction graph mining, and high-throughput enterprise OLTP graph systems.

### 17. [Apache Jena](https://github.com/apache/jena) [![GitHub stars](https://img.shields.io/github/stars/apache/jena?style=social&color=white)](https://github.com/apache/jena/stargazers)
* **License**: Apache 2.0
* **Architecture**: Established open-source Java framework and triple store (TDB2 / Fuseki) for building Semantic Web and Linked Data applications. Complete SPARQL 1.1 query engine and rule-based inference.
* **Best for**: Academic knowledge graphs, government ontology publishing, and W3C semantic web standards.

### 18. [ArcadeDB](https://github.com/ArcadeData/arcadedb) [![GitHub stars](https://img.shields.io/github/stars/ArcadeData/arcadedb?style=social&color=white)](https://github.com/ArcadeData/arcadedb/stargazers)
* **License**: Apache 2.0
* **Architecture**: Next-generation multi-model database engine created by the original author of OrientDB. Natively supports Cypher, Gremlin, SQL, GraphQL, and full-text search.
* **Best for**: High-density multi-model graph and document workloads with low memory footprint.

---

## Comparison & Architecture Selection

| Use Case / Scenario | Recommended Solution | Query Interface | Key Trade-off / Consideration |
| :--- | :--- | :--- | :--- |
| **Enterprise Standard & Skill Availability** | **Neo4j** | Cypher | Mature ecosystem; clustering & enterprise HA requires commercial license. |
| **Real-time Streaming & Sub-millisecond Fraud Detection** | **Memgraph** | Cypher | In-memory RAM requirements; BSL source-available license. |
| **Existing PostgreSQL Stack** | **Apache AGE** | openCypher + SQL | Zero new database infrastructure; limited to single-node PostgreSQL scale limits. |
| **Embedded Graph Analytics & LLM GraphRAG** | **Kùzu** / **FalkorDB** | Cypher | In-process or Redis-backed simplicity; not meant for massive distributed sharding. |
| **Massive Horizontal Scale (>100B Vertices)** | **NebulaGraph** / **JanusGraph** | nGQL / Gremlin | Operational overhead of distributed cluster storage and index coordination. |
| **Git-style Data Lineage & Branching** | **TerminusDB** | WOQL / GraphQL | Unique data modeling paradigm requiring architectural adjustments. |
| **Enterprise Multi-Cloud Managed Infrastructure** | **Azure Cosmos DB** / **AWS Neptune** | Gremlin / openCypher | Managed hyperscaler SLAs; consumption costs scale with high IOPS/throughput. |

---

## How to Contribute

Contributions are welcome! Please follow these steps to add or update an entry:

1. **Fork** this repository.
2. Edit `README.md` following the established table or list formatting.
3. Ensure every SaaS product includes specific starting prices, exact free tier limits, and company scale metrics.
4. Ensure open-source projects include official star badges linking directly to their `/stargazers` URL and are sorted by star count.
5. Submit a **Pull Request** with a descriptive summary of changes.

---

## License & Disclaimer

* **Community Curated**: This list is curated for technical comparison and educational reference.
* **License Verification**: Always check individual project repository licenses (e.g., Apache 2.0, MIT, BSL 1.1, SSPL, GPL v3) before deploying into proprietary or enterprise production environments.
* **Pricing & Cloud Quotas**: SaaS pricing and free tier quotas are subject to vendor updates. Figures cited reflect verified October 2026 platform specifications.
