# Hi there, I'm Rahul 👋

## Software Engineer II | Data Engineering

I build scalable data pipelines and distributed systems that transform raw data into actionable insights. Passionate about big data technologies, cloud-native architectures, and engineering elegant solutions to complex data challenges.

---

## 🛠️ Technology Stack

### Big Data & Processing
![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=for-the-badge&logo=apache-spark&logoColor=white)
![Apache Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apache-spark&logoColor=white)

### Cloud & Data Services
![AWS](https://img.shields.io/badge/Amazon_AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![AWS Lambda](https://img.shields.io/badge/AWS_Lambda-FF9900?style=for-the-badge&logo=aws-lambda&logoColor=white)
![AWS S3](https://img.shields.io/badge/AWS_S3-569A31?style=for-the-badge&logo=amazon-s3&logoColor=white)
![AWS Glue](https://img.shields.io/badge/AWS_Glue-8C4FFF?style=for-the-badge&logo=amazon-aws&logoColor=white)
![AWS Lake Formation](https://img.shields.io/badge/AWS_Lake_Formation-527FFF?style=for-the-badge&logo=amazon-aws&logoColor=white)

### Orchestration & Workflow
![Apache Airflow](https://img.shields.io/badge/Apache_Airflow-017CEE?style=for-the-badge&logo=apache-airflow&logoColor=white)

### Programming Languages
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![Scala](https://img.shields.io/badge/Scala-DC322F?style=for-the-badge&logo=scala&logoColor=white)

---

## 💼 What I Do

```python
from pyspark.sql import SparkSession
from airflow import DAG
import aws_services as aws

# 📊 Data Engineering Pipeline
"""
┌─────────────┐      ┌──────────────┐      ┌─────────────┐      ┌──────────────┐
│   INGEST    │─────▶│  TRANSFORM   │─────▶│   PROCESS   │─────▶│    SERVE     │
│             │      │              │      │             │      │              │
│ • S3        │      │ • PySpark    │      │ • Lambda    │      │ • Data Lake  │
│ • Kafka     │      │ • Glue       │      │ • Airflow   │      │ • Analytics  │
│ • APIs      │      │ • SQL        │      │ • EMR       │      │ • BI Tools   │
└─────────────┘      └──────────────┘      └─────────────┘      └──────────────┘
"""

class DataPipeline:
    """
    Building production-grade data infrastructure that processes
    millions of records daily with 99.9% reliability
    """
    
    def __init__(self):
        self.role = "Software Engineer II | Data Engineering"
        self.mission = "Transform chaos into insights"
        
    def build_pipeline(self):
        # 🔄 Extract
        raw_data = aws.s3.read("s3://data-lake/raw/")
        
        # ⚙️ Transform
        spark = SparkSession.builder.appName("DataPipeline").getOrCreate()
        transformed = spark.sql("""
            SELECT 
                customer_id,
                SUM(revenue) as total_revenue,
                COUNT(*) as transaction_count
            FROM raw_data
            GROUP BY customer_id
        """)
        
        # 🚀 Load
        transformed.write.partitionBy("date").mode("append") \
            .parquet("s3://data-lake/processed/")
        
        return "✅ Pipeline executed successfully"
    
    def orchestrate(self):
        with DAG('etl_pipeline', schedule_interval='@daily') as dag:
            return [
                "🔹 Validate data quality",
                "🔹 Run distributed transformations",
                "🔹 Optimize partition strategies", 
                "🔹 Monitor pipeline health",
                "🔹 Ensure data lineage"
            ]

# 💪 Daily Impact
daily_tasks = {
    "data_processed": "10TB+",
    "pipelines_managed": "50+",
    "uptime": "99.9%",
    "coffee_consumed": "∞"
}
```

---

## 🎯 Core Competencies

- **Data Pipeline Engineering**: Design and build robust, scalable ETL/ELT pipelines
- **Cloud Architecture**: Serverless data processing with AWS Lambda, Glue, and Lake Formation
- **Big Data Processing**: Distributed computing with PySpark for large-scale data transformations
- **Workflow Orchestration**: Complex DAG management and scheduling with Apache Airflow
- **Data Lake Management**: Building and maintaining enterprise data lakes on AWS S3
- **Performance Optimization**: Query tuning, partition strategies, and cost optimization

---

## 📊 GitHub Stats

<div align="center">
  
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=rahull97&show_icons=true&theme=dark&hide_border=true&bg_color=0D1117&title_color=58A6FF&icon_color=58A6FF&text_color=C9D1D9)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=rahull97&layout=compact&theme=dark&hide_border=true&bg_color=0D1117&title_color=58A6FF&text_color=C9D1D9)

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=rahull97&theme=dark&hide_border=true&background=0D1117&stroke=58A6FF&ring=58A6FF&fire=58A6FF&currStreakLabel=C9D1D9)

</div>

---

## 🔗 Connect With Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rahull97/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rahull97)

---

<div align="center">
  
### 💡 "Data is the new oil, but pipelines are the refineries."

![Profile Views](https://komarev.com/ghpvc/?username=rahull97&color=58A6FF&style=flat-square&label=Profile+Views)

</div>
