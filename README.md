<div align="center">

# Hey, I'm Rahul 👋

<a href="https://github.com/rahull97">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=58A6FF&center=true&vCenter=true&width=640&lines=Data+Engineer+%40+JPMorgan+Chase;I+keep+a+500%2B+TB+data+lake+alive+across+regions;AWS+%E2%80%A2+Apache+Iceberg+%E2%80%A2+PySpark+%E2%80%A2+Kafka;7%2B+years+turning+raw+events+into+reliable+data" alt="Typing intro" />
</a>

**Data Engineer · Software Engineer II at JPMorgan Chase · Mumbai, India**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-rahull97-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rahull97/)
[![Email](https://img.shields.io/badge/Email-Say_hi-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:techrahullalwani@gmail.com)
![Experience](https://img.shields.io/badge/Experience-7%2B_years-2EA043?style=flat-square)
![SnowPro Core](https://img.shields.io/badge/SnowPro_Core-Certified-29B5E8?style=flat-square&logo=snowflake&logoColor=white)
![Profile views](https://komarev.com/ghpvc/?username=rahull97&color=58A6FF&style=flat-square&label=Profile+views)

</div>

---

### ⚡ TL;DR

I design **cloud data platforms that don't go down**. At JPMorgan Chase I build the **Consumer & Community Banking (CCB) Data Lake** on AWS and led its **multi-region resiliency and disaster recovery** architecture. Before that, I built Spark and Kafka pipelines handling **tens of millions of events a day** for media analytics and healthcare imaging.

<div align="center">

| 🗄️ **500+ TB** | ⏱️ **< 1 hr RTO** | 🪣 **380+ S3 buckets** | 📈 **50M+ events/day** | 🚀 **1M+ events/sec** |
|:---:|:---:|:---:|:---:|:---:|
| data lake made multi-region | recovery time after a region failure | DR provisioning, fully automated | PySpark ingestion pipelines | Kafka + Druid ingestion, tuned |

</div>

---

### 🏗️ The thing I'm proudest of: a data lake that survives a region outage

When a whole AWS region fails, consumers of the CCB Data Lake shouldn't notice. Here's the shape of what I designed:

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
- Result: **RTO under 1 hour** for a **500+ TB** lake.

---

### 💼 Where I've worked

<table>
<tr>
<td width="140"><b>2024 – now</b></td>
<td>
<b>Software Engineer II · JPMorgan Chase & Co.</b><br/>
Building the CCB Data Lake with Python, SQL, S3, Glue, Lake Formation, Iceberg and Athena. Led its multi-region resiliency and disaster recovery design (the diagram above).
</td>
</tr>
<tr>
<td><b>2022 – 2024</b></td>
<td>
<b>Senior Data Engineer · MarketCast</b><br/>
• PySpark ETL ingesting <b>50M+ pixel-tracker events/day</b> to analyse behaviour across web and connected devices.<br/>
• Survey processing pipelines behind cross-tabs and Tableau dashboards: report turnaround cut from <b>2 days to 4 hours</b>.<br/>
• Joined retail purchase data with TV ad viewership to measure how ads move brand sales.
</td>
</tr>
<tr>
<td><b>2019 – 2022</b></td>
<td>
<b>Big Data & Cloud Developer · Abzooba</b><br/>
• Built a <b>PySpark library for reading and analysing DICOM medical images</b> at scale, published as a third-party Spark package.<br/>
• Tuned Kafka and Druid to sustain <b>1M+ events per second</b> under heavy ingestion.<br/>
• Near real-time infra monitoring (CPU, memory, network, disk) with Prometheus and Grafana.
</td>
</tr>
</table>

---

### 🧰 What I work with

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
<summary><b>🐍 Me, as a Python class (click to expand)</b></summary>

```python
class Rahul:
    role       = "Software Engineer II, Data Engineering @ JPMorgan Chase"
    based_in   = "Mumbai, India"
    experience = "7+ years"

    stack = {
        "lakehouse": ["Apache Iceberg", "AWS Glue", "Lake Formation", "Athena", "S3"],
        "compute":   ["PySpark", "Kafka", "Druid", "Snowflake"],
        "infra":     ["Terraform", "multi-region HA/DR", "Prometheus", "Grafana"],
    }

    def principles(self):
        return [
            "Design for the region that fails, not the one that works.",
            "Automate anything you'd have to do twice (380 buckets taught me that).",
            "A pipeline isn't done until it's observable.",
        ]

    def currently(self):
        return "Making a 500+ TB data lake boring to fail over."
```

</details>

<details>
<summary><b>🎓 Education & certifications</b></summary>

- **B.E. Computer Engineering**, Sinhgad College of Engineering, Savitribai Phule Pune University (2015 – 2019) · CGPA 8.61 / 10
- **SnowPro Core Certification**, Snowflake

</details>

---

<div align="center">

### 🤝 Let's talk

I'm happy to chat about **lakehouse architecture, Apache Iceberg, AWS disaster recovery, or scaling Spark and Kafka pipelines**.

[![Connect on LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rahull97/)
[![Email me](https://img.shields.io/badge/Email_me-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:techrahullalwani@gmail.com)

<sub>⭐ If something here was useful, a follow is appreciated.</sub>

</div>
