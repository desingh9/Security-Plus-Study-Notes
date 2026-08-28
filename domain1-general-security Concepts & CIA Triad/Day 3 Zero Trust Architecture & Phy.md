* Day 3: Zero Trust Architecture \& Physical Security Concepts



=>Earlier, we tackled how organizations implement safeguards using Technical, Managerial, and Operational controls. Today, we are looking at Domain 1.2's modern architectural approach to security—Zero Trust—alongside the critical physical concepts that keep hardware safe.



* **🛑 1. The Zero Trust Architecture (ZTA)**



**=> Traditional security relied on the "Castle and Moat" strategy: protect the perimeter, and trust everyone inside. Zero Trust completely eliminates this. Its guiding philosophy is simple: Never trust, always verify.**



**CompTIA will test your understanding of its foundational tenets:**



* **Assume Breach: Operate under the assumption that attackers are already inside your network.**



* **Explicit Verification: Always authenticate and authorize based on all available data points (user identity, location, device health, service or workload, context).**



* **Least Privilege Access: Limit user access with Just-In-Time (JIT) and Just-Enough-Access (JEA) models to minimize risk.**



* Key Zero Trust Components to Know:



* Data Plane: The communication path where the actual application data flows.
* 
* Control Plane: The management path where policy decisions are made.
* 
* Policy Engine (PE): The brain. It makes the ultimate decision to grant, deny, or revoke access to a resource based on security enterprise policy.
* 
* Policy Administrator (PA): The enforcer. It communicates with the Policy Engine and commands the Policy Enforcement Point to open or close the communication path.
* 
* Policy Enforcement Point (PEP): A system (like a firewall, gateway, or agent) that actually enables, monitors, and terminates connections between a subject and a resource.



🏢 2. Physical Security Concepts



Digital security is useless if an attacker can simply walk into a server room and pull a hard drive. You must know these physical mechanisms:

* Bollards: Thick, heavy concrete or metal posts designed to prevent vehicles from ramming into a building.
* Mantraps / Access Portals: A specialized two-door entry system where the first door must close 
before the second door opens. It is highly effective at preventing tailgating (following an authorized person through a door).



* Fencing \& Signage: The first line of perimeter defense (Deterrent and Preventive).



* Alarms \& Motion Detection: Infrared, ultrasonic, or microwave sensors used to 
detect unauthorized movement (Detective).
* Faraday Cages: An enclosure made of conducting material used to block external electromagnetic fields. 
It prevents unauthorized wireless signals from entering or leaving a specific area.
* 



📊 Quick Summary: The Zero Trust Relationship

* \[ User / Device ]
           │
* &#x20;          ▼
* ┌──────────────────────┐
* │  Policy Enforcement  │ <──── (Control Plane: PE decides, PA commands)
* │     Point (PEP)      │
* └──────────────────────┘
* &#x20;          │
* &#x20;          ▼  (Data Plane: Authenticated \& Encrypted)
* ┌──────────────────────┐
* │  Corporate Resource  │
* └──────────────────────┘



🧠 Quick Knowledge Check

Scenario: A security administrator configures a network so that even when a user successfully logs into their workstation from the main corporate office, 
they must re-authenticate and pass a device health check before accessing the payroll database. Which framework is being actively implemented?



* Answer: Zero Trust. Rather than trusting the user because they are physically inside the office network, 
the system explicitly verifies the user's context and device state at the resource level.











