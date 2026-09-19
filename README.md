# Hi there, I'm Swapna Tondapu 👋

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/swapnatondapu)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:swapnatondapu7@gmail.com)
[![AWS Certified](https://img.shields.io/badge/AWS%20Certified%20Data%20Engineer-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](https://aws.amazon.com/certification/certified-data-engineer-associate/)

**Data Engineer @ American Express** — I build the batch and streaming pipelines behind card transactions: roughly **1M transactions and ~8 TB a day**.

I care about the unglamorous half of data engineering — the part where a number has to be *the same* the second time you ask for it. Late-arriving data, idempotent reloads, reconciliation between systems that disagree, and tests that fail before a finance team finds the problem.

---

## 👩‍💻 About Me

🔭 Currently a **Data Engineer at American Express** (Palo Alto), working on authorization and settlement pipelines — Spark and Hive batch jobs, Kafka and Flink streams, orchestrated in Airflow and served through ClickHouse and Grafana.

🎓 **MS in Business Analytics, Texas A&M University** (GPA 4.0)

📜 **AWS Certified Data Engineer – Associate**

🏢 Previously at **Johnson & Johnson Consumer Health** (data platform and quality tooling) and **JioSaavn**

⚡ Things I've actually shipped:
- Cut a daily merchant aggregation's runtime **~25%** by repartitioning skewed joins and tuning Spark SQL
- Built Presto reconciliation checks that catch schema drift **before** it reaches downstream consumers
- Maintain an **SCD2 merchant dimension** and incremental loads with late-arrival handling

📫 Reach me at **swapnatondapu7@gmail.com**

---

## 🛠 Tech Stack

**Processing & Streaming**

![Apache Spark](https://img.shields.io/badge/Apache%20Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache%20Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![Flink](https://img.shields.io/badge/Apache%20Flink-E6526F?style=for-the-badge&logo=apacheflink&logoColor=white)
![Hive](https://img.shields.io/badge/Apache%20Hive-FDEE21?style=for-the-badge&logo=apachehive&logoColor=black)

**Orchestration & Transformation**

![Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=apacheairflow&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?style=for-the-badge&logo=dbt&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)

**Warehouses & Query Engines**

![BigQuery](https://img.shields.io/badge/BigQuery-669DF6?style=for-the-badge&logo=googlebigquery&logoColor=white)
![Redshift](https://img.shields.io/badge/Redshift-8C4FFF?style=for-the-badge&logo=amazonredshift&logoColor=white)
![Presto](https://img.shields.io/badge/Presto-5890FF?style=for-the-badge&logo=presto&logoColor=white)
![ClickHouse](https://img.shields.io/badge/ClickHouse-FFCC01?style=for-the-badge&logo=clickhouse&logoColor=black)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![DuckDB](https://img.shields.io/badge/DuckDB-FFF000?style=for-the-badge&logo=duckdb&logoColor=black)

**Cloud & Platform**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![GCP](https://img.shields.io/badge/Google%20Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white)
![Delta Lake](https://img.shields.io/badge/Delta%20Lake-00ADD4?style=for-the-badge&logo=delta&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

---

## 📊 Projects

### 🏦 [merchant-settlement-dbt](https://github.com/swapnatondapu7-netizen/merchant-settlement-dbt)

**Card authorization vs settlement reconciliation, modelled in dbt.**

The same problem I work on at Amex, expressed in dbt: authorization and settlement arrive as two separate streams that don't line up one-to-one. Settlements land 0–9 days late, amounts drift (tips, partial captures), and some authorizations never settle at all.

- **Incremental model with a late-arrival window** — reprocesses a trailing window and replaces those days wholesale, so a settlement arriving 4 days late still corrects the day it belongs to. *Verified:* injecting a late settlement moved a already-written day from 4 open auths / $173.78 → 3 open auths / $187.87. A naive `where auth_date = current_date` incremental leaves that day under-reported forever.
- **SCD2 merchant dimension** — risk tier and region change; overwriting silently re-attributes historical facts to current attributes, so a report run twice gives two answers.
- **33 passing tests** — `unique`, `not_null`, `relationships` across both streams, plus a reconciliation invariant that I had to *correct*: it initially failed on 2 of 2,699 merchant-days that had only 3 and 13 transactions, where a single legitimate over-capture dominates the ratio. A test that fails on correct data trains people to ignore it, so it gained a volume floor.

`dbt 1.12` · `DuckDB` · runs locally with no warehouse credentials

---

## 📈 GitHub Stats

![Stats](https://github-readme-stats.vercel.app/api?username=swapnatondapu7-netizen&show_icons=true&theme=tokyonight&hide_border=true&count_private=true)
![Streak](https://github-readme-streak-stats.herokuapp.com/?user=swapnatondapu7-netizen&theme=tokyonight&hide_border=true)
![Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=swapnatondapu7-netizen&layout=compact&theme=tokyonight&hide_border=true)

---

<p align="center">
  <i>Open to mid-level Data Engineer and Analytics Engineer roles across the US.</i>
</p>
