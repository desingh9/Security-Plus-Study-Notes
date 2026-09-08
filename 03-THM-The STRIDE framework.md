  
The STRIDE framework provides a structured methodology for threat modeling in information security, designed to assist organizations in detecting and categorizing system vulnerabilities throughout software development. The acronym represents six key security threat categories:

* **Spoofing**: Impersonating an authorized user or system to obtain illicit access.  
* **Tampering**: Modifying or manipulating code or data without authorization.  
* **Repudiation**: Refusing responsibility for an action due to missing or inadequate audit logging.  
* **Information Disclosure**: Unlawfully exposing confidential or sensitive data to unauthorized entities.  
* **Denial of Service**: Impairing service availability to block legitimate access.  
* **Elevation of Privilege**: Escalating permissions illegally to execute unauthorized operations.

By leveraging this model, security teams can methodically uncover, evaluate, and mitigate risks during system development.

| Threat Category | Description | Security Principle Violated |
| :---- | :---- | :---- |
| Spoofing | Impersonating an authorized user or system component to gain illicit entry. | Authentication |
| Tampering | Unauthorized altering or tinkering with system data or executable code. | Integrity |
| Repudiation | Denying performance of an action due to missing or inadequate audit logs. | Non-repudiation |
| Information Disclosure | Exposing confidential data—such as financial or personal records—to unauthorized parties. | Confidentiality |
| Denial of Service | Disrupting system operations to block legitimate users from accessing services. | Availability |
| Elevation of Privilege | Illegally gaining higher permissions to execute unauthorized tasks. | Authorisation |

The STRIDE threat model aligns with the core principles of the CIA triad (and related security concepts) as follows:

*   
*   
* **Confidentiality**  
  * **Information Disclosure**: Directly compromises confidentiality by allowing unauthorized parties to access sensitive data.  
  * **Spoofing**: Undermines authentication, which can subsequently result in confidential information falling into unauthorized hands.  
* **Integrity**  
  * **Tampering**: Directly targets integrity through the unauthorized alteration or manipulation of data.  
  * **Repudiation**: Weakens auditability and non-repudiation, causing disputes when system actions cannot be verifiably traced.  
* **Availability & Control**  
  * **Denial of Service**: Threatens availability by hindering or preventing legitimate users from accessing services and data.  
  * **Elevation of Privilege**: Bypasses authorization, granting attackers higher permissions to perform restricted actions.

| Scenario | Spoofing | Tampering | Repudiation | Information Disclosure | Denial of Service | Elevation of Privilege |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| Sending a spoofed email, wherein the mail gateway lacks email security and logging configuration. | ✔ |  | ✔ |  |  |  |
| Flooding a web server with many requests that lack load-balancing capabilities. |  |  |  |  | ✔ |  |
| Abusing an SQL injection vulnerability. |  | ✔ |  | ✔ |  |  |
| Accessing public cloud storage (such as AWS S3 bucket or Azure blob) that handles customer data. |  |  |  | ✔ | ✔ |  |
| Exploiting a local privilege escalation vulnerability due to the lack of system updates and modifying system configuration for a persistent backdoor. |  | ✔ |  |  |  | ✔ |

