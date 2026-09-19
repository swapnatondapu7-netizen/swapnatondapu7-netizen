<h1 align="center">Swapna Tondapu</h1>

<p align="center">
  <b>Data Engineer @ American Express</b> · Santa Clara, CA<br>
  I work on the data pipelines behind about <b>1M card transactions a day</b>.
</p>

<p align="center">
  <a href="https://linkedin.com/in/swapnatondapu"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:swapnatondapu7@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
  <img src="https://img.shields.io/badge/AWS%20Certified-Data%20Engineer%20Associate-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AWS Certified">
  <img src="https://img.shields.io/badge/Open%20to-Data%20%26%20Analytics%20Engineering-2ea44f?style=for-the-badge" alt="Open to work">
</p>

---

### A bit about me

I got into data engineering because almost everything in tech now runs on data. Whether a product works, what a company builds next, how a bank spots a problem, all of it comes back to whether the data is there and whether you can trust it. I liked the idea of working on that part.

What I enjoy most is building pipelines people can rely on. Getting the same answer when you run something twice. Making sure late data still gets counted. Catching a problem in the pipeline before it turns into a wrong number in someone's report.

At American Express I work on the data behind card transactions, around 1M a day. I use Spark and Hive for the batch jobs, Kafka and Flink for the authorization and settlement events, Airflow to schedule everything, and ClickHouse with Grafana so people can see the numbers.

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

Some things I have actually done, not just used:

- Made a daily merchant job about **25% faster**. The problem was skewed joins, so I repartitioned the data and tuned the Spark SQL.
- Wrote the **Presto checks** that catch a schema change before it reaches the teams using the data.
- Look after an **SCD2 merchant table** and the incremental loads, so late settlements get counted without rewriting old history.

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

**The late settlement problem, built in dbt.**

Authorizations and settlements come in as two separate streams that do not match up. Settlements can be days late, the amount can change because of tips, and some authorizations never settle at all. None of these throw an error. They just make the number wrong.

So the model goes back over the last few days each run instead of only today, keeps merchant history with a snapshot so changing a merchant does not change last quarter's numbers, and has tests that only fail when something is really wrong.

> I checked that this actually works instead of assuming it. I added a settlement that arrived 4 days late, ran the model again, and the old day corrected itself from **4 unsettled / $173.78** to **3 / $187.87**.

</td></tr>
<tr><td width="100%">

#### [streaming-recon](https://github.com/swapnatondapu7-netizen/streaming-recon)

<a href="https://github.com/swapnatondapu7-netizen/streaming-recon"><img src="https://img.shields.io/badge/Apache%20Flink-1.20-E6526F?style=flat-square&logo=apacheflink&logoColor=white"></a>
<img src="https://img.shields.io/badge/Kafka-3.8-231F20?style=flat-square&logo=apachekafka&logoColor=white">
<img src="https://img.shields.io/badge/checks-7%2F7%20passing-2ea44f?style=flat-square">

**The same problem, but on the stream side.**

Two Kafka streams that do not line up, matched in Flink SQL on event time. An interval join so the job does not have to remember both sides forever, and LEFT joins so the transactions that never match get reported instead of quietly disappearing.

> It found all 5 authorizations that never settled and all 3 settlements with no authorization, and still matched a settlement that arrived **6 days late**. `./run.sh` goes from an empty Docker to 7/7 checks in about two minutes.

</td></tr>
<tr><td width="100%">

#### [schema-matcher](https://github.com/swapnatondapu7-netizen/schema-matcher)

<a href="https://github.com/swapnatondapu7-netizen/schema-matcher"><img src="https://img.shields.io/badge/sentence--transformers-MiniLM-FFD21E?style=flat-square"></a>
<img src="https://img.shields.io/badge/CPU%20only-no%20API%20key-2ea44f?style=flat-square">
<img src="https://img.shields.io/badge/26%2F36%20right-1%20wrong-blue?style=flat-square">

**Using a model for the boring half of onboarding a feed.**

Every partner sends the same facts under different column names, and somebody maps them by hand. This does the first pass with embeddings, comparing what is *in* a column as well as what it is called, so a column named `COL_7` still gets recognised from its values.

> The important part is that it is allowed to say it does not know. A wrong mapping is silent and turns up in a report later, so the threshold is chosen with an explicit 10:1 cost of a wrong answer against a human review.

</td></tr>
<tr><td width="100%">

#### [pipeline-anomaly](https://github.com/swapnatondapu7-netizen/pipeline-anomaly)

<a href="https://github.com/swapnatondapu7-netizen/pipeline-anomaly"><img src="https://img.shields.io/badge/scikit--learn-1.7-F7931E?style=flat-square&logo=scikitlearn&logoColor=white"></a>
<img src="https://img.shields.io/badge/pandas-2.3-150458?style=flat-square&logo=pandas&logoColor=white">
<img src="https://img.shields.io/badge/9%2F9%20caught-3%20false%20alarms%2Fwk-2ea44f?style=flat-square">

**Catching the job that succeeds and loads half the data.**

A crash is easy, someone gets paged. The expensive one reports success after loading 40% of the rows. Volume moves with the hour, the weekday and month end, so a fixed threshold either fires every night or catches nothing.

> Scored the way you would actually judge it: what got caught, how long it took, and how many false alarms a week. Waiting three hours before alerting took false alarms from 20 a week to 3. An Isolation Forest found no more than the medians did, at 91 a week, and the README says so.

</td></tr>
</table>

---

### What I'm working on now

<table>
<tr><td width="33%" valign="top" align="center">

**Closing the dbt gap**

Doing the transformations, dependencies and tests I already do by hand, but in dbt, where they live in one place.

</td><td width="33%" valign="top" align="center">

**Backfills that do not hurt**

Reprocessing a month of history without taking the pipeline down or double counting anything. Mostly a question of making jobs safe to run twice.

</td><td width="33%" valign="top" align="center">

**Data contracts**

Writing tests that only fail when data is really wrong. If a test keeps failing on good data, people stop reading it.

</td></tr>
</table>

---

<p align="center">
  <b>Open to mid-level Data Engineer / Analytics Engineer roles across the US.</b><br>
  <sub>Currently in Santa Clara, happy to relocate · <a href="mailto:swapnatondapu7@gmail.com">swapnatondapu7@gmail.com</a></sub>
</p>
