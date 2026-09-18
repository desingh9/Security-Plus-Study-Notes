## **📘 Week 1, Day 6: Domain 2.0 — Malware Types, System Attacks, & Indicators of Compromise**

Welcome to **Day 6**\! Yesterday, we covered social engineering and human vulnerabilities. Today, we focus on technical system threats: **Malware Types, System Attacks, and Indicators of Compromise (IoCs)**.

Recognizing how specific malware operates and identifying its technical footprint is key to answering scenario-based questions in **Domain 2.0 (22%)**.

🦠 1\. **Malware Categories & Behavior Matrix**&nbsp;

Use this matrix to differentiate malware types by their primary operational mechanism:

&nbsp;

| Malware Type | Core Operational Mechanism | Primary Indicator / Payload |
| :---- | :---- | :---- |
| **Ransomware** | Encrypts local/network files using strong asymmetric/symmetric keys | Extortion note, demands cryptocurrency, .locked extensions |
| **Trojan** | Masquerades as legitimate software to trick users into execution | Unexpected background network connections, fake utilities |
| **Worm** | Self-propagating malware that spreads automatically across networks | Massive network traffic spikes, port scans without human action |
| **Rootkit** | Operates at the OS kernel level (Ring 0\) to hide processes and files | Inconsistent API results, hooks kernel calls, hides processes |
| **Keylogger** | Captures keystrokes to steal credentials and sensitive data | Unauthorized background hooks on input drivers |
| **Botnet / RAT** | Provides Remote Access Trojan capabilities for Command & Control (C2) | Periodic beaconing traffic to external C2 server IPs |
| **Logic Bomb** | Dormant code triggered by a specific event, time, or condition | Executes destructively after an admin is removed from AD |

&nbsp;

&nbsp;