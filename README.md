<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
  <img alt="Gopi Perumalla, software engineer: Java, Kafka, AWS Bedrock" src="assets/banner-light.svg" width="100%">
</picture>

<p align="center">
  <a href="https://linkedin.com/in/gopi-perumalla-data"><img src="https://img.shields.io/badge/LinkedIn-gopi--perumalla--data-0A66C2?style=flat-square" alt="LinkedIn"></a>
  <a href="mailto:gopiperumalla25@gmail.com"><img src="https://img.shields.io/badge/Email-gopiperumalla25%40gmail.com-0f766e?style=flat-square" alt="Email"></a>
  <img src="https://img.shields.io/badge/Cincinnati%2C%20OH-open%20to%20relocation-59636e?style=flat-square" alt="Cincinnati, OH, open to relocation">
</p>

> [!NOTE]
> **Looking for:** Software engineering roles (Java, Spring Boot, GenAI on AWS) in any industry.
> Based in Cincinnati, OH and open to relocation.

## About me

I'm a software engineer specializing in Java and Spring Boot, with experience building and supporting production systems in banking and healthcare.
At Deloitte I built loan payment services for a banking client that post around 150K payments a day. At CloudWave I build Spring Boot services and
Angular pages for a healthcare hosting portal, and practical AI tooling, including a Java MCP server on AWS Bedrock.

The two projects below are built the way I'd want production code to be: measured, tested against failure, and honest about their limits.

## Featured projects

<table>
<tr>
<td width="50%" valign="top">
<a href="https://github.com/PerumallaSG2/event-driven-payment-platform">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/card-payments-dark.svg">
  <img alt="Event-Driven Payment Platform: 155 tests, 15 fault scenarios, fails closed" src="assets/card-payments-light.svg" width="100%">
</picture>
</a>

- Three Spring Boot services: payment API, saga orchestrator, double-entry ledger
- Transactional outbox and inbox, so Kafka's at-least-once delivery never moves money twice
- Fault tests kill services mid-payment and pause Kafka; every run ends in a clean reconciliation

</td>
<td width="50%" valign="top">
<a href="https://github.com/PerumallaSG2/fraud-detection">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/card-fraud-dark.svg">
  <img alt="Fraud Detection API: 52% recall on 555k transactions, 700 tx/s, 98% coverage" src="assets/card-fraud-light.svg" width="100%">
</picture>
</a>

- Five rules (amount spike, velocity, impossible travel, risky merchant, odd hours) and analyst alerts
- Load-tested with k6: 700 transactions/s for 5 minutes, median 2 ms to a decision, on a laptop
- Replayed 555k labeled transactions: half of all fraud flagged for review at an 8% false-positive rate

</td>
</tr>
</table>

### How they work together

```mermaid
flowchart LR
    client([Card payment]) --> pay[Payment platform<br/>holds the funds]
    pay -- "score this" --> fraud[Fraud detection<br/>APPROVE / REVIEW / BLOCK]
    fraud -- "APPROVE" --> cap[Capture]
    fraud -- "REVIEW" --> hold[Hold until an analyst decides]
    fraud -- "BLOCK or unavailable" --> rel[Release the hold]
```

## Experience

**Software Engineer · CloudWave** · Nov 2025 – Present
Java and Spring Boot backend of a customer portal hospital IT teams use to check uptime, backups and disaster-recovery status.

- Built a backup verification check that flags failed or missed nightly jobs before the morning shift
- Built Angular status pages (backup history, DR tests, open tickets) with Redis caching on the Spring Boot APIs
- Helped migrate services from Spring Boot 2.7 to 3.x (Jakarta, Spring Security 6, Hibernate 6)
- Built a Java MCP server with Spring AI giving an AWS Bedrock assistant three read-only tools, each call permission-checked and logged
- Added runbook search with embeddings and OpenSearch so answers link back to the source

**Software Engineer · Deloitte** · Jun 2020 – Aug 2024
Loan servicing platform for a banking client: around 150K payments (about $80M) a day.

- Kafka producers and consumers for postings, reversals and late fees, with idempotent consumers and retry / dead-letter topics that nearly eliminated duplicate postings
- REST APIs for payment scheduling, payoff quotes and status, used by 6 other systems and the customer website
- Redis cache on the busiest lookups: ~800 ms down to under 100 ms
- End-of-day Spring Batch run cut from ~5 hours to under 2
- Daily reconciliation job against the general ledger; breaks reported to finance dropped by more than half
- L2/L3 production support; Resilience4j circuit breakers and Splunk alerts kept services at 99.9% uptime

## Education

**MS in Computer Science** · University of Cincinnati · Aug 2024 – Apr 2026

## Tech stack

**Backend**
<br>
<img src="https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java">
<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white" alt="Spring Boot">
<img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white" alt="Spring Security">
<img src="https://img.shields.io/badge/REST%20APIs-59636e?style=flat-square" alt="REST APIs">
<img src="https://img.shields.io/badge/Spring%20Batch-6DB33F?style=flat-square" alt="Spring Batch">
<img src="https://img.shields.io/badge/Angular-DD0031?style=flat-square&logo=angular&logoColor=white" alt="Angular">
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">

**Messaging and data**
<br>
<img src="https://img.shields.io/badge/Apache%20Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" alt="Kafka">
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL">
<img src="https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white" alt="Oracle">
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="MySQL">
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" alt="Redis">

**AI**
<br>
<img src="https://img.shields.io/badge/Spring%20AI-6DB33F?style=flat-square" alt="Spring AI">
<img src="https://img.shields.io/badge/MCP%20servers-1f2328?style=flat-square" alt="MCP servers">
<img src="https://img.shields.io/badge/AWS%20Bedrock-232F3E?style=flat-square" alt="AWS Bedrock">
<img src="https://img.shields.io/badge/SageMaker-232F3E?style=flat-square" alt="SageMaker">
<img src="https://img.shields.io/badge/RAG-0f766e?style=flat-square" alt="RAG">
<img src="https://img.shields.io/badge/LangChain%20%2F%20LangGraph-1C3C3C?style=flat-square&logo=langchain&logoColor=white" alt="LangChain">

**Cloud, DevOps and observability**
<br>
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square" alt="AWS">
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker">
<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" alt="Kubernetes">
<img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions">
<img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white" alt="Prometheus">
<img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white" alt="Grafana">
