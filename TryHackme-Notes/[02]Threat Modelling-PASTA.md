**PASTA Threat Modelling Framework**: Study Guide & Practice Exercises

&nbsp;

PASTA stands for **Process for Attack Simulation and Threat Analysis**. It is a step-by-step, risk-centric threat modelling framework used by organizations to identify, evaluate, and mitigate security threats to their applications and infrastructure.

&nbsp;

The framework was created in 2015 by **Tony UcedaVélez** and **Marco Morana**, who detailed the methodology in their book *"Risk Centric Threat Modeling: Process for Attack Simulation and Threat Analysis"*.

&nbsp;

The 7 Steps of PASTA (Study Notes)

&nbsp;

1. **Stage 1: Define Objectives** – Identify business goals, compliance requirements, and security imperatives.  
2. **Stage 2: Define Technical Scope** – Map system boundaries, components, dependencies, and entry points.  
3. **Stage 3: Application Decomposition** – Create Data Flow Diagrams (DFDs) to trace data movement, trust boundaries, and user roles.  
4. **Stage 4: Threat Analysis** – Gather threat intelligence, identify threat actors, and analyze attack vectors relevant to the application.  
5. **Stage 5: Vulnerability Analysis** – Identify existing weaknesses in design, architecture, or code using scanners, CVE lists, and code reviews.  
6. **Stage 6: Attack Modeling** – Simulate potential attacks by constructing attack trees to understand exploit paths and probability.  
7. **Stage 7: Risk & Impact Analysis** – Calculate business impact, prioritize risks, and develop countermeasure strategies.

&nbsp;

## Practical Exercises & Guidance

&nbsp;

### Exercise 1: Mapping PASTA Stages to a E-Commerce Application

Consider a modern web-based retail platform. Practice applying each stage of PASTA by answering the following prompts:

* **Stage 1 Target:** Define 2 key business objectives (e.g., maintaining customer payment data privacy and PCI-DSS compliance).  
* **Stage 2 & 3 Target:** Draw a basic Data Flow Diagram (DFD) illustrating user login, payment gateway processing, and database interactions.  
* **Stage 4 & 5 Target:** Identify 2 realistic threat actors (e.g., credential stuffing bots, malicious insiders) and potential application vulnerabilities (e.g., unpatched SQL injection in checkout form).  
* **Stage 6 & 7 Target:** Build a simple Attack Tree for a "Database Breach" scenario and propose mitigations based on potential business loss.

&nbsp;

### Study Guidance & Tips

* **Focus on Business Value:** PASTA stands out because it aligns technical vulnerabilities directly with financial and strategic business impacts.

**Build Attack Trees:** Practice creating attack trees for common exploits (e.g., XSS, privilege escalation) to master Stage 6\.