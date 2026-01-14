# Yirla Security: Audit, Logging, and Accountability Architecture

## 📌 Overview
Yirla maintains a high-integrity security posture by ensuring that every action—from application-level API calls to infrastructure-level configuration changes—is captured, monitored, and archived. This document outlines our multi-layered approach to auditability, ensuring compliance and "Zero-Trust" observability.

---

## 🏗️ Audit & Logging Architecture



### 1. Ingestion & Application Processing
The lifecycle of an audit log begins at the **Application Layer**, powered by **FastAPI**.

* **User Action Ingestion:** We capture events from three primary sources: User UI interactions, programmatic API calls, and automated system-to-service communication.
* **Contextual Enrichment:** Our middleware injects tenant-specific metadata (Tenant ID, User ID, Session ID) into every log.
* **RBAC Enforcement:** Logs specifically track authorization checks, capturing both successful access and denied attempts.
* **Data Provenance:** We generate specific audit events for data reads, exports, and administrative support actions to ensure a clear chain of custody.

### 2. Real-Time Monitoring & Security SIEM
Logs are funneled into **Datadog** for real-time ingestion and observability.

* **Structured JSON:** All logs follow a strict JSON schema for machine-readability and rapid querying.
* **Access Control:** The monitoring environment is protected by **Multi-Factor Authentication (MFA)** and granular **RBAC**.
* **Active Alerting:** Real-time monitors detect and alert on anomalous patterns, such as credential stuffing or bulk data exfiltration attempts.

### 3. Intelligent Threat Detection
**AWS GuardDuty** consumes log streams to perform continuous security analysis.
* **Anomaly Detection:** Uses machine learning to identify credential misuse and unauthorized API calls.
* **Infrastructure Defense:** Monitors for signs of data exfiltration or communication with known malicious IP addresses.

---

## 🔒 Immutability and Infrastructure Integrity

### Long-Term Audit Archive (Amazon S3)
To satisfy regulatory requirements, logs are archived in a **dedicated, isolated AWS account** using Amazon S3 with **Object Lock**.

| Component | Specification | Benefit |
| :--- | :--- | :--- |
| **Storage Model** | **WORM** (Write Once, Read Many) | Prevents deletion or modification of records. |
| **Encryption** | **AES-256** (at rest) | Ensures data confidentiality even if physical disks are accessed. |
| **Integrity** | **Object Lock (Compliance Mode)** | Even Root administrators cannot bypass retention periods. |
| **Isolation** | **Cross-Account Storage** | Prevents log tampering if the primary application account is compromised. |
| **Retention** | **1–7 Years** | Customizable based on specific tenant or regulatory needs. |

### AWS Control Plane Integration
We utilize **AWS CloudTrail** to monitor the underlying infrastructure. This includes:
* Changes to **IAM** roles and policies.
* Access requests to **RDS** (Databases), **KMS** (Encryption Keys), and **Secrets Manager**.
* CloudTrail streams directly to the immutable S3 archive, ensuring an independent trail of infrastructure changes.

---

## 📊 Strategic Context: Why This Matters for Performance
In the context of Demand Gen and Performance Marketing, this architecture ensures that the data used for **ROAS and Pipeline analysis** is untampered and verifiable. 

When marketing dashboards show a divergence between CTR and Pipeline, our Audit Architecture allows teams to trace back the **exact account signals** and **API calls** to determine if the drop is due to technical attribution failure or actual market fatigue.

---

## 📈 Compliance Summary
This architecture is designed to exceed the requirements of:
* **SOC2 Type II:** For system availability and confidentiality.
* **HIPAA/GDPR:** Regarding data access traceability and "The Right to be Informed."
* **ISO 27001:** For comprehensive security logging and monitoring.

***

*Note: For a deep dive into how we use this data to solve the "High CTR / Low ROAS" paradox, see our [Performance Strategy Guide](./PIPELINE_VS_CTR.md).*
