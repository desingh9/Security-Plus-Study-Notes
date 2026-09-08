## **📘 Week 5, Day 21: Centralized Logging, SIEM & SOAR Architecture**

Welcome to **Week 5**\! Over the past four weeks, we covered fundamental security concepts (Domain 1.0), threats and attack vectors (Domain 2.0), and core security architecture (Domain 3.0). Today, we dive deeper into **Domain 4.0: Security Operations** (28% of the exam—the largest domain) with **Centralized Logging, SIEM, and SOAR** (Domain 4.2).

Detecting intrusions, analyzing breaches, and containing incidents require continuous visibility into system and network activity.

## **📜 1\. Log Sources & Network Telemetry**

Security tools rely on accurate log collection across the entire enterprise stack:

* **Syslog:** A standardized protocol for message logging across routers, switches, firewalls, and Unix/Linux systems.  
  * *Ports:* UDP port 514 (unencrypted cleartext) or **TCP port 6514** (Secure Syslog encrypted via TLS).  
* **OS & Application Event Logs:** Records operating system events (e.g., Windows Event Viewer ID 4624 for successful logins, 4625 for failed logins) and application actions.  
* **Flow Logs (NetFlow / IPFIX):** Captures metadata about IP traffic traversing network interfaces (source IP, destination IP, source port, destination port, protocol, packet volume) without capturing full packet payloads.  
* **NTP (Network Time Protocol):** **Crucial for log correlation\!** Ensures all network devices, servers, and security appliances have precisely synchronized system clocks (uses UDP port 123). Without accurate NTP, establishing a chronological timeline during forensic investigations is nearly impossible.

## **📊 2\. Security Information and Event Management (SIEM)**

A **SIEM** aggregates, normalizes, and correlates log data from across the enterprise into a centralized dashboard to identify threats in real time.

\[ Routers / Switches \]   ┐ \[ Firewalls / WAFs \]      ├─► \[ Log Collectors / Forwarders \] ─► \[ SIEM Correlation Engine \] \[ Servers / Endpoints \]  ┘     (Normalization & Parsing)           (Alert Generation)

* **Log Aggregation & Ingestion:** Pulling log feeds from disparate systems into a central data repository.  
* **Normalization & Parsing:** Formatting unstructured logs from different vendors into a unified schema so they can be parsed consistently.  
* **Correlation Engine:** Uses rule-based logic or machine learning algorithms to match pattern indicators across multiple distinct log sources (e.g., triggering an alert if 50 failed SSH logins occur on a server followed immediately by an admin account creation).

## **🤖 3\. Security Orchestration, Automation, and Response (SOAR)**

Whereas a SIEM flags potential threats for analysts, a **SOAR** platform automates containment and remediation actions to address incidents at machine speed.

* **Core Benefit:** Lowers **MTTR (Mean Time to Respond)** and helps alleviate alert fatigue among Security Operations Center (SOC) personnel.  
* **Playbooks:** Formally documented procedures outlining step-by-step logic for addressing particular incident scenarios (such as handling phishing attacks).  
* **Runbooks:** Automated workflows run directly within the SOAR system to execute playbook tasks automatically—such as disconnecting compromised hosts, revoking active session tokens, or blocking malicious IP addresses at the firewall.

## 

## 

## **📊 SIEM vs. SOAR Comparison**

| Feature | SIEM | SOAR |
| :---- | :---- | :---- |
| **Primary Goal** | Centralized log ingestion, correlation, & alerting | Threat response automation & orchestration |
| **Action Type** | Passive (detects and notifies) | Active (executes response actions) |
| **Key Enabler** | Correlation rules & NTP log timestamps | Automated Playbooks & Runbooks |
| **Analyst Impact** | Provides visibility & alerts | Reduces manual workload & speeds containment |

## **🧠 Quick Knowledge Check**

> **Scenario:** During an incident investigation, a security analyst finds that log entries from a firewall indicate an attack occurred at 14:00 UTC, while the target server's logs show the attack occurred at 14:15 UTC. What fundamental protocol was misconfigured or missing on these appliances?

* *Answer:* **NTP (Network Time Protocol)**. Without time synchronization across devices, correlation engines and analysts cannot build an accurate sequence of events.

## **📝 Today's Action Items**

1. **Read/Watch:** Review SIEM, SOAR, and NTP functionality in Domain 4.2. Focus on how SOAR runbooks automate security tasks.  
2. **Flashcards:** Create cards for *Syslog ports (UDP 514 vs TCP 6514), NTP (UDP 123), SIEM Correlation Engine, SOAR, Playbooks vs. Runbooks,* and *NetFlow*.  
3. **Exam Mindset:** If a scenario asks how to *automatically isolate a compromised workstation as soon as an alert fires*, select **SOAR / Runbook execution**.

Tomorrow, we will explore **Incident Response Frameworks & The IR Lifecycle** 

(Preparation, Detection, Containment, Eradication, Recovery, and Lessons Learned)\!

## 

## 

## **📘 Week 5, Day 22: Incident Response Frameworks & The IR Lifecycle**

