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

## **🔎 2\. Forensics & Evidence Preservation Mechanics**

Avoid losing easy marks on forensic standards by strictly adhering to these operational protocols:

* **Volatility Hierarchy (Highest to Lowest Volatility):**  
  Processor Registers & Cache ⟶ Main Memory (RAM) ⟶ Network Status & ARP Cache ⟶ Swap/Paging File ⟶ Local Secondary Storage (SSD/NVMe) ⟶ Archival Media & Backups  
* **Maintaining Evidence Integrity:**  
  1. Connect the target physical drive using a **Hardware Write Blocker**.  
  2. Generate an initial cryptographic hash (such as SHA-256) of the primary drive.  
  3. Produce a sector-by-sector forensic duplicate (**Bit-Stream Image**).  
  4. Calculate the cryptographic hash of the image and confirm that Hash original \== Hashcopy.  
  5. Conduct all investigation and analysis exclusively on the **forensic clone**, leaving the source media untouched.  
* **Chain of Custody Log:** A strict chronological record documenting the details of evidence handling: *Who* collected or transferred it, *What* item was seized, *When* (exact date/timestamp) it occurred, *Where* it was kept (e.g., tamper-evident evidence bag or secure safe), and *Why* control was relinquished or moved.

## **📊 3\. Centralized Telemetry & Log Analysis Drills**

Be ready to recognize these operational tools and formats instantly:

* **SIEM vs. SOAR:**  
  * **SIEM:** Aggregates, parses, normalizes, and correlates logs to generate **alerts** (Passive detection).  
  * **SOAR:** Executes automated **playbooks** and **runbooks** to take active response actions at machine speed (Active response).  
* **Network Flow Data (NetFlow / IPFIX):** Captures metadata about network traffic (Source IP, Destination IP, Ports, Protocols, Byte Volume) without capturing raw packet contents.  
* **Syslog Standard Protocols:**  
  * **UDP 514:** Traditional, unencrypted cleartext logging.  
  * **TCP 6514:** Encrypted Syslog over TLS (Secure standard).

## **🧠 Quick Knowledge Check**

> **Scenario:** A SOC analyst receives a high-priority alert that an endpoint workstation is beaconing out to a known malicious Command and Control (C2) IP address over port 443\. What is the analyst's immediate NEXT step?

* *Answer:* **Isolate the infected workstation from the network** (Containment). Isolating the endpoint stops C2 commands and prevents lateral movement across the internal subnet while preserving system RAM for analysis.

## **📝 Today's Action Items**

1. **Review Drill:** Recite the 6 steps of the NIST Incident Response lifecycle in exact chronological order without looking at notes.  
2. **Flashcards:** Create cards for *Order of Volatility, Bit-Stream Image vs File Copy, Hardware Write Blocker, Chain of Custody, SOAR Runbooks,* and *Syslog Ports (514 vs 6514\)*.  
3. **Exam Mindset:** On evidence preservation questions, if an option suggests analyzing the *original target hard drive directly*, it is **ALWAYS WRONG**. Analysis is performed only on verified forensic copies.

Tomorrow, for **Week 7, Day 34**, we will execute our **Domain 5.0 (GRC) High-Yield Remediation Drill**\!

