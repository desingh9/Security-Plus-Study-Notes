Week 1, Day 4: Deception Technologies \& Change Management



Earlier ,we covered **Zero Trust Architecture and physical controls**. Today, we are finishing up Domain 1 concepts by diving into Deception and Disruption Technologies (Domain 1.2) and the security impacts of Change Management (Domain 1.3).



CompTIA tests these concepts heavily because unauthorized changes and unmonitored systems are primary causes of security incidents.



🎯 1. Deception \& Disruption Technologies



By redirecting threat actors from production assets into decoy environments, deception technology enables security teams to analyze attacker TTPs (Tactics, Techniques, and Procedures) safely without exposing sensitive data.

* Honeypot: An individual decoy asset (such as a workstation, server, or application) purposefully set up with simulated weaknesses to draw in attackers.
* Honeynet: An entire decoy network segment composed of several honeypots to mimic an authentic enterprise environment.
* Honeyfile: A decoy document (e.g., passwords.xlsx or Q4\_Executive\_Salaries.pdf) containing embedded monitoring mechanisms or fake credentials that trigger immediate high-priority alerts when accessed.
* Honeytoken: A dummy data artifact (like a fake AWS key, API credential, or database entry) deployed across live or decoy systems to detect unauthorized usage right away.



🔄 2. Change Management Processes \& Security Impact

A robust change management framework guarantees that modifications to network configurations, infrastructure, or software do not introduce security vulnerabilities or cause unplanned service disruptions.

* Key Pillars of a Secure Change Process:

&#x20;\* Business Processes \& Approvals: Proposed changes must undergo formal evaluation and obtain authorization—typically from a Change Advisory Board (CAB)—prior to implementation.

* Test Results \& Sandbox Environments: Implementations must undergo thorough validation in isolated, non-production environments before deployment.
* Documentation \& Version Control: Maintaining updated architecture maps, SOPs, and system configurations ensures changes are fully traceable over time.
* Backout Plan: A required, step-by-step procedure to revert systems to a stable operational baseline should the change encounter severe issues.
* Maintenance Windows \& Downtime: Planning deployments during designated low-traffic hours helps mitigate business disruption and safely manage service restarts.



⚠️ Security Risks of Poor Change Management

When unauthorized or unvetted changes occur, organizations face several primary risks:

1. Misconfiguration: Accidentally opening ports, disabling firewalls, or removing access controls.

2\. Downtime \& Outages: Unintended dependencies failing when an application or service restarts unexpectedly.

3\. Legacy Dependencies: Upgrading a single library or OS version without testing can break critical legacy business applications.







