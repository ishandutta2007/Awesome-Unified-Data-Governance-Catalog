# Awesome-Unified-Data-Governance-Catalog

## Top Unified Data & Governance Catalog Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Metadata Management, Data Lineage & Self-Hosted Governance Platforms*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Unified Data & Governance Catalogs**. These tools enable organizations to discover, understand, and govern data assets across the enterprise—providing a central metadata repository, column-level lineage, business glossaries, and access policies that make data trustworthy and AI-ready.



**Examples** include Snowflake Horizon Catalog, Collibra Data Intelligence Platform, Alation Data Catalog, Atlan Data Governance, Microsoft Purview Catalog, Informatica CDGC, Databricks Unity Catalog, Quest erwin Data Catalog, IBM Watson Knowledge Catalog, and data.world (the category leaders).



**Open-source emphasis**: Unified Data & Governance Catalogs is a domain where open-source tooling is **mature and production-proven for core catalog capabilities**, though self-hosting carries a hidden operational cost. **DataHub** and **OpenMetadata** are the two leading open-source catalogs—both provide column-level lineage parsed from query logs, connector ecosystems, and governance features, and a 2026 comparative study notes they are "genuinely capable software and the right choice in several scenarios" . **Apache Atlas** provides Hadoop-ecosystem-focused metadata management with tag-based access control via Ranger . **Amundsen** (Lyft) offers search-first data discovery but lacks column-level lineage . The critical caveat: **self-hosting costs roughly a quarter to a full platform engineer** in ongoing time for upgrades, connector repair, and identity configuration—the license is free, but that engineer fraction decides most business cases . A compliance obligation from an external party (auditor, regulator) is the usual trigger for migrating to commercial platforms, not missing features .



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-products)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[Snowflake Horizon Catalog](https://www.snowflake.com/)**  

  Unified governance layer within Snowflake for discovering, governing, and securing data and AI assets; provides lineage, classification, access policies, and cross-account sharing.



- **[Collibra Data Intelligence Platform](https://www.collibra.com/)**  

  Enterprise data governance and catalog platform with business glossary, data lineage, policy management, and stewardship workflows; positioned for large regulated organizations.



- **[Alation Data Catalog](https://www.alation.com/)**  

  Data catalog with collaborative curation, active data governance, and behavioral analytics (query log analysis to surface popular datasets); known for strong user adoption and search experience.



- **[Atlan Data Governance](https://atlan.com/)**  

  Modern data catalog and governance platform with a marketplace-style interface, lineage, and collaboration features; popular with data-mature startups and mid-market teams.



- **[Microsoft Purview Catalog](https://www.microsoft.com/en-us/security/business/microsoft-purview)**  

  Unified data governance service within Microsoft Purview; provides automated data discovery, sensitivity labeling, lineage, and access management across Microsoft and third-party sources.



- **[Informatica CDGC](https://www.informatica.com/)**  

  Cloud Data Governance and Catalog within Informatica's Intelligent Data Management Cloud; provides metadata management, lineage, glossary, and governance workflows with AI-powered recommendations.



- **[Databricks Unity Catalog](https://www.databricks.com/)**  

  Unified catalog for data and AI assets within Databricks; manages tables, volumes (unstructured data), and AI models/functions together, with support for Delta Lake, Iceberg via UniForm, Parquet, CSV, and JSON . Implements the Iceberg REST Catalog API and supports credential vending for centralized governance . **Open-sourced in June 2024** and donated to LF AI & Data as a sandbox project .



- **[Quest erwin Data Catalog](https://www.quest.com/)**  

  Data catalog and governance platform with metadata management, lineage, and data quality integration; part of the erwin by Quest suite.



- **[IBM Watson Knowledge Catalog](https://www.ibm.com/products/watson-knowledge-catalog)**  

  Enterprise catalog and governance platform within IBM Cloud Pak for Data; provides discovery, classification, policy enforcement, and collaboration.



- **[data.world](https://data.world/)**  

  Cloud-native data catalog with a collaborative, social-style interface; strong for data discovery and team collaboration, with governance features layered on.



## Open-Source GitHub Projects



### Unified Metadata Platforms (DataHub / OpenMetadata)



- **[DataHub](https://github.com/datahub-project/datahub)**  

  The leading open-source **metadata platform** (Apache 2.0) with **event-driven microservices architecture** (Kafka, Elasticsearch, MySQL) . Features: real-time metadata updates (proven to 10M+ assets and O(1B) relationships at LinkedIn) , column-level lineage parsed from query logs, GraphQL/REST/Thrift APIs, and an **Aspect model** that allows custom metadata fields—including embedding vectors for semantic search . **The strongest choice for high-frequency change environments** where upstream schema changes need sub-minute indexing; also the furthest ahead on AI/vector metadata support . Docker and Kubernetes deployment.



- **[OpenMetadata](https://github.com/open-metadata/OpenMetadata)**  

  Open-source **unified metadata platform** (Apache 2.0) with a **monolithic Java service + Elasticsearch** architecture designed as an "all-in-one" platform . Features: **column-level lineage**, data quality, governance, glossary with typed relations (relatedTo, synonym, broader/narrower, calculatedFrom), data contracts, and a **Data Marketplace** with customizable landing pages . v1.13.0 adds **Google Gemini embedding provider**, hybrid search tuning (keyword/semantic weights, RRF), and **MCP Server** for AI agent access to the metadata graph . **Best for teams wanting data quality and governance in one platform** with lower operational complexity than DataHub's microservices, though coupling means module upgrades can affect overall stability .



### Hadoop-Ecosystem Catalog



- **[Apache Atlas](https://github.com/apache/atlas)**  

  Open-source **metadata management and governance** platform (Apache 2.0, ~2,000 GitHub stars, 215 contributors) incubated by Hortonworks with Aetna, JPMorgan Chase, Merck, SAS, and Target . Provides: data classification, centralized auditing, search and lineage, and a **security/policy engine** integrated with Apache Ranger for tag-based access control . **Focused on the Apache Hadoop platform** but designed to exchange metadata with other tools; best for organizations already standardized on Hadoop/Hive.



### Search-First Discovery



- **[Amundsen](https://github.com/amundsen-io/amundsen)**  

  Open-source data discovery platform (Apache 2.0) originally developed by Lyft; **search-engine-first architecture** (all queries go through Elasticsearch) for fast table search at scale . **Critical limitation**: default ingestion is **table-level metadata only**—column-level lineage and column-level statistics require custom ingestion plugins . Metadata model is relatively fixed, limiting custom extensions without code changes . Best for large-scale table search where column-level depth is not required.



### Additional Strong Open-Source Options



- **Apache Gravitino** — Open-source metadata lakehouse catalog with **federation** capabilities (can sit in front of existing Hive Metastore, Polaris, etc.) and broad metadata scope across systems . **Best for organizations needing to front existing catalogs** rather than replace them wholesale.

- **Lakekeeper** — Open-source Iceberg REST catalog (Apache 2.0) with a focus on operational simplicity; **credible and actively built** for Iceberg-native deployments . **Catalog-focused**—not a full governance platform with glossary and stewardship.

- **Unity Catalog OSS** — The open-source version of Databricks' Unity Catalog (donated to LF AI & Data) . Provides universal catalog for tables, volumes, and AI assets with Iceberg REST API and credential vending . **Best for teams in the Databricks/Lakehouse ecosystem** or wanting a vendor-neutral catalog standard.



**Frameworks for building custom systems**: The choice hinges on architecture and AI-readiness. For **high-frequency change environments and vector metadata support**, DataHub . For **all-in-one governance with data quality and MCP access**, OpenMetadata . For **Hadoop-centric environments with Ranger integration**, Apache Atlas . For **large-scale table search without column depth**, Amundsen . For **federating existing catalogs**, Apache Gravitino . No open-source catalog matches the **managed compliance evidence and auditor workflows** of Collibra or Alation—those become relevant when external parties require retained approval history and immutable access records .



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Data governance catalogs handling metadata and access policies must comply with applicable privacy regulations (GDPR, CCPA) and industry compliance requirements; **permission models do not migrate cleanly between catalogs**—switching requires rebuilding the permission graph by hand, and a period where two systems both think they are authoritative is where incidents happen .

- **Open-source data catalogs are capable software with a hidden operational cost**—self-hosting costs roughly 0.25–1.0 FTE platform engineer in ongoing time . The license is free, but that engineer fraction is the cost that decides most business cases. **A compliance obligation from an external party** (auditor, regulator requiring retained approval history and immutable access records) is the usual trigger for migrating to commercial platforms, not missing features .

- Verify license terms for commercial use; DataHub, OpenMetadata, Apache Atlas, Amundsen, and Apache Gravitino use Apache 2.0; Unity Catalog OSS is open-source under the LF AI & Data foundation .



---



**Made for data governance leads, metadata architects, and organizations building trustworthy data foundations for AI.**  

Let's make data governance more open, but with clear eyes about the engineer time and compliance triggers that define the real cost.
