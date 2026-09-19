<h1 align="center">Swapna Tondapu</h1>

<p align="center">
  <b>Data Engineer @ American Express</b> · Santa Clara, CA<br>
  I keep the pipelines behind <b>~1M card transactions and ~8 TB a day</b> honest.
</p>

<p align="center">
  <a href="https://linkedin.com/in/swapnatondapu"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:swapnatondapu7@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
  <img src="https://img.shields.io/badge/AWS%20Certified-Data%20Engineer%20Associate-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AWS Certified">
  <img src="https://img.shields.io/badge/Open%20to-Data%20%26%20Analytics%20Engineering-2ea44f?style=for-the-badge" alt="Open to work">
</p>

---

### A bit about me

I fell into data engineering through the unglamorous door: someone asked why a number in a report had changed overnight, and I went looking. A settlement had landed four days late and quietly rewritten a day everyone thought was finished.

That's still the part of the job I like most. Not the dashboards — the promise underneath them. That the number is the same the second time you ask. That late data corrects itself instead of silently vanishing. That when two systems disagree, something tells you before the finance team does.

Day to day at **American Express** that means Spark and Hive over card transactions, Kafka and Flink for authorization and settlement events, Airflow holding it together, and ClickHouse with Grafana at the front so people can actually see it.

<br>

<table>
<tr><td width="50%" valign="top">

**Education**

`MS Business Analytics` — Texas A&M University
GPA 4.0 · Aug 2022 – Dec 2023

**Certification**

`AWS Certified Data Engineer – Associate`

</td><td width="50%" valign="top">

**Experience**

`Data Engineer` — **American Express**, Palo Alto
Jan 2024 – present

`Data Platform` — **Johnson & Johnson** Consumer Health
Prior: **JioSaavn**

</td></tr>
</table>

---

### What I actually work on

```mermaid
flowchart LR
    A["Card<br/>transactions"] -->|Kafka| B["Flink<br/>auth + settlement<br/>streams"]
    A -->|batch| C["Spark / Hive<br/>merchant aggregation<br/>~8 TB/day"]
    B --> D["Delta Lake<br/>/ warehouse"]
    C --> D
    D --> E["Presto<br/>reconciliation<br/>checks"]
    D --> F["ClickHouse<br/>+ Grafana"]
    G["Airflow"] -.orchestrates.-> C
    G -.orchestrates.-> E

    style A fill:#2563eb,stroke:#1e40af,color:#fff
    style B fill:#e6526f,stroke:#9f1239,color:#fff
    style C fill:#e25a1c,stroke:#9a3412,color:#fff
    style D fill:#00add4,stroke:#0e7490,color:#fff
    style E fill:#5890ff,stroke:#1e40af,color:#fff
    style F fill:#f46800,stroke:#9a3412,color:#fff
    style G fill:#017cee,stroke:#1e40af,color:#fff
```

A few things I'm proud of rather than just familiar with:

- Cut a daily merchant aggregation's runtime by **~25%** — the culprit was skewed joins, fixed by repartitioning and tuning the Spark SQL
- Built the **Presto reconciliation checks** that catch schema drift before it reaches anyone downstream
- Maintain an **SCD2 merchant dimension** and incremental loads that handle late-arriving settlements without rewriting history

---

### Tools I reach for

<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white">
<img src="https://img.shields.io/badge/Apache%20Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white">
<img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white">
<img src="https://img.shields.io/badge/Flink-E6526F?style=flat-square&logo=apacheflink&logoColor=white">
<img src="https://img.shields.io/badge/Hive-FDEE21?style=flat-square&logo=apachehive&logoColor=black">
</p>
<p>
<img src="https://img.shields.io/badge/Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white">
<img src="https://img.shields.io/badge/dbt-FF694B?style=flat-square&logo=dbt&logoColor=white">
<img src="https://img.shields.io/badge/Databricks-FF3621?style=flat-square&logo=databricks&logoColor=white">
<img src="https://img.shields.io/badge/Delta%20Lake-00ADD4?style=flat-square&logo=delta&logoColor=white">
</p>
<p>
<img src="https://img.shields.io/badge/BigQuery-669DF6?style=flat-square&logo=googlebigquery&logoColor=white">
<img src="https://img.shields.io/badge/Redshift-8C4FFF?style=flat-square&logo=amazonredshift&logoColor=white">
<img src="https://img.shields.io/badge/Presto-5890FF?style=flat-square&logo=presto&logoColor=white">
<img src="https://img.shields.io/badge/ClickHouse-FFCC01?style=flat-square&logo=clickhouse&logoColor=black">
<img src="https://img.shields.io/badge/DuckDB-FFF000?style=flat-square&logo=duckdb&logoColor=black">
</p>
<p>
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white">
<img src="https://img.shields.io/badge/GCP-4285F4?style=flat-square&logo=googlecloud&logoColor=white">
<img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white">
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white">
<img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white">
</p>

---

### Projects

<table>
<tr><td width="100%">

#### [merchant-settlement-dbt](https://github.com/swapnatondapu7-netizen/merchant-settlement-dbt)

<a href="https://github.com/swapnatondapu7-netizen/merchant-settlement-dbt"><img src="https://img.shields.io/badge/dbt-1.12-FF694B?style=flat-square&logo=dbt&logoColor=white"></a>
<img src="https://img.shields.io/badge/DuckDB-local-FFF000?style=flat-square&logo=duckdb&logoColor=black">
<img src="https://img.shields.io/badge/tests-33%20passing-2ea44f?style=flat-square">

**The four-days-late settlement problem, modelled properly.**

Authorizations and settlements arrive as two streams that refuse to line up — settlements land days late, amounts drift with tips and partial captures, and some authorizations never settle at all. Each one breaks a naive pipeline quietly, which is the dangerous kind.

So I built it the way it should be built: an incremental model that reprocesses a trailing window instead of only today, an SCD2 snapshot so re-tiering a merchant doesn't rewrite last quarter, and tests that fail for the right reasons.

> I proved the late-arrival logic rather than claiming it — injected a settlement arriving 4 days late and watched an already-written day correct itself from **4 open auths / $173.78** to **3 / $187.87**.

</td></tr>
</table>

---

### What I'm working on now

<table>
<tr><td width="33%" valign="top" align="center">

**Closing the dbt gap**

Expressing the transformation, DAG and testing work I do by hand in dbt — models, snapshots and tests rather than three separate systems.

</td><td width="33%" valign="top" align="center">

**Streaming reconciliation**

Taking the auth-vs-settlement problem upstream: event-time windows, watermarks, and what to do with the event that arrives late.

</td><td width="33%" valign="top" align="center">

**Data contracts**

Tests that fail for the right reasons. A check that fires on correct data teaches people to ignore checks.

</td></tr>
</table>

---

<p align="center">
  <b>Open to mid-level Data Engineer / Analytics Engineer roles across the US.</b><br>
  <sub>Currently in Santa Clara, happy to relocate · <a href="mailto:swapnatondapu7@gmail.com">swapnatondapu7@gmail.com</a></sub>
</p>
