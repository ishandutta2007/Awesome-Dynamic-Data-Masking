# Awesome-Dynamic-Data-Masking

# Awesome-Dynamic-Data-Masking

**Top Dynamic Data Masking (Opensource) 🌟 Star if you like it! 🌟**



**Curated List of SaaS Products & Open-Source GitHub Projects**

*Focused on Query-Time Redaction, Attribute-Based Policies, Proxy Architecture & Self-Hosted Masking Libraries*

**Last updated: November 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Dynamic Data Masking (DDM)**. These tools enable organizations to mask sensitive data in real time—at query time, without creating separate masked copies—so authorized users see full data while others see redacted values, based on role, attribute, or context.



**Examples** include Snowflake Dynamic Data Masking, Immuta, Privacera, ALTR, Satori, Protegrity, Cyral, Baffle, Mentis, and Delphix (the category leaders in commercial space).



**Open-source emphasis**: This section is expanded with every relevant project for self-hosted masking, PII detection libraries, and open policy enforcement. **Critical note**: True open-source dynamic data masking platforms are nearly nonexistent—**Apache Ranger** provides column masking for Hadoop ecosystems, but general-purpose DDM libraries like **Presidio** and **Blindfold** handle detection and redaction in application code, not query-time enforcement. No open-source project matches Immuta's cross-platform policy-as-code or Satori's transparent proxy architecture.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## Sector Overview & Market Dynamics

The global data masking market (encompassing dynamic and static masking) is estimated at **.1B–.3B** and projected to reach **.5B–.5B** by the mid-2030s, growing at a **13–15% CAGR** driven by strict data privacy mandates (GDPR, HIPAA, DPDP) and real-time zero-trust data access. The sector is **moderately concentrated**: foundational cloud warehouses and enterprise giants dominate high-compliance large enterprise tiers, while emerging proxy and policy-as-code providers compete for multi-cloud and lakehouse dynamic governance.

## SaaS/Hosted Platforms

| Platform | Company Valuation / Revenue Scale | Specific Starting Tier Pricing | Free Tier / Trial Limit | Key Architecture & Capabilities |
| :--- | :--- | :--- | :--- | :--- |
| **Snowflake Dynamic Data Masking** | **~– Market Cap** (~.7B+ ARR) | **Enterprise Edition tier required**: Standard compute starts at .00/credit; Enterprise starts at **.00/credit** (+50% compute surcharge across all workloads) | **30-day free trial** with ** in free compute credits** | Native column-level dynamic masking executed inside the engine; RBAC/ABAC SQL policy-based |
| **Immuta** | **.0B Valuation** (Unicorn; Series E) | Custom contract; G-Cloud public schedule lists base user tiers starting from **~£1,000–£1,600/user/year** (typically **,000/yr** platform minimum) | **No public free tier**; 14-to-30 day customized sales-assisted PoC trial upon request | Multi-cloud data access control & policy-as-code layer across Snowflake, Databricks, BigQuery, Redshift |
| **Protegrity** | **~+ Implied Valuation** (~– ARR) | Enterprise unit-based licensing; AWS Marketplace Private Offer starting contracts typically **~,000–,000+/year** | **No self-service free tier**; 30-day enterprise evaluation / PoC available via private offer | High-performance field-level dynamic tokenization, format-preserving encryption (FPE), and masking |
| **Privacera** | **~– Est. Valuation** (~– ARR) | Enterprise sales-led; AWS Marketplace custom contracts typically starting from **~,000–,000/year** | **30-day free trial** for PrivaceraCloud via AWS Marketplace | Apache Ranger-based enterprise unified governance and dynamic masking across hybrid & multi-cloud data estates |
| **Delphix** (Perforce) | **Acquired** (~ debt financing backing deal; ~+ ARR) | BYOL capacity license based on managed source storage, starting at **~,500–,000/TB/year** + cloud infra costs | **No self-service free tier**; guided 30-day PoC evaluation license on request | Continuous Compliance & Hyperscale masking (primarily high-throughput static/subset masking for lakehouses/RDBMS) |
| **Satori** (Commvault) | **Acquired** (Raised .25M prior to acquisition; ~ ARR) | Annual subscription based on protected data locations; entry contracts typically start at **~,000–,000/year** (avg ~,000/year) | **No public free tier**; 14-day assisted PoC trial available on request | Transparent inline database proxy (<5ms latency overhead); agentless dynamic masking without schema changes |
| **ALTR** | **~– Est. Valuation** (~.6M ARR; Series C) | Published self-serve tier starting at ** per user/month** | **Free Forever plan**: permanently free for up to **3 connected databases** with core masking & classification | Cloud-native Snowflake data access governance, dynamic masking, and tokenization via Partner Connect |
| **Cyral** (Varonis) | **Acquired** (Raised – prior to acquisition; ~ ARR) | Identity & repository-based contract tiers; custom starting tiers typically from **~,000–,000/year** | **No public free tier**; 30-day trial environment via AWS Marketplace / sales engagement | Cloud-native stateless interception proxy for real-time attribute-based dynamic masking and activity monitoring |
| **Baffle** | **~– Est. Valuation** (~.5M raised; ~– ARR) | Usage/metered data protection tiers via AWS Marketplace; starting contracts from **~,000–,000/year** | **30-day free trial** available via AWS Marketplace (Baffle Trial for RDS/S3) | No-code dynamic data masking and field-level encryption at the presentation/data-pipeline layer |
| **Mentis** (iMask) | **Privately Held / Bootstrapped-Growth** (~– ARR) | Published cloud tiers starting from **/month** (Individual, 1 user) up to **,000/month** (100 users) | **No public free tier or free trial**; evaluation PoC arranged via enterprise sales | In-database dynamic masking (iMask) with embedded hooks, RBAC/ABAC, and <5% performance overhead |

## Open-Source GitHub Projects



- **Apache Ranger**

  **Centralized security policy framework** (Apache 2.0) — **the only production-grade open-source dynamic masking engine** for Hadoop ecosystems. **Features**: **Dynamic column masking** for Hive—policies apply at query time based on user/group/role; masking types include **Redact, Partial mask (show first/last 4), Hash, Nullify, Date (show only year), and Custom UDF expressions**; **audit log entry generated every time a masking policy is applied** . **Tech stack**: Java. **Deploy**: Self-hosted (Hadoop ecosystem). **Trade-off**: **Hadoop/Hive-centric**—no native support for Snowflake, BigQuery, or modern OLAP databases without additional integration. **Best for**: organizations running Hadoop/Hive needing query-time column masking with audit—the foundation for open-source DDM in that ecosystem.



- **Microsoft Presidio**

  **Open-source PII detection and anonymization** (MIT, ~11k stars) — **the most widely adopted open-source PII toolkit**, for detecting, redacting, masking, and anonymizing sensitive data across text, images, and structured data . **Features**: **NLP-powered detection** (names, locations, organizations via spaCy); **pattern matching** (credit cards, SSNs, emails); **anonymization operators** (redact, mask, hash, replace, encrypt); customizable pipelines. **Tech stack**: Python. **Deploy**: Library, Docker, or API. **Trade-off**: **Library, not a query-time enforcement engine**—it processes data in application code, not at the database layer. **Performance**: Benchmarked at **~85–99 rows/second** with `en_core_web_lg`—**4,000×+ slower than Rust-based maskops** on structured data . **Best for**: developers building custom masking pipelines needing NLP detection for unstructured text—not for database-level DDM.



- **Blindfold**

  **Open-source PII detection and masking SDK** (open source) — **the most developer-friendly open-source masking toolkit** with multi-language support and MCP integration. **Features**: **SDKs for Python, JS/TS, Go, Java, .NET**; **CLI** and **MCP Server** for Claude/Cursor integration; **Operations**: detect, tokenize (reversible), detokenize, redact, **mask** (partial hiding like `***-**-6789`), synthesize, hash, encrypt; **Detection policies**: basic, strict, GDPR, HIPAA, PCI-DSS; **works offline** in local mode without API key . **Tech stack**: Multi-language SDKs. **Deploy**: SDK/CLI/MCP. **Trade-off**: **Application-level masking**—not query-time enforcement; local mode has limited entity types (names, addresses, orgs require API key). **Best for**: developers wanting to add PII masking to applications with minimal integration effort—especially those using AI coding assistants via MCP.



