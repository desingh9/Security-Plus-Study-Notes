## **📘 Week 7, Day 33: Domain 4.0 (Security Operations) High-Yield Remediation Drill**

Welcome to Day 33\! Yesterday, we conducted our high-yield remediation drill on Domain 3.0 (Security Architecture). Today, we focus on **Domain 4.0: Security Operations**, which carries the heaviest weight on the Security+ exam (**28% of your total score**).

Operations questions test your practical response skills: handling active security incidents, analyzing logs, managing software/host vulnerabilities, and executing forensic procedures without compromising legal evidence.

## **🚨 1\. Incident Response Phases & Immediate Actions Drill**

CompTIA frequently asks, *"What should an analyst do FIRST upon discovering X?"* You must map the scenario directly to the correct NIST SP 800-61 phase:

| INCIDENT RESPONSE OPERATIONAL FLOW |  |  |
| ----- | :---- | :---- |
| **Phase** | **Primary Goal** | **Key Real-World Action** |
| **1\. Preparation** | Strengthen organizational resilience | Revise response playbooks and conduct tabletop exercises |
| **2\. Detection & Analysis** | Verify alerts and assess incident scope | Triage SIEM notifications and confirm indicators of compromise (IOCs) |
| **3\. Containment** | Halt lateral movement | Isolate affected endpoints or quarantine the network VLAN |
| **4\. Eradication** | Remove the core threat | Purge malicious software and patch underlying vulnerabilities |
| **5\. Recovery** | Restore standard operations | Rebuild systems from clean images and validate backup integrity |
| **6\. Lessons Learned** | Drive procedural enhancements | Execute a post-incident review within two weeks |

**The "First Action" Golden Rule:**

* If malware/ransomware is actively spreading: **Containment comes FIRST** (e.g., isolate host from network / disable Wi-Fi). *Do NOT power off or reboot immediately\!*  
* If a credential is compromised: **Disable/Revoke the account or session token immediately**.  
* If legal/forensic investigation is ordered: **Capture volatile RAM before powering down or disconnecting hardware**.

