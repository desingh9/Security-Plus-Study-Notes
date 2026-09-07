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

