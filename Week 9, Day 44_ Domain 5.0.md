📘 Week 9, Day 44: Domain 5.0 (GRC) Rapid-Fire Scenario Elimination&nbsp;

&nbsp;

**Day 44 Focus: Domain 5.0 – Governance, Risk, and Compliance (GRC)**

* **Weight:** 20% of the total exam score.

**Key Topics:** Risk calculation, third-party assessment tools, privacy enforcement, and organizational policy implementation.

## **⚡ 1\. Rapid-Fire GRC Scenario Matrix**

Use this matrix to quickly pair GRC scenario requirements with their technical or operational solution:

| If the Scenario Prompt Asks For... | The Correct GRC Solution Is... | Primary Operational Reason |
| :---- | :---- | :---- |
| Assessing technical/operational controls of a SaaS vendor over a 12-month period | **SOC 2 Type II Report** | Evaluates operational effectiveness *over a period of time* (6–12 months) |
| Identifying software component dependencies to prevent supply chain attacks | **SBOM (Software Bill of Materials)** | Itemizes third-party libraries/modules embedded in software |
| Mitigating single-person fraud in sensitive administrative procedures | **Separation of Duties (SoD)** | Requires two or more people to complete a high-risk workflow |
| Discovering hidden unauthorized activity performed by a privileged admin | **Mandatory Vacations** | Forces another employee to perform the duties, exposing unauthorized actions |
| Standardizing contract language for guaranteed service availability (e.g., 99.99%) | **SLA (Service Level Agreement)** | Defines measurable uptime metrics and penalties for non-performance |

&nbsp;

## **2\. Third-Party Risk & Agreement Types**

CompTIA tests whether you can select the correct legal or vendor management agreement based on scenario context:

&nbsp;

| Agree-ment Type | Primary Purpose | Binding Status |
| :---- | :---- | :---- |
| **SLA** | Specifies performance metrics & uptime | Legally binding contract |
| **MSA** | Master terms governing future contracts | Standard overarching terms |
| **SOW** | Defines specific deliverables & timeline | Specific project scope |
| **MOU** | Expresses mutual intent & common goals | Non-binding agreement |
| **NDA** | Protects confidential data from exposure | Legally binding contract |

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

📊 **3\. Risk Tolerance & Privacy Metrics**&nbsp;

Be ready to eliminate choices involving these core GRC standards:

* **Risk Appetite vs. Risk Tolerance:**  
  * **Risk Appetite:** The broad, high-level amount of risk an organization is willing to accept to pursue its goals.  
  * **Risk Tolerance:** The acceptable *deviation* or variance from the defined risk appetite.  
* **Data Anonymization vs. Pseudonymization:**  
  * **Anonymization:** Permanently strips PII so data can never be re-identified (irreversible).  
  * **Pseudonymization:** Replaces private identifiers with pseudonyms (reversible only with a separate decryption key).

## **📘 Week 9, Day 45: Performance-Based Question (PBQ) Simulation Blitz**

**Welcome to Day 45\!** Having wrapped up yesterday's scenario elimination drill covering Domain 5.0 (GRC), we now move into the final day of Week 9, centered entirely on **PBQ Mastery & Simulation Blitz**.

Performance-Based Questions (PBQs) are placed right at the start of the live exam (usually questions 1 to 5). These items evaluate your hands-on proficiency with network diagram remediation, firewall ruleset evaluation, practical configuration, and real-time log parsing under strict time constraints.

## **🛠️ 1\. Firewall ACL Ruleset PBQ Strategy**

A classic Security+ PBQ asks you to configure or fix a stateful packet inspection (SPI) firewall access control list (ACL).

**│ FIREWALL ACL EVALUATION FLOW │**

**├─────────────────────────────────────────────────────────**

**│ • Rule Processing Order:** TOP-DOWN (First Match Wins)   │

│ • **Catch-All Rule at Bottom:** IMPLICIT DENY (Deny Any Any) │&nbsp;

### 

### 

### **PBQ Scenario Execution Steps:**

1. **Check Rule Order:** Firewall rules execute from **Top to Bottom**. If a broad `DENY` rule is placed above an `ALLOW` rule, the traffic will be blocked regardless of lower rules.  
2. **Verify Protocol & Port Mappings:** Ensure secure alternatives are permitted while insecure protocols are blocked:  
   * **Web:** Allow TCP `443` (HTTPS); Deny TCP `80` (HTTP).  
   * **Management:** Allow TCP `22` (SSH); Deny TCP `23` (Telnet).  
   * **Directory Services:** Allow TCP `636` (LDAPS); Deny TCP `389` (LDAP).  
3. **Inspect Directionality:** Confirm Source IP/Port vs. Destination IP/Port (e.g., `Internal Subnet -> DMZ Web Server`).

## **🌐 2\. Network Diagram & Segmentation PBQ Scenario**

In architecture PBQs, you are often asked to place security appliances into a multi-tier network topology:

| Network Zone | Appropriate Security Appliance / Control |
| :---- | :---- |
| Network Edge (WAN) | Boundary Firewall, DDoS Mitigation, Border Router |
| DMZ (Public Access) | Web Application Firewall (WAF), Reverse Proxy, Load Bal. |
| Internal Network | Internal Next-Gen Firewall (NGFW), NAC, EDR |
| Secure Storage Subnet | Host Isolation, Air-Gapping, Database Firewall |

&nbsp;