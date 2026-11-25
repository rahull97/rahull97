<div align="center">

# Hey, I'm Rahul 👋

### Data Engineer · Building resilient data platforms on AWS

**Software Engineer II at JPMorgan Chase · Mumbai, India**

> *Show up every day. Build it to last. Never stop learning.*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-rahull97-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rahull97/)
[![Email](https://img.shields.io/badge/Email-Say_hi-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:techrahullalwani@gmail.com)
![Experience](https://img.shields.io/badge/Experience-7%2B_years-2EA043?style=flat-square)
![SnowPro Core](https://img.shields.io/badge/SnowPro_Core-Certified-29B5E8?style=flat-square&logo=snowflake&logoColor=white)

</div>

---

### 🧭 About me

I'm a data engineer who likes hard, unglamorous problems: the ones you only solve with patience and steady effort. Over 7+ years I've gone from tuning Kafka clusters to designing **disaster recovery for a 500+ TB banking data lake**, learning each layer of the stack by building on it.

What drives me is simple: **data platforms that people can trust**, even on their worst day.

---

### 🧗 The climb so far

Every role was a step up built on the one before it. No shortcuts, just compounding.

```text
                                                        ┌──────────────────────────────┐
                                                        │ 2024 → now · JPMorgan Chase  │
                                                        │ Software Engineer II         │
                                                        │ Multi-region DR for a 500+ TB│
                                                        │ data lake · RTO < 1 hour     │
                                   ┌────────────────────┴───────────┬──────────────────┘
                                   │ 2022 → 2024 · MarketCast       │
                                   │ Senior Data Engineer           │
                                   │ 50M+ events/day · reports from │
                                   │ 2 days → 4 hours               │
              ┌────────────────────┴───────────────┬────────────────┘
              │ 2019 → 2022 · Abzooba              │
              │ Big Data & Cloud Developer         │
              │ Kafka + Druid at 1M+ events/sec    │
              │ Open-source PySpark DICOM package  │
──────────────┴────────────────────────────────────┘
 2015 → 2019 · B.E. Computer Engineering (CGPA 8.61 / 10)
```

---

### ⚡ Proof of work

<div align="center">

| 🗄️ **500+ TB** | ⏱️ **< 1 hr RTO** | 🪣 **380+ S3 buckets** | 📈 **50M+ events/day** | 🚀 **1M+ events/sec** |
|:---:|:---:|:---:|:---:|:---:|
| data lake made multi-region | recovery after a region failure | DR provisioning, fully automated | PySpark ingestion pipelines | Kafka + Druid ingestion, tuned |

</div>

---

### 🏗️ Perseverance, in architecture form

When a whole AWS region fails, the people using the CCB Data Lake shouldn't notice. Designing for the day everything goes wrong is what I'm proudest of:

```mermaid
flowchart LR
    C["📊 Consuming apps<br/>(no client changes)"] --> G{{"🌐 Global endpoint<br/>routes to the healthy region"}}

    subgraph E["us-east-1 · primary"]
        direction TB
        S3E[("Amazon S3<br/>Iceberg + non-Iceberg data")]
        GCE["AWS Glue Data Catalog"]
        LFE["AWS Lake Formation<br/>permissions"]
        ATE["Amazon Athena"]
    end

    subgraph W["us-west-2 · standby"]
        direction TB
        S3W[("Amazon S3<br/>replica")]
        GCW["AWS Glue Data Catalog"]
        LFW["AWS Lake Formation<br/>permissions"]
        ATW["Amazon Athena"]
    end

    G -->|healthy| ATE
    G -.->|failover| ATW
    S3E == "data replication" ==> S3W
    GCE == "metadata replication" ==> GCW
    LFE == "access-control replication" ==> LFW
```

- **Global endpoint** sends traffic to whichever region is healthy, so failover needs no change on the client side.
- **Cross-region Glue Catalog replication** keeps Apache Iceberg and non-Iceberg tables consistent in both regions.
- **Lake Formation permission replication** means access controls still hold after failover.
- **Automated lifecycle for 380+ S3 buckets** replaced manual provisioning for DR readiness.

---

### 📐 Discipline: how I work

| Principle | What it looked like in practice |
|---|---|
| **Design for the bad day** | Multi-region resiliency so a region outage costs under an hour, not days. |
| **Automate the second time** | 380+ S3 buckets went from manual setup to fully automated lifecycle management. |
| **Measure the impact** | Survey pipelines that cut report turnaround from 2 days to 4 hours. |
| **If it isn't observable, it isn't done** | Near real-time CPU, memory, network and disk monitoring with Prometheus and Grafana. |
| **Push the limits, then hold them** | Tuned Kafka and Druid to sustain 1M+ events per second under heavy load. |

---

### 🔥 Passion: learning in public

- 📦 **Gave back to open source:** built a PySpark library for reading and analysing DICOM medical images at scale, published as a third-party Spark package.
- 🎓 **Learned beyond the day job:** earned the **SnowPro Core Certification** from Snowflake.
- 🔁 **Kept widening the stack:** from streaming (Kafka, Druid) to batch (PySpark) to lakehouse (Iceberg, Glue, Lake Formation) to cloud architecture (multi-region HA/DR, Terraform).
- 🌱 **Currently going deeper on:** Apache Iceberg at scale, lakehouse architecture, and resilient cloud data platforms.

---

### 🧰 Toolbox

| Area | Tools |
|---|---|
| **Languages** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white) |
| **Lakehouse & processing** | ![Apache Iceberg](https://img.shields.io/badge/Apache_Iceberg-2C3E50?style=flat-square&logo=apache&logoColor=white) ![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=flat-square&logo=apachespark&logoColor=white) ![Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white) ![Druid](https://img.shields.io/badge/Apache_Druid-29F1FB?style=flat-square&logo=apachedruid&logoColor=black) ![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=flat-square&logo=snowflake&logoColor=white) |
| **AWS** | ![S3](https://img.shields.io/badge/S3-569A31?style=flat-square&logo=amazons3&logoColor=white) ![Glue](https://img.shields.io/badge/Glue-8C4FFF?style=flat-square) ![Lake Formation](https://img.shields.io/badge/Lake_Formation-527FFF?style=flat-square) ![Athena](https://img.shields.io/badge/Athena-8C4FFF?style=flat-square) ![Lambda](https://img.shields.io/badge/Lambda-FF9900?style=flat-square&logo=awslambda&logoColor=white) ![EC2](https://img.shields.io/badge/EC2-FF9900?style=flat-square) ![RDS](https://img.shields.io/badge/RDS-527FFF?style=flat-square) ![SQS](https://img.shields.io/badge/SQS-FF4F8B?style=flat-square) ![IAM](https://img.shields.io/badge/IAM-DD344C?style=flat-square) ![CloudWatch](https://img.shields.io/badge/CloudWatch-FF4F8B?style=flat-square) |
| **Architecture & IaC** | ![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white) ![Multi-region](https://img.shields.io/badge/Multi--region-HA_%2F_DR-0E7C86?style=flat-square) |
| **Observability & BI** | ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white) ![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white) ![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat-square&logo=tableau&logoColor=white) |

**Concepts:** data lakes & lakehouses · ETL/ELT · data modelling · data warehousing · high availability · disaster recovery

---

<details>
<summary><b>💼 Full experience (click to expand)</b></summary>

**Software Engineer II · JPMorgan Chase & Co.** · Apr 2024 – present
- Designed multi-region resiliency for the CCB Data Lake (500+ TB) across us-east-1 and us-west-2, bringing RTO under 1 hour.
- Architected a global endpoint that routes traffic to the healthy region, with no client-side changes on failover.
- Built cross-region metadata replication for AWS Glue Data Catalog tables (Iceberg and non-Iceberg).
- Replicated AWS Lake Formation permissions across regions so access controls hold after failover.
- Automated creation and lifecycle management of 380+ S3 buckets for DR readiness.

**Senior Data Engineer · MarketCast** · Apr 2022 – Apr 2024
- PySpark ETL ingesting 50M+ pixel-tracker events/day across web and connected devices.
- Survey processing pipelines behind cross-tabs and Tableau dashboards; turnaround cut from 2 days to 4 hours.
- Joined retail purchase data with TV ad viewership to measure advertising impact on brand sales.

**Big Data & Cloud Developer · Abzooba** · Jul 2019 – Apr 2022
- PySpark library for DICOM medical images at scale, published as a third-party Spark package.
- Tuned Kafka and Druid to sustain 1M+ events per second.
- Near real-time infrastructure monitoring with Prometheus and Grafana.

**Education:** B.E. Computer Engineering, Sinhgad College of Engineering, SPPU (2015 – 2019) · CGPA 8.61 / 10
**Certification:** SnowPro Core, Snowflake

</details>

---

<div align="center">

### 🤝 Let's build something that lasts

Happy to talk **lakehouse architecture, Apache Iceberg, AWS disaster recovery, or scaling Spark and Kafka pipelines**.

[![Connect on LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rahull97/)
[![Email me](https://img.shields.io/badge/Email_me-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:techrahullalwani@gmail.com)

<sub>*Small steps, every day. That's the whole secret.*</sub>

</div>
