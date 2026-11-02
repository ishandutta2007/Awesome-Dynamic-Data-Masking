# 🛡️ Awesome Dynamic Data Masking

<p align="center">
  <a href="https://github.com/ishandutta2007/Awesome-Awesome-Awesome"><img src="https://img.shields.io/badge/Awesome-%E2%9C%94-blueviolet?style=flat-square&logo=github" alt="Awesome"/></a><a href="https://discord.gg/jc4xtF58Ve"><img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord" /></a>
  <a href="https://github.com/ishandutta2007/Awesome-Dynamic-Data-Masking/stargazers"><img src="https://img.shields.io/github/stars/ishandutta2007/Awesome-Dynamic-Data-Masking?style=social" alt="GitHub Stars" /></a>
  <a href="https://github.com/ishandutta2007/Awesome-Dynamic-Data-Masking/network/members"><img src="https://img.shields.io/github/forks/ishandutta2007/Awesome-Dynamic-Data-Masking?style=social" alt="GitHub Forks" /></a>
  <a href="https://github.com/ishandutta2007/Awesome-Dynamic-Data-Masking/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square" alt="License" /></a>
  <a href="https://github.com/ishandutta2007"><img alt="GitHub followers" src="https://img.shields.io/github/followers/ishandutta2007?label=Follow" /></a>
</p>

<p align="center">
  <img src="assets/banner.svg" alt="Awesome Dynamic Data Masking Banner" width="100%" />
</p>

<h3 align="center">
  🚀 Curated Guide to Dynamic Data Masking (DDM), Query-Time Redaction, Zero-Trust Data Governance &amp; PII Anonymization
</h3>

<p align="center">
  <strong>Enterprise SaaS Pricing &amp; Market Share &bull; Production Open-Source Engines &bull; SQL Proxies &bull; Policy-as-Code</strong>
</p>

---

## 📌 Introduction &amp; Core Concepts

**Dynamic Data Masking (DDM)** enables organizations to protect sensitive data (PII, PHI, financial records) in real time—at query runtime—without copying or modifying the underlying database tables. Based on user roles, granular attributes (ABAC), or connection contexts, unauthorized users see redacted, anonymized, tokenized, or pseudonymized values while authorized systems receive original records.

Whether you are designing zero-trust compliance for **GDPR, HIPAA, PCI-DSS, or DPDP**, this repository provides a definitive, battle-tested breakdown of commercial SaaS leaders and active open-source solutions.

---

## 📑 Table of Contents

- [📊 Sector Overview &amp; Market Dynamics](#-sector-overview--market-dynamics)
- [🏢 SaaS &amp; Commercial Hosted Platforms](#-saas--commercial-hosted-platforms)
- [🔓 Open-Source GitHub Projects (Ranked by Stars)](#-open-source-github-projects-ranked-by-stars)
- [📈 Star History](#-star-history)
- [💖 Support &amp; Community](#-support--community)
- [🤝 How to Contribute](#-how-to-contribute)
- [⚖️ Architecture Insights &amp; Disclaimer](#️-architecture-insights--disclaimer)

---

## 📊 Sector Overview &amp; Market Dynamics

The global data masking market (spanning dynamic data masking, static test data masking, and format-preserving tokenization) is currently valued between **$1.1B and $1.3B**, with research projecting it to exceed **$2.5B to $4.5B** by the mid-2030s at a **13%–15% CAGR**. 

Market concentration is **moderately concentrated**:
- **Dominant Tier:** Major cloud data warehouses (Snowflake, Databricks, BigQuery) and legacy infrastructure leaders handle native single-platform masking.
- **Cross-Cloud &amp; Proxy Tier:** Fast-growing independent policy-as-code and inline proxy vendors (Immuta, Privacera, Satori, ALTR, Protegrity) dominate complex multi-cloud enterprise deployments where unified governance is demanded.

---

## 🏢 SaaS &amp; Commercial Hosted Platforms

*Sorted in descending order by company scale (market capitalization / enterprise valuation).*

| Platform | 🏢 Company Scale / Valuation | 💰 Specific Starting Tier Pricing | 🎁 Free Tier / Trial Limit | 🛠️ Architecture &amp; Key Masking Capabilities |
| :--- | :--- | :--- | :--- | :--- |
| **Snowflake Dynamic Data Masking** | **~$110B–$120B Market Cap** (~$4.7B+ ARR; NYSE: SNOW) | **Enterprise Edition tier required**: Standard compute starts at $2.00/credit; Enterprise starts at **$3.00/credit** (+50% compute surcharge across all workloads) | **30-day free trial** with **$400 in free compute credits** | ⚡ Native database column-level masking policies; zero copy, applied dynamically per query via SQL/Snowsight |
| **Immuta** | **$1.0B Valuation** (Unicorn; Series E) | Custom contract; G-Cloud public procurement lists base user tiers starting from **~£1,000–£1,600/user/year** (typically **$100,000/yr** platform minimum) | **No public free tier**; 14-to-30 day guided Proof-of-Concept (PoC) evaluation upon sales approval | 🌐 Centralized cross-cloud policy-as-code layer across Snowflake, Databricks, BigQuery, and Amazon Redshift |
| **Protegrity** | **~$400M+ Implied Valuation** (~$50M–$100M ARR) | Enterprise unit-based licensing; AWS Marketplace Private Offer contracts typically starting from **~$50,000–$100,000+/year** | **No self-service free tier**; 30-day enterprise evaluation / PoC available via private offer | 🔐 Ultra-high-throughput field-level dynamic tokenization, format-preserving encryption (FPE), and in-stream masking |
| **Privacera** | **~$250M–$500M Est. Valuation** (~$10M–$50M ARR; Series B) | Enterprise sales-led; AWS Marketplace custom contracts typically starting from **~$30,000–$50,000/year** | **30-day free trial** for PrivaceraCloud on AWS Marketplace | 🛡️ Built by the creators of Apache Ranger; multi-cloud unified data access governance, column masking, and tagging |
| **Delphix** (Perforce) | **Acquired** (~$375M debt financing backing deal; ~$100M+ ARR) | BYOL capacity license based on managed source storage, starting at **~$1,500–$2,000/TB/year** + cloud infra costs | **No self-service free tier**; 30-day guided enterprise evaluation license on request | 📦 Continuous Compliance &amp; Hyperscale masking (specialized in high-volume static data masking and database virtualization) |
| **Satori** (Commvault) | **Acquired** (Raised $25.25M prior to acquisition; ~$10M ARR) | Annual subscription based on protected locations; entry contracts typically start at **~$35,000–$45,000/year** (avg ~$95,000/yr) | **No public free tier**; 14-day guided sandbox PoC evaluation on request | 🔀 Transparent inline database proxy (<5ms latency overhead); universal agentless masking without altering schemas |
| **ALTR** | **~$100M–$250M Est. Valuation** (~$8.6M ARR; Series C) | Published self-serve tier starting at **$10 per user/month** | **Free Forever tier**: permanently free for up to **3 connected databases** with core masking &amp; classification | ❄️ Cloud-native Snowflake data access governance, automated sensitive data discovery, and dynamic column masking |
| **Cyral** (Varonis) | **Acquired** (Raised $41M–$46M prior to acquisition; ~$5M ARR) | Identity &amp; repository-based tiers; custom entry contracts typically start from **~$25,000–$35,000/year** | **No public free tier**; 30-day sandbox trial via AWS Marketplace / sales engagement | 🚦 Stateless interception proxy providing real-time attribute-based dynamic masking and database activity monitoring |
| **Baffle** | **~$50M–$100M Est. Valuation** (~$36.5M raised; ~$3M–$4M ARR) | Usage/metered data protection tiers via AWS Marketplace; starting contracts from **~$15,000–$20,000/year** | **30-day free trial** available via AWS Marketplace (Baffle Trial for Amazon RDS &amp; S3) | 🧩 No-code dynamic data masking and privacy-preserving field encryption at the application and lakehouse layer |
| **Mentis** (iMask) | **Privately Held / Bootstrapped-Growth** (~$5M–$15M ARR) | Published cloud tiers starting from **$50/month** (Individual, 1 user) up to **$3,000/month** (100 users) | **No public free tier or free trial**; evaluation PoC arranged via enterprise sales | ⚙️ In-database dynamic masking (iMask) with embedded hooks, ABAC/RBAC rules, and <5% operational overhead |

---

## 🔓 Open-Source GitHub Projects (Ranked by Stars)

*Top open-source projects for dynamic column masking, real-time AI guardrails, PII detection, and database anonymization. Sorted in descending order by GitHub stargazers count.*

### 1. [Bytebase](https://github.com/bytebase/bytebase) [![GitHub stars](https://img.shields.io/github/stars/bytebase/bytebase?style=social&color=white)](https://github.com/bytebase/bytebase/stargazers)
- **Primary Focus**: 🛡️ Database DevSecOps &amp; Dynamic Data Masking
- **Tech Stack**: Go, TypeScript, Vue
- **License**: Apache-2.0
- **Summary**: Bytebase provides unified database governance, schema migrations, and query access management. It features enterprise-grade **dynamic data masking** across 20+ database engines (PostgreSQL, MySQL, ClickHouse, Snowflake, BigQuery, etc.), redacting sensitive columns at query runtime based on user roles and project environments.

### 2. [Microsoft Presidio](https://github.com/data-privacy-stack/presidio) [![GitHub stars](https://img.shields.io/github/stars/data-privacy-stack/presidio?style=social&color=white)](https://github.com/data-privacy-stack/presidio/stargazers)
- **Primary Focus**: 🔍 PII Detection, Anonymization &amp; Redaction SDK
- **Tech Stack**: Python, spaCy, Transformers
- **License**: MIT
- **Summary**: The industry-standard library for detecting and anonymizing Personally Identifiable Information (PII) in unstructured text, images, and tabular columns. Offers customizable recognizers (NLP + regex pattern matching) and anonymization operators (redact, hash, mask, encrypt, replace).

### 3. [Neosync](https://github.com/nucleuscloud/neosync) [![GitHub stars](https://img.shields.io/github/stars/nucleuscloud/neosync?style=social&color=white)](https://github.com/nucleuscloud/neosync/stargazers)
- **Primary Focus**: 🔄 Open-Source Developer Data Anonymization &amp; Synthetic Data Platform
- **Tech Stack**: Go, Next.js, React
- **License**: MIT
- **Summary**: Modern developer platform to monitor, detect PII, and anonymize production database data across environments. Allows engineers to build data masking pipelines, generate relational synthetic test data, and safely replicate masked subsets into staging/QA.

### 4. [Greenmask](https://github.com/GreenmaskIO/greenmask) [![GitHub stars](https://img.shields.io/github/stars/GreenmaskIO/greenmask?style=social&color=white)](https://github.com/GreenmaskIO/greenmask/stargazers)
- **Primary Focus**: 🐘 PostgreSQL Database Anonymization &amp; Masking Utility
- **Tech Stack**: Go
- **License**: Apache-2.0
- **Summary**: A stateless logical database backup and anonymization utility designed natively for PostgreSQL. Supports deterministic obfuscation, synthetic generation, and database subsetting without copying raw production PII to developer machines.

### 5. [Apache Ranger](https://github.com/apache/ranger) [![GitHub stars](https://img.shields.io/github/stars/apache/ranger?style=social&color=white)](https://github.com/apache/ranger/stargazers)
- **Primary Focus**: 🏛️ Enterprise Centralized Data Access &amp; Dynamic Column Masking Engine
- **Tech Stack**: Java
- **License**: Apache-2.0
- **Summary**: The bedrock dynamic masking and governance engine for big data and Hadoop architectures. Provides native query-time column masking for Apache Hive and Spark (redact, partial mask, hash, custom UDFs) backed by centralized RBAC/ABAC policies and complete audit trails.

### 6. [Hoop.dev](https://github.com/hoophq/hoop) [![GitHub stars](https://img.shields.io/github/stars/hoophq/hoop?style=social&color=white)](https://github.com/hoophq/hoop/stargazers)
- **Primary Focus**: 🤖 Runtime AI Guardrail &amp; Database Dynamic Masking Proxy
- **Tech Stack**: Go, TypeScript
- **License**: AGPL-3.0
- **Summary**: An AI and human access gateway that sits in front of production databases and LLM agents. Dynamically intercepts database queries and terminal sessions to mask PII/sensitive data on-the-fly and block destructive commands in real time.

### 7. [Datanymizer](https://github.com/datanymizer/datanymizer) [![GitHub stars](https://img.shields.io/github/stars/datanymizer/datanymizer?style=social&color=white)](https://github.com/datanymizer/datanymizer/stargazers)
- **Primary Focus**: 🦀 High-Performance Database Dumper with Anonymization
- **Tech Stack**: Rust
- **License**: Apache-2.0
- **Summary**: Fast and flexible database anonymizer written in Rust. Replaces production database tables with realistic fake data using templates and regex rules during dump creation, ensuring compliance before data leaves production boundaries.

### 8. [Visulima Redact](https://github.com/visulima/visulima) [![GitHub stars](https://img.shields.io/github/stars/visulima/visulima?style=social&color=white)](https://github.com/visulima/visulima/stargazers)
- **Primary Focus**: 📜 High-Speed TypeScript &amp; JavaScript Redaction Library
- **Tech Stack**: TypeScript
- **License**: MIT
- **Summary**: Modular library for deep-object redaction, handling circular references, regex rules, and customizable PII masking across JSON objects, application logs, and API payload layers.

### 9. [PostgreSQL Anonymizer](https://github.com/neondatabase/postgresql_anonymizer) [![GitHub stars](https://img.shields.io/github/stars/neondatabase/postgresql_anonymizer?style=social&color=white)](https://github.com/neondatabase/postgresql_anonymizer/stargazers)
- **Primary Focus**: 🧩 In-Database Dynamic Masking Extension for PostgreSQL
- **Tech Stack**: C, PL/pgSQL
- **License**: PostgreSQL License
- **Summary**: A declarative PostgreSQL extension implementing in-engine **Dynamic Masking**. Roles marked as masked automatically receive obfuscated data for specified columns at query execution time via standard SQL security labels (`SECURITY LABEL`).

### 10. [VeilDB](https://github.com/veildb/veildb) [![GitHub stars](https://img.shields.io/github/stars/veildb/veildb?style=social&color=white)](https://github.com/veildb/veildb/stargazers)
- **Primary Focus**: 🐳 Self-Hosted Client-Agent Masked Database Dumps
- **Tech Stack**: PHP, Symfony, Docker
- **License**: MIT
- **Summary**: Self-hosted anonymization suite featuring an agent-based architecture where raw database dumps are processed entirely within your private network before sanitized dumps are delivered to developers.

### 11. [MaskOps](https://github.com/fcarvajalbrown/MaskOps) [![GitHub stars](https://img.shields.io/github/stars/fcarvajalbrown/MaskOps?style=social&color=white)](https://github.com/fcarvajalbrown/MaskOps/stargazers)
- **Primary Focus**: ⚡ Rust-Powered Apache Arrow / Polars PII Masking Plugin
- **Tech Stack**: Rust, Python (Polars)
- **License**: MIT
- **Summary**: Native Polars plugin engineered for ultra-high-throughput tabular data pipelines. Benchmarked at **~479,000 rows/second** (4,800× faster than typical Python NLP loops), providing instant regex, check-digit validation, and format-preserving masking.

### 12. [Blindfold](https://github.com/blindfold-dev/Blindfold) [![GitHub stars](https://img.shields.io/github/stars/blindfold-dev/Blindfold?style=social&color=white)](https://github.com/blindfold-dev/Blindfold/stargazers)
- **Primary Focus**: 🛡️ Multi-Language PII Masking SDK &amp; MCP Server
- **Tech Stack**: Python, TypeScript, Go, Java, .NET
- **License**: Open Source
- **Summary**: Developer-first privacy toolkit supporting 8 core operations (detect, redact, mask, tokenize, detokenize, hash, encrypt, synthesize). Operates 100% offline with zero network calls and provides a native Model Context Protocol (MCP) server for AI coding assistants.

---

## 📈 Star History

[![Star History Chart](https://star-history.dera.page/svg?repos=ishandutta2007/Awesome-Dynamic-Data-Masking&type=date&legend=top-left)](https://star-history.dera.page/#ishandutta2007/Awesome-Dynamic-Data-Masking&type=date&legend=top-left)

---

## 💖 Support &amp; Community

Thank you for exploring this curated directory! If this guide helped you assess dynamic data masking tools, architect data privacy workflows, or safeguard sensitive databases, please consider supporting the project:

- ⭐ **Star this repository** to help others find it on GitHub
- 🍴 **Fork and share** with your data engineering and cybersecurity peers
- ☕ **Sponsor or buy a coffee**: [Sponsor ishandutta2007 on GitHub Sponsors](https://github.com/sponsors/ishandutta2007)

---

## 🤝 How to Contribute

Contributions from data security practitioners, compliance leads, and open-source maintainers are warmly welcomed!

1. 🍴 Fork the repository.
2. ✍️ Add or update entries following the established table / ranked list formats.
3. 🔗 Verify that all product URLs, starting tier pricing figures, free limits, and repository links are accurate and factual.
4. 🚀 Submit a Pull Request with a concise summary of your changes.

---

## ⚖️ Architecture Insights &amp; Disclaimer

- **Native In-Engine vs. Inline Proxy vs. Application Libraries**: 
  - **Native In-Engine (Snowflake, Apache Ranger, PostgreSQL Anonymizer, Bytebase)**: Enforces masking directly inside the database query engine. Highly secure and eliminates network hops, but requires engine-specific configuration.
  - **Transparent Inline Proxy (Satori, Hoop.dev, Cyral)**: Intercepts queries on the wire. Zero changes to database schemas, rapid setup, but adds minor network latency overhead (<5ms).
  - **Application Libraries (Presidio, Blindfold, MaskOps)**: Redacts or masks data in code prior to persistence or display. Ideal for unstructured text and LLM prompts, but does not provide database-level protection.
- **Cost Transparency**: Native cloud data warehouse masking can carry significant surcharges (e.g., Snowflake requires upgrading to Enterprise Edition, creating a **+50% compute cost increase across all workloads**). Always calculate overall infrastructure implications before selecting an enforcement strategy.
- **Compliance Reminder**: Masking is one pillar of a defense-in-depth posture. Always combine query-time redaction with robust access controls, encryption-at-rest, and comprehensive audit logging to ensure full compliance with GDPR, HIPAA, PCI-DSS, and DPDP frameworks.

---

<p align="center">
  <strong>Maintained with ❤️ by <a href="https://github.com/ishandutta2007">Ishan Dutta</a> and the open-source data security community.</strong>
</p>
