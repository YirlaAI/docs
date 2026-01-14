# 🚀 Security-Focused Onboarding Checklist

This checklist is designed to help Enterprise Admins configure their Yirla tenant according to industry best practices. Following these steps ensures your deployment is **SOC 2 compliant** from Day 0 and maintains the integrity of your demand gen analytics.

---

## 🏗️ Phase 1: Identity & Access Management (IAM)
*Goal: Ensure only authorized users can access sensitive performance data.*

- [ ] **Enforce MFA:** Confirm that every user invited to the Yirla tenant has Multi-Factor Authentication (MFA) enabled.
- [ ] **Role-Based Access (RBAC):** Review user types. Assign **Admin** only to those managing integrations; use **Viewer** for team members who only need to consume reports.
- [ ] **SSO Integration (Enterprise):** If your plan includes SAML/SSO, link Yirla to your Identity Provider (Okta, Azure AD, or Google Workspace).
- [ ] **User Audit Schedule:** Set a recurring calendar reminder to review and "prune" user access every 90 days.

---

## 🔑 Phase 2: Ad Platform Integration
*Goal: Securely bridge Yirla with your marketing data sources.*

- [ ] **Verify Read-Only Scopes:** When connecting LinkedIn or other platforms, ensure the permissions requested are "Read-Only." Yirla never requires "Manager" or "Write" access to your ads.
- [ ] **Dedicated Service Account:** Use a non-human "Service Account" to connect APIs. This prevents the integration from breaking when an individual employee leaves or changes their password.
- [ ] **Token Rotation Review:** Familiarize yourself with how to revoke and re-authorize tokens within your ad platform’s "Authorized Apps" settings.

---

## 📊 Phase 3: Data Hygiene & Privacy
*Goal: Prevent PII (Personally Identifiable Information) from entering the analytics stream.*

- [ ] **Sanitize Campaign Naming:** Review your naming conventions. Ensure no emails, phone numbers, or customer names are included in campaign or creative titles.
- [ ] **UTM Parameter Audit:** Verify your UTM strings do not pass PII in the URL (e.g., avoid `?email=user@company.com`).
- [ ] **Verify PII-Free Logic:** Confirm that no custom "Hidden Fields" in your ad platform contain sensitive lead data that Yirla might ingest.



---

## 🛡️ Phase 4: Monitoring & Compliance
*Goal: Maintain ongoing visibility and audit readiness.*

- [ ] **Designate Security Contact:** Provide Yirla with a primary security email for "Incident Response" and "Security Advisory" notifications.
- [ ] **Verify Audit Logs:** Log into Yirla and navigate to the **Activity Log**. Confirm that your own login event was recorded correctly.
- [ ] **Incident Playbook:** Brief your security team on Yirla's [Shared Responsibility Model](./SHARED_RESPONSIBILITY.md).

---

## ✅ Checklist Summary

| Task Category | Priority | Impact |
| :--- | :--- | :--- |
| **MFA/SSO Setup** | 🔥 Critical | Access Security |
| **Read-Only Scopes** | 🔥 Critical | Data Integrity |
| **User Role Review** | 🟡 High | Internal Governance |
| **PII/Naming Audit** | 🟡 High | Regulatory Compliance |

***

### 🆘 Need Technical Support?
If your security team requires a custom **Vulnerability Disclosure Policy (VDP)** or a signed **Data Processing Agreement (DPA)**, please reach out to your Account Manager or email `security@yirla.com`.
