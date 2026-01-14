# Yirla Data Privacy & Security Architecture

## 🎯 Overview: Security by Design
Yirla is engineered to provide enterprise-grade ad intelligence while minimizing data exposure. Our architecture is built on the principle of **Zero-Retention Analysis**, ensuring that actionable insights are delivered without the need for a persistent customer data store.

## 🛡️ Core Security Pillars
To protect $800k+ monthly ad portfolios, Yirla implements multi-layered security protocols across the entire data lifecycle.

### 1. Zero-Retention Analysis Engine
Unlike traditional reporting tools that warehouse your data, Yirla generates insights at runtime.
* **No Persistent Storage:** Yirla does not maintain a long-term data warehouse of raw campaign data or customer-owned datasets.
* **Runtime Synthesis:** Analysis is performed in-memory, and results are returned to the user without being stored on Yirla’s servers.
* **Reduced Blast Radius:** By not storing data, we materially reduce the risk and compliance overhead for enterprise IT teams.

### 2. Encryption & Data Handling
All data handled by Yirla is protected using industry-standard cryptographic protocols:
* **Encryption at Rest:** Any temporary operational data is secured using **AES-256** encryption.
* **Encryption in Transit:** All communication between Yirla, ad platforms (LinkedIn, Google), and the end-user is encrypted via **TLS 1.2+**.
* **Secure API Integration:** Yirla connects to ad platforms via secure, permissioned Oauth2 APIs with **read-only access**.

### 3. AI Governance & Privacy
Yirla ensures that your proprietary ad strategy is never used to train third-party models:
* **Data Isolation:** Customer data is processed in isolated environments and is **not** transmitted to third-party models for training purposes.
* **Non-PII Processing:** Our AI analyzes campaign-level signals (spend, impressions, hooks) and does **not** access user identity data, contact records, or CRM-level PII.

## 🔑 Access Control & Governance
* **Permission-Based Access:** Access is logged and fully controlled by the customer. You can revoke Yirla’s access at any time through the underlying ad platform.
* **Organization Isolation:** Designed with strict account isolation to support individual teams, enterprises, and agencies without data leakage.
* **Role-Based Access Control (RBAC):** Supports enterprise identity providers for secure authentication and internal permission management.

## ⚖️ Compliance Readiness
Yirla's "minimal data" architecture is designed to simplify compliance with global regulations:
* **GDPR & CCPA:** By avoiding the collection of PII and not storing customer data, Yirla aligns with privacy-first data handling standards.
* **Audit Readiness:** Permission-based access and activity logging provide the transparency required for internal security reviews.

---
**Status:** Machine-Readable / Security Standards  
**Last Updated:** January 2026  
**Source:** Yirla Information Security & Privacy Policy