- **VeilDB**

  **Open-source database anonymization platform** (open source) — **the most complete open-source tool for creating masked database dumps** for development teams. **Features**: **Three-component architecture**—Service (configuration/rules), Agent (processing inside your infrastructure), Client (CLI for developers); **Agent runs inside client's infrastructure**—service never accesses production database directly; raw dumps never leave controlled environment unprocessed; configure masking rules, trigger processing, download anonymized dumps . **Tech stack**: Docker, PHP/Symfony. **Deploy**: Self-hosted (Docker Compose). **Trade-off**: **Static masking for dumps**—not dynamic/query-time masking. **Best for**: teams needing safe, production-like databases for development and QA—not runtime DDM.



### Additional Strong Open-Source Options



- **maskops** — High-speed PII masking as a Polars plugin powered by Rust (open source). Benchmarked **4,849× faster than Presidio** on clean data (479,441 rows/s vs. 99 rows/s); covers IBAN, EU VAT, RUT, CPF, CURP, DNI/NIE, NIN, Personalausweis—patterns Presidio lacks . **Note**: **Structured data pipelines only**—no NLP for names/addresses; pair with Presidio for free-text fields. **Best for**: high-volume structured data masking in Python pipelines.

- **@visulima/redact** — TypeScript redaction library (open source). Deep object traversal, circular reference handling, customizable rules, optional NLP via compromise . **Note**: **Application-level redaction**—not database DDM. **Best for**: JavaScript/TypeScript developers masking sensitive data in logs and objects.



**Frameworks for building custom systems**: Combine **Apache Ranger** for Hive query-time masking with **Presidio** or **Blindfold** for application-level PII detection and **VeilDB** for safe development dumps—creating a layered open-source masking stack. **None of these match Immuta's cross-platform policy-as-code or Satori's transparent proxy**, but for specific layers, the options are functional.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, license (for open-source), and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Dynamic data masking platforms handling sensitive data must comply with data protection regulations (GDPR, HIPAA, PCI DSS, etc.) and implement appropriate access controls.

- **The "native masking" vs. "policy-as-code" vs. "transparent proxy" vs. "application library" vs. "static dump masking" distinction is critical.** **Snowflake DDM** is **native masking**—built into the database, but requires Enterprise Edition (+50% compute cost) . **Immuta** is **policy-as-code**—centralized policies across platforms, six-figure pricing . **Satori** is a **transparent proxy**—no database changes, <5ms latency, rapid deployment . **Presidio and Blindfold** are **application libraries**—you integrate masking into your code, not the database. **VeilDB and Delphix** are **static dump masking**—they create masked copies for development, not runtime DDM . **Choose based on whether you need database-native, cross-platform, proxy-based, code-level, or development-copy masking.**

- **Snowflake DDM's hidden cost is the Enterprise upgrade.** If you are on Standard, enabling masking requires upgrading to Enterprise—**50% increase in compute costs across your entire Snowflake usage**, not just masked queries . **Model your total compute before committing.**

- **Immuta's entry point is $100K–$200K/year.** No free tier, no self-service; proof-of-concept engagements only . **ALTR at $10/user/month** is the only published per-user pricing in this category .

- **Satori's proxy architecture is the fastest to deploy**—minutes vs. weeks, no database changes, <5ms latency overhead . **The trade-off**: proxy throughput limits; less suited for complex multi-tenant data mesh.

- **Mentis has the most transparent pricing**—$50/month for 1 user to $3,000/month for 100 users, with database-embedded masking at **<5% overhead** (vs. proxy approaches) . **The trade-off**: NoSQL support historically limited; verify current status .

- **Delphix Hyperscale performs static masking, not dynamic masking.** It reads Delta files, masks them, and writes them back—**zero DBUs consumed for masking**, but it creates masked copies . **Do not evaluate it for runtime DDM.**

- **Presidio's performance is a bottleneck for high-volume structured data**—~85–99 rows/second vs. maskops' 479,441 rows/second . **For high-throughput structured pipelines, maskops is the pragmatic choice; Presidio is for NLP-heavy free text.**

- **Apache Ranger is the only open-source query-time DDM engine**, but it is Hive-centric—no native Snowflake or BigQuery support . **For modern data platforms, commercial DDM is required.**

- Self-hosted open-source solutions require proper infrastructure (Hadoop for Ranger, Docker for VeilDB), security hardening, and ongoing maintenance. **Masking tools handle sensitive data**—ensure your deployment meets your organization's privacy and compliance requirements before connecting production data sources.



---



**Made for data security engineers, privacy teams, and organizations building transparent masking solutions.**

Let's make Dynamic Data Masking more open, data-driven, and query-time aware.
