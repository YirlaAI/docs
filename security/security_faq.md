# Yirla Security Review: Frequently Asked Questions

> **The Yirla Security Philosophy:** > "Yirla is architected as a read-only, PII-free, tenant-isolated analytics system, with encryption everywhere, no standing super-admin access, and auditability built into every layer."

---

## A. DATA — Ingestion, Processing, and Boundaries

### 1. What customer data does Yirla collect?
We ingest **advertising performance metadata only**: impressions, clicks, spend, creatives, timestamps, and targeting attributes at an aggregate level. We do **not** collect PII (Personally Identifiable Information), user-level identifiers, emails, IP addresses, or LinkedIn member-specific data.

### 2. Do you store raw data or transformed data?
**Both.** Raw data is stored immutably for audit and debugging purposes. Transformed and aggregated datasets are used for analytics surfaced to users. Raw and derived datasets are logically separated to prevent accidental cross-contamination.

### 3. Is any PII stored or processed?
**No.** Our data model is explicitly designed to be **PII-free**. If a source unexpectedly includes PII, it is rejected at the ingestion layer before reaching our databases.

### 4. Is customer data ever mixed across tenants?
**No.** Data is **logically isolated by Tenant ID** at every layer: ingestion, storage, query, and application logic. There is no shared query context across tenants.

### 5. Do you train models on customer data?
**No.** Customer data is never used for training foundation models (LLMs). Any analytics or heuristics are rule-based or operate exclusively on that specific customer’s isolated data.

---

## B. STORAGE — Encryption and Persistence

### 6. Where is data stored geographically?
Primary storage is in **AWS (US regions)**. We can support region pinning (e.g., EU-only) if required by contract.

### 7. How is data encrypted at rest?
All data at rest is encrypted using **AES-256** via AWS-managed KMS keys. We maintain a strict policy of no plaintext storage across all environments.

### 8. Who controls the encryption keys?
Keys are managed by **AWS KMS** with highly restricted IAM policies. We can support **Customer-Managed Keys (CMK)** for enterprise-tier contracts.

### 9. How long do you retain data?
Default retention is **3 months**, though this is configurable per customer. Customers can request deletion at any time; deletes propagate across raw, derived, and backup layers.

### 10. Are backups encrypted and isolated?
**Yes.** Encrypted backups are stored in separate, restricted AWS accounts and are tested quarterly for restore integrity.

---

## C. SECURITY — Policies and Access Control

### 11. How is data encrypted in transit?
All data in transit uses **TLS 1.2+**. Internal service-to-service traffic is also encrypted; we operate on a "Zero-Trust" internal network model.

### 12. Do you have a “God mode” or super-admin access?
There is **no standing "God mode."** Privileged access is time-bound, audited, and requires MFA. Emergency access follows "break-glass" procedures with mandatory post-incident reviews.

### 13. Who internally can access customer data?
Only a **small, role-restricted subset of engineers** for support/debugging, and only with explicit approval. Every access event is logged in our immutable audit trail.

### 14. How do you handle secrets (API keys, tokens)?
Secrets are managed via **AWS Secrets Manager**, rotated regularly, and are never hard-coded or written to logs.

### 15. How do you protect against data exfiltration?
We employ restricted network egress, least-privilege IAM policies, and **AWS GuardDuty** to trigger alerts on anomalous access patterns.

### 16. Have you performed penetration testing?
We conduct regular internal security reviews. We are currently on a roadmap for third-party penetration testing (e.g., Cobalt) and **SOC-2 Type II** compliance as we scale enterprise usage.

---

## D. OPERATIONAL RISK — Integrity and Response

### 17. Can Yirla write back to ad platforms or mutate data?
**No.** Yirla is **read-only**. We do not modify campaigns, bids, or creatives unless explicitly authorized in future enterprise-specific workflows.

### 18. What happens if our credentials are compromised?
Because Yirla credentials are scoped as **read-only**, a compromise would not allow an attacker to mutate your ad accounts. Furthermore, such a compromise would not expose PII or cross-tenant data.

### 19. How do you log and monitor security events?
We maintain a three-tier monitoring stack:
1. **AWS S3 + Object Lock (WORM):** Immutable audit logs.
2. **Datadog:** Real-time alerting and SIEM.
3. **AWS GuardDuty & CloudTrail:** Infrastructure and account-level activity monitoring.

### 20. What’s your incident response posture?
We maintain defined escalation paths, customer notification SLAs, and root-cause analysis (RCA) procedures aligned with enterprise expectations.

---

**For a technical breakdown of our logging architecture, please refer to our [Audit and Logging Architecture](./SECURITY_ARCHITECTURE.md).**
