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

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **Snowflake Dynamic Data Masking**

  **Native column-level masking** within Snowflake. Masking policies transform data on-the-fly based on the user's role and permissions—no separate masked copies . **Pricing**: **Enterprise Edition required**—Standard is $2/credit, Enterprise $3/credit (**+50% compute cost across all workloads**), Business Critical $4/credit . **Free tier**: Trial credits. **Best for**: Snowflake customers already on Enterprise wanting native masking—**trade-off**: Standard users pay 50% more on everything just to unlock masking; policy management is SQL-only with no Snowsight UI .



- **Immuta**

  **Data access governance platform** with dynamic data masking across Snowflake, Databricks, BigQuery, Redshift, and more from a single control plane . **Pricing**: **No published tiers, no free tier**; enterprise contracts typically **$100,000–$200,000/year** for mid-market, rising to **$500,000+** for large deployments . **Best for**: enterprises wanting policy-as-code that transforms data at the query layer across multiple platforms—**trade-off**: six-figure minimum; no self-service evaluation.



- **Privacera**

  **Enterprise data encryption and masking** solution with hybrid deployment . **Pricing**: **Commercial, price not published**—sales-led model with no public tiers; free trial may be available on request . **Best for**: organizations wanting enterprise masking with vendor support and SLAs—**trade-off**: entirely sales-gated; no self-serve pricing.



- **ALTR**

  **Cloud-native data control** for Snowflake with discovery, masking, and tokenization. **Pricing**: **Starting at $10 per user per month**—the only platform in this list with published per-user pricing . **Free tier**: Yes, can start for free and upgrade as needed . **Best for**: Snowflake-centric teams wanting accessible masking without enterprise commitment—**trade-off**: Snowflake-focused; not multi-platform.



- **Satori**

  **Agentless data security platform** with dynamic masking and just-in-time access provisioning . **Pricing**: **Commercial, price not published** . **Architecture**: **Transparent inline proxy**—sits between user/agent and database, applying row/column/cell-level masking in real time **without modifying source data**; deployment in minutes as sidecar or SaaS proxy; **<5ms average query latency overhead** . **Best for**: teams wanting rapid deployment across multiple data stores without touching database schemas—**trade-off**: proxy throughput limits; less suited for deeply nested multi-tenant data mesh architectures .



- **Protegrity**

  **Enterprise data protection** with tokenization, encryption, masking, and anonymization. **Pricing**: **Quote-based**—custom quote by data estate and needs . **Best for**: large regulated enterprises needing field-level protection across cloud warehouses without proxy overhead—**trade-off**: overkill for simple test-data masking; enterprise complexity .



- **Cyral**

  **Data security platform** with attribute-based field-level masking. **Pricing**: Quote-only (inferred from enterprise positioning; case study confirms masking capability) . **Best for**: teams wanting defense-in-depth with field-level masking—**trade-off**: limited public information on pricing and standalone availability.



- **Baffle**

  **No-code data protection** with dynamic data masking at the presentation layer. **Pricing**: Third-party listing shows **$0.00** with a **onetime/perpetual license** model—likely a placeholder or incomplete listing . **Best for**: organizations wanting cryptographic protection of specific columns—**trade-off**: verify actual pricing directly; listing appears unreliable.



- **Mentis**

  **Enterprise sensitive data security suite** with **iMask** for dynamic data masking. **Pricing**: **Cloud plans from $50/month** (Individual, 1 user) to **$3,000/month** (Medium Business, 100 users); **annual discounts up to 20%** . **Features**: Role-based, conditional, and location-aware masking; database and application-level embedding with **<5% performance overhead** (vs. proxy-based approaches) . **Best for**: teams wanting published pricing with database-embedded masking—**trade-off**: NoSQL support was on roadmap (verify current status); less strong on unstructured data .



- **Delphix**

  **Data masking for Databricks lakehouse** (Hyperscale Compliance). **Pricing**: **BYOL** (bring your own license) + Azure infrastructure costs . **Critical note**: Hyperscale performs **static masking**—it reads Delta files, applies deterministic masking, and writes masked files back. **Not dynamic/query-time masking** . **Best for**: teams needing masked non-production data in Databricks—**not** for runtime DDM.



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
