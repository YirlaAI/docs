# Trust & Security at Yirla

## 🛡️ Our Commitment
At **Yirla**, trust is foundational. Customers rely on Yirla to analyze sensitive advertising and performance data, and we take that responsibility seriously. Our approach to security is pragmatic, preventative, and continuously improving—designed to protect customer data while enabling fast, reliable decision-making.

---

## 🔒 How We Protect Customer Data

### **Secure Infrastructure**
Yirla is hosted on industry-standard cloud infrastructure (AWS) with built-in redundancy, monitoring, and physical security controls. We leverage mature cloud services rather than custom infrastructure wherever possible to reduce surface-area risk.

### **Encryption**
* **In Transit:** All data is encrypted using **TLS 1.2+**.
* **At Rest:** Data is encrypted using industry-standard **AES-256** encryption mechanisms.

### **Access Controls**
* **Least Privilege:** Role-based access control (RBAC) following strict least-privilege principles.
* **Restricted Admin Access:** Administrative access is restricted to a minimal number of authorized personnel.
* **Access Reviews:** Permissions are reviewed periodically and removed promptly upon role changes or departure.

### **Monitoring & Logging**
We maintain comprehensive logging and monitoring across our systems to detect availability issues, unusual activity, and potential security events.

---

## ⚙️ Operational Security Practices

### **Secure Development Lifecycle (SDLC)**
Security is integrated throughout the development lifecycle, including:
* **Code Reviews:** Mandatory peer reviews for all code changes.
* **Environment Separation:** Strict logical separation between production and non-production environments.
* **Controlled Deployments:** Auditable and versioned deployment processes via GitHub.

### **Third-Party Dependencies**
Yirla integrates with third-party platforms (e.g., LinkedIn, Google, Meta APIs) to deliver insights. We:
* Select vendors with strong, documented security postures.
* Limit API access to the absolute minimum data required to operate the service.

### **Incident Preparedness**
Yirla maintains an internal incident response process designed to:
1.  **Detect** security and availability incidents quickly.
2.  **Contain** and mitigate impact.
3.  **Communicate** transparently with affected customers.

> *For more details, please refer to our [Incident Response Policy](INCIDENT_RESPONSE.md).*

---

## ⚖️ Compliance & Privacy Alignment
Yirla operates in alignment with widely accepted security and privacy principles, including **SOC 2 Trust Service Criteria**. Formal certifications are pursued as our customer base and regulatory needs evolve.

Our handling of personal data is governed by our **Privacy Policy** and **Data Retention Policy**.

---

## 📧 Questions
If you have questions about our security practices or need additional documentation for your review, please contact:  
**security@yirla.com**
