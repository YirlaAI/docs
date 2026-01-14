# Yirla Shared Responsibility Model

## 🤝 Overview
Security at Yirla is a partnership. While Yirla ensures the security **of** the platform and its underlying infrastructure, our customers are responsible for security **within** their specific configuration and the management of their ad platform credentials. 

This model follows the industry standard for SaaS (Software as a Service) to ensure there are no gaps in the security perimeter.



---

## 🏗️ Responsibility Matrix

| Category | Yirla Responsibility | Customer Responsibility |
| :--- | :--- | :--- |
| **Physical Security** | Physical security of AWS Data Centers. | Security of customer office and hardware. |
| **Infrastructure** | Hardening of AWS EC2, RDS, and S3. | N/A |
| **Network Security** | Encryption in transit (TLS), Firewalls. | Managing internal network access to Yirla. |
| **Data Protection** | Encryption at rest (AES-256), Backup integrity. | Ensuring PII is not sent to Yirla. |
| **Identity & Access** | MFA for Yirla employees, RBAC logic. | MFA for Customer users, User Offboarding. |
| **Application Logic** | Patching vulnerabilities, API Security. | Responsible use of Yirla Insights. |
| **Ad Platform Keys** | Secure storage in AWS Secrets Manager. | Revoking API tokens if no longer in use. |

---

## 🟢 1. What Yirla Manages

### Infrastructure & Physical Security
Yirla is hosted on Amazon Web Services (AWS). We inherit the physical and environmental security controls of AWS, including biometric access, 24/7 surveillance, and climate control. 

### Platform Security
We are responsible for the "Security of the Cloud":
* **Patch Management:** Keeping the FastAPI application and OS-level dependencies up to date.
* **Vulnerability Scanning:** Continuous monitoring of our codebase and container images for known exploits.
* **Logging & Monitoring:** Maintaining the immutable audit trail (WORM) and SIEM alerts via Datadog.

---

## 🔵 2. What the Customer Manages

### User Access Management
The customer is responsible for who has access to their Yirla tenant. 
* **Strong Passwords:** Enforcing strong password policies (if not using SSO).
* **MFA:** Ensuring all users assigned to the Yirla tenant have Multi-Factor Authentication enabled.
* **Offboarding:** Immediately deactivating users when they leave the organization or change roles.

### Data Input & Compliance
While Yirla is designed to be PII-free, the customer is responsible for:
* **Input Hygiene:** Ensuring that custom fields in ad platforms (like LinkedIn) do not contain sensitive PII before Yirla ingests them.
* **Legal Compliance:** Ensuring their use of Yirla’s analytics complies with their own internal privacy policies and local regulations (GDPR, CCPA).

### Credential Governance
Customers provide Yirla with **Read-Only** access to ad platforms. 
* **Scope:** Customers must ensure they only provide the minimum required scopes for analytics.
* **Revocation:** If a customer terminates their service, they should revoke the API token/integration from their ad platform's side as an additional layer of security.

---

## 🛠️ Summary of Controls

| Control | Responsible Party |
| :--- | :--- |
| **Data Encryption at Rest** | Yirla |
| **Encryption in Transit** | Yirla |
| **Endpoint Security (Laptop/Mobile)** | Customer |
| **MFA Configuration** | Customer |
| **Audit Log Integrity** | Yirla |

***
