
# osTicket: Ticketing System Lifecycle & Configuration

This lab demonstrates the end-to-end installation and configuration of osTicket, an open-source ticketing system. I focus on setting up the environment, establishing business logic (SLAs, Departments), and executing the full ticket lifecycle from intake to resolution.

## 🛠️ Prerequisites and Installation

To begin, I configured the Internet Information Services (IIS) environment and managed PHP extensions to ensure the web server could communicate with the osTicket database.

* **IIS and PHP Configuration:** Setting up the PHP Manager to handle the osTicket requirements.
<img width="499" alt="PHP-Manager-IIS-Setup" src="https://github.com/user-attachments/assets/404ac746-90c7-4d81-bbc7-b55de1887394" />

* **Deployment Success:** The osTicket installation is live and ready for administrative configuration.
<img width="1219" alt="osTicket-Deployment-Success" src="https://github.com/user-attachments/assets/92149055-8c09-47de-8b71-8bdf2a29b087" />

---

## ⚙️ Post-Installation Configuration

A ticketing system is only as good as its organization. In this phase, I established the "Business Rules" for the help desk.

* **Service Level Agreements (SLAs):** Defined response and resolution times for different priority levels (Sev-A, Sev-B, etc.).
<img width="1027" alt="Service Level Agreements" src="https://github.com/user-attachments/assets/d4e71003-da36-476c-b750-049ed4a9f8a8" />

* **Help Topics:** Organized ticket categories to ensure incoming requests are routed to the correct department (Support, Sales, Admin).
<img width="966" alt="osHelpTopics" src="https://github.com/user-attachments/assets/d6311135-1384-4a59-afa5-1c341685386b" />

* **User Directory:** Populated the directory with end-users and agents to simulate a real-world environment.
<img width="1027" alt="User Directory users" src="https://github.com/user-attachments/assets/8adbf3f3-b90a-4af1-80c8-33f0ef1c1c5c" />

---

## 🤳 Ticket Lifecycle Examples

The final step was simulating the daily operations of an IT professional, managing tickets through their entire lifecycle.

* **User Intake:** Creating a ticket from the end-user perspective (Simulating "Karen" reporting an issue).
<img width="1027" alt="Open a New Ticket-end userkaren" src="https://github.com/user-attachments/assets/70179f85-1516-47ea-8fe9-d12a47106541" />

* **Agent Management:** Demonstrating the difference between the Admin panel and the Agent panel where work is actually performed.
<img width="993" alt="agent vs admin panel" src="https://github.com/user-attachments/assets/a55cf024-f082-404d-b82e-775115d79cd3" />

* **Resolution:** Successfully closing a high-priority (Sev-B) ticket according to SLA guidelines.
<img width="1027" alt="SLA_Sev-B_Ticket_Closure_Success" src="https://github.com/user-attachments/assets/10a3a77b-519d-45ae-a909-73e3fb4f44f3" />