Yesterday, we set up centralized log collection, SIEM correlation, and SOAR automation. Today, we put those detection mechanisms to work by diving into **Incident Response Frameworks & The IR Lifecycle** (Domain 4.3).

When a security breach occurs, chaos is the enemy. A structured, standardized Incident Response (IR) plan ensures that teams act systematically to minimize damage, preserve evidence, and restore normal operations quickly.

## **🔄 1\. The Incident Response Lifecycle (NIST SP 800-61)**

CompTIA tests heavily on the sequential stages of the IR lifecycle according to standards like NIST SP 800-61 and ISO/IEC 27035\. You must know what activities happen in each specific phase:

┌──────────────────────────────────────────────────────┐

│ 1\. Preparation │  
└────────────────────────┬─────────────────────────────┘  
                           │  
                          ▼  
┌──────────────────────────────────────────────────────┐  
│ 2\. Detection & Analysis │  
└────────────────────────┬─────────────────────────────┘  
                           │  
                           ▼  
┌──────────────────────────────────────────────────────┐  
│ 3\. Containment, Eradication, & Recovery │ ◄──┐  
└──────────────────────────┬───────────────────────────┘ │(Iterative Loop)  
                            │ ───┘  
                           ▼  
┌──────────────────────────────────────────────────────┐  
│ 4\. Post-Incident Activity (Lessons Learned) │

└──────────────────────────────────────────────────────┘

### 

### **Phase 1: Preparation**

* **Goal:** Establish capabilities, policies, tools, and training *before* an incident occurs.  
* **Key Actions:** Developing IR plans, building jump kits, configuring backup systems, establishing communication call trees, and running table-top exercises.

### **Phase 2: Detection & Analysis**

* **Goal:** Identify potential security incidents, determine their scope, and confirm validity.  
* **Key Actions:** Analyzing SIEM alerts, reviewing host logs, triaging alerts, and determining whether an anomaly is a false positive or an actual breach.

### **Phase 3: Containment, Eradication, & Recovery**

* **Containment:** Limit the damage and prevent the threat from spreading across the network.  
  * *Short-term:* Isolating infected endpoints from the network, disabling compromised user accounts.  
  * *Long-term:* Applying temporary firewall blocks or network segmentation changes while systems stay running.  
* **Eradication:** Removing the root cause of the incident from the environment.  
  * *Actions:* Deleting malware files, terminating malicious processes, removing rogue user accounts, and patching the exploited vulnerability.  
* **Recovery:** Safely restoring impacted systems back to normal operational status.  
  * *Actions:* Rebuilding servers from clean golden images, restoring data from verified uninfected backups, validating system integrity, and monitoring traffic closely as services come back online.

### **Phase 4: Post-Incident Activity (Lessons Learned)**

* **Goal:** Analyze the incident response process to improve future defenses and plans.  
* **Key Actions:** Holding a post-mortem meeting within 1–2 weeks, documenting the incident timeline, updating IR playbooks, and modifying security controls to prevent recurrence.

## 

## 

## 

## 

## **🛠️ 2\. Containment Strategies: Isolation vs. Shutdown**

CompTIA scenario questions often test when to choose specific containment techniques:

| Strategy | Execution | Best Used When... |
| :---- | :---- | :---- |
| **Network Isolation** | Disconnecting host network cables or using EDR to quarantine network adapters | Preserving system state/RAM for forensic analysis while preventing lateral movement. |
| **System Shutdown** | Powering down the machine completely | **Rarely recommended** unless critical hardware damage is occurring (wipes volatile RAM evidence). |
| **Segmentation** | Placing compromised subnets into an isolated quarantine VLAN | Containing multi-system or domain-wide infections (e.g., active ransomware propagation). |

## **🧠 Quick Knowledge Check**

> **Scenario:** After removing malware binaries and patching a vulnerable web application, an incident response team restores system databases from clean backups and verifies that web services are operating normally before opening traffic to the public. Which phase of the incident response lifecycle is being performed?

* *Answer:* **Recovery**. The team is restoring systems to full production status after the threat has been eradicated.

## **📝 Today's Action Items**

1. **Study Focus:** Examine the NIST SP 800-61 Incident Response phases within Domain 4.3, placing specific emphasis on clearly differentiating Eradication from Recovery.  
2. **Flashcards:** Build review cards covering *Preparation, Detection & Analysis, Containment vs. Eradication vs. Recovery,* and *Lessons Learned / Post-Mortem*.  
3. **Exam Strategy:** When a scenario asks for the immediate *initial* step following a confirmed ransomware outbreak on an endpoint, prioritize **Isolating / Containing the workstation from the network** over powering down the machine or immediately purging files.

In the upcoming module, we will delve into **Digital Forensics & Evidence Preservation**—focusing on the Chain of Custody, Order of Volatility, and Disk/RAM Imaging\!

Tomorrow, we will explore **Digital Forensics & Evidence Preservation** (Chain of Custody, Order of Volatility, and Disk/RAM Imaging)\!

