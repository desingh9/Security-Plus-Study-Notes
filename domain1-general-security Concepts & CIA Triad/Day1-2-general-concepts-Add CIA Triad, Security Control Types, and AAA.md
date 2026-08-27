Domain 1.1. You cannot secure an environment without understanding the fundamental models used to evaluate risk and protection.







1\. The CIA Triad



The absolute bedrock of information security. Every control you implement aims to protect one or more of these three pillars:







Confidentiality: Ensuring that data is only viewable by authorized users.







Key Mitigations: Encryption (AES), Access Controls (MFA, RBAC), Obfuscation.







Integrity: Ensuring that data has not been altered, tampered with, or destroyed by unauthorized entities.







Key Mitigations: Hashing (SHA-256), Digital Signatures, Configuration Management.







Availability: Ensuring that systems, networks, and data are accessible to authorized users when needed.







Key Mitigations: Redundancy (RAID, load balancers), Backups, DoS/DDoS mitigation.





2\. The Non-Repudiation Concept



Definition: Ensuring that a party to a transaction or communication cannot deny the authenticity of their signature on a document or the sending of a message that they originated.







How it's achieved: Digital Signatures (which use asymmetric cryptography) and robust logging/audit trails.







3\. Authentication vs. Authorization vs. Accounting (AAA)



Authentication: Proving you are who you say you are (e.g., entering a password + biometric scan).







Authorization: Determining what permissions and resources you have access to after you are authenticated (e.g., Read/Write access to a specific folder).







Accounting: Tracking and logging what you did while logged in (e.g., audit logs showing you modified a specific file at 10:14 AM).







🧠 Quick Knowledge Check



Scenario: An attacker intercepts a company email, alters the financial figures inside the document, and forwards it to the accounting department. Which pillar of the CIA triad was breached?



Answer: Integrity. An unauthorized party altered the data in transit.







📝 Day 1 Action Items







Read/Watch: Spend 20 minutes reviewing the CIA Triad and AAA concepts in your primary study material (e.g., Professor Messer, Sybex, or Udemy).







Flashcards: Create cards for Confidentiality, Integrity, Availability, Non-repudiation, and AAA.







Mindset: Remember, CompTIA loves scenarios. Don't just memorize the definitions; think about how a company loses integrity or ensures non-repudiation.







In Next step day 3, we will dive into Security Control Types (Technical, Operational, Managerial) and how they apply to these core pillars!







📘 Week 1, Day 2: Security Control Categories and Types



Earlier, we established the foundational goals of cybersecurity: the CIA Triad (Confidentiality, Integrity, and Availability) and the AAA framework. Today, we focus on Domain 1.1's implementation mechanics: Security Controls.



CompTIA expects you to categorize these controls in two distinct ways: by Category (how they are implemented) and by Type (what function they perform).



* 🏛️ 1. Control Categories (The "How")

Security controls are divided into three primary categories based on how they are managed and executed:



* Technical (Logical) Controls: Security controls executed by hardware, software, or firmware.



Examples: Firewalls, Encryption, Access Control Lists (ACLs), Antivirus software, IDS/IPS.



* Managerial (Administrative) Controls: Controls that focus on administrative risk assessment, management, and policy. They dictate the "rules" of the organization.



Examples: Security policies, risk assessments, employee training, background checks, separation of duties policies.



* Operational (Physical/Procedural) Controls: Controls implemented by people (rather than systems) to secure daily operations, or physical mechanisms used to protect assets.



Examples: Security guards, awareness training programs, incident response procedures, fire suppression systems, visitor logs.





* **2. Control Types (The "What")**

**Controls are also classified by their functional goal during a security event:**

* **Preventive: Designed to stop an incident from occurring in the first place.**

&#x20;   **\* Examples: Security awareness training, firewalls, guard dogs, biometric locks.**

* **Detective: Designed to identify and flag an active or past security incident. They do not stop the attack, they only sound the alarm.**

&#x20; **\* Examples: Security cameras (CCTV), system logs, Intrusion Detection Systems (IDS), motion sensors.**

* **Corrective: Designed to mitigate damage and restore systems back to a normal state after an incident occurs.
\* Examples: Data backups, system imaging, antivirus software removing a virus, patching a vulnerability.**
* Deterrent: Designed to discourage a potential attacker psychologically from attempting a breach.
\* Examples: "Beware of Dog" signs, visible security cameras, warning banners on login screens.

* Physical: Tangible, real-world measures designed to protect personnel, hardware, and facilities.

&#x20;  \* Examples: Fences, bollards, mantraps, badge readers.

* Compensating: Alternative controls deployed when a primary control is too expensive, difficult, or technically impossible to implement.

&#x20;  \* Examples: If a legacy system cannot support encryption (primary technical control), a compensating control might be isolating that system on a completely locked-down network segment.






📊 Quick Reference Matrix

CompTIA frequently mixes these together. A single item can be both a Technical category and a Preventive type:



Security Measure	Category	Type

Firewall Rule	Technical	Preventive

Security Guard	Operational	Preventive / Deterrent

Reviewing Audit Logs	Technical / Operational	Detective

Restoring from Backup	Technical	Corrective

A Warning Sign on a Fence	Operational	Deterrent



🧠 Quick Knowledge Check

Scenario: A company installs a locked cage inside their data center to hold high-value cryptographic hardware. Only authorized administrators can badge into the cage. What control category and functional type best describe the cage?



Answer: Category: Operational (Physical) | Type: Preventive. It physically bars unauthorized entry to prevent theft or tampering.





