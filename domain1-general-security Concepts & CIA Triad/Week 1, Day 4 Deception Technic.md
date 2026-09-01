📘 Week 1, Day 4: Deception Technologies \& Change Management

we covered Zero Trust Architecture and physical controls. Today, we are finishing up Domain 1 concepts by diving into Deception and Disruption Technologies (Domain 1.2) and the security impacts of Change Management (Domain 1.3).

CompTIA tests these concepts heavily because unauthorized changes and unmonitored systems are primary causes of security incidents.

🎯 1. Deception \& Disruption Technologies
Deception technology lures threat actors away from actual enterprise assets into monitored, decoy environments. This allows defenders to observe attacker TTPs (Tactics, Techniques, and Procedures) without risk to real production data.

* Honeypot: A single decoy system (server, application, or workstation) intentionally configured with simulated vulnerabilities to attract attackers.
* Honeynet: A network segment populated with multiple honeypots that simulates an entire corporate enterprise infrastructure.
* Honeyfile: An enticing fake file (e.g., passwords.xlsx or Q4\_Executive\_Salaries.pdf) embedded with tracking triggers or fake credentials. Opening or accessing the file immediately generates a high-priority security alert.
* Honeytoken: A piece of fake data (such as a dummy API key, AWS access key, or database record) placed in production or decoy systems. Any attempt to use this token immediately flags unauthorized activity.



🔄 2. Change Management Processes \& Security Impact



Change management ensures that modifications to systems, networks, or applications do not introduce unmanaged risk, unintended outages, or security gaps.

* Core Components of a Secure Change Process:
* Business Processes \& Approvals: Formal requests must undergo risk/impact analysis and be approved (often by a Change Advisory Board or CAB) before execution.
* Documentation \& Version Control: All changes, architectural updates, network diagrams, and Standard Operating Procedures (SOPs) must be updated. Version control ensures configurations can be tracked over time.
* Test Results \& Sandbox Environments: Changes must be verified in non-production environment testing before deploying to production.
* 



