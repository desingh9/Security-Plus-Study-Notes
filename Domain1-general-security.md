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



Day-2, we will dive into Security Control Types (Technical, Operational, Managerial) and how they apply to these core pillars!





Read/Watch: Spend 20 minutes reviewing the CIA Triad and AAA concepts in your primary study material (e.g., Professor Messer, Sybex, or Udemy).



Flashcards: Create cards for Confidentiality, Integrity, Availability, Non-repudiation, and AAA.



Mindset: Remember, CompTIA loves scenarios. Don't just memorize the definitions; think about how a company loses integrity or ensures non-repudiation.



In Next step day 3, we will dive into Security Control Types (Technical, Operational, Managerial) and how they apply to these core pillars!







