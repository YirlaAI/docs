# Service Level Agreement (SLA)

**Effective Date:** Jan 11, 2026  
**Service Provider:** Spark Foundry, dba Yirla

---

## 1. Service Overview
Yirla provides a cloud-based advertising intelligence and analytics platform that aggregates, processes, and presents advertising data for decision-making purposes. This SLA defines Yirla’s commitments regarding **availability**, **support response times**, and **service credits**.

---

## 2. Service Availability
Yirla commits to a **Monthly Uptime Percentage of 99.5%**.

### **Availability Formula**
The monthly uptime percentage is calculated as follows:
$$\text{Availability \%} = \frac{\text{Total Minutes in Month} - \text{Downtime Minutes}}{\text{Total Minutes in Month}} \times 100$$

### **Exclusions**
Uptime commitments do not apply to downtime caused by:
* **Scheduled Maintenance:** Communicated at least 48 hours in advance.
* **Third-Party Failures:** Outages of external ad platforms (e.g., LinkedIn, Google Ads APIs).
* **Force Majeure:** Events outside Yirla’s reasonable control (e.g., natural disasters, war).
* **Customer Actions:** Misconfiguration or unauthorized use of the platform.

---

## 3. Support Services & Response Targets
Support is available via **support@yirla.com** during standard business hours (**Monday–Friday, 9:00 AM – 5:00 PM PT**).

| Severity | Description | Initial Response Target |
| :--- | :--- | :--- |
| **Critical (P1)** | Platform unavailable or major functionality unusable. | ≤ 4 Business Hours |
| **High (P2)** | Significant degradation with no viable workaround. | ≤ 1 Business Day |
| **Medium (P3)** | Partial impact or a workaround is available. | ≤ 2 Business Days |
| **Low (P4)** | General questions or cosmetic issues. | ≤ 3 Business Days |

> **Note:** Response time refers to the acknowledgment and start of investigation, not necessarily the final resolution.

---

## 4. Service Credits (Enterprise Only)
If Yirla fails to meet the 99.5% uptime commitment, Enterprise customers may be eligible for Service Credits applied to future invoices.

| Monthly Uptime | Service Credit (% of Monthly Fee) |
| :--- | :--- |
| **99.0% – 99.49%** | 5% |
| **98.0% – 98.99%** | 10% |
| **< 98.0%** | 15% |

**Credit Request Process:** Credits must be requested within **30 days** of the month in which the downtime occurred.

---

## 5. Data Dependencies
Yirla relies on third-party APIs. We do not guarantee:
1.  The **timeliness** of data provided by external ad platforms.
2.  The **completeness** of data if external sources are unavailable.
3.  The **accuracy** of third-party spend signals.

---

## 6. Contact
For SLA-related inquiries or to report an uptime issue, contact:  
**support@yirla.com**
