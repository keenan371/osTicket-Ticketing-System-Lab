# osTicket Help Desk: Azure Deployment, Configuration, and Ticket Lifecycle

## Project summary

This portfolio project documents a complete hands-on osTicket help-desk lab. I created a Windows 10 virtual machine in Microsoft Azure, installed IIS, PHP, MySQL, and osTicket, configured the help desk for a fictional banking support environment, and processed three tickets from intake through resolution and escalation.

The work is divided into three independent walkthroughs so installation, administration, and daily support operations can each be followed from beginning to end.

## Environments and technologies used

- Microsoft Azure: resource group, Windows VM, virtual network, NIC, public IP, and RDP
- Windows 10 Enterprise 22H2, `Standard_D4ls_v6` (4 vCPU, 8 GiB)
- IIS with CGI, PHP Manager, PHP 7.3.8, URL Rewrite, and VC++ Redistributable
- MySQL 5.5.62 and HeidiSQL 12.3
- osTicket 1.15.8
- Windows PowerShell and Command Prompt

## Demonstration walkthroughs

1. **[Install osTicket on an Azure Windows VM](01-installation.md)**  
   Create the Azure environment, connect through RDP, install every dependency, create the database, complete the browser installer, and secure the installation.

2. **[Configure osTicket after installation](02-post-installation-configuration.md)**  
   Create departments, SLA plans, agents, roles, and department access.

3. **[Run a complete ticket lifecycle](03-ticket-lifecycle.md)**  
   Submit, assess, prioritize, route, work, resolve, close, and escalate real lab tickets.

## Final result

The finished help desk contained three departments, two custom SLA plans, two agents with different access, and three completed ticket scenarios. The outage ticket preserved a full history across two agents and demonstrated department-based access control.

![Completed ticket thread across two agents](evidence/15_T1_full_history_hhippo_to_rbunny_resolved.png)

The [`evidence`](evidence/) directory contains 21 numbered screenshots. Each walkthrough places its matching screenshots directly beside the steps they prove.

## Scope and cleanup

- Personal training lab, not client or production work.
- All agent and customer identities are fictional.
- Passwords, Azure identifiers, and the VM public IP are excluded.
- The Azure resource group was deleted after evidence capture to stop remaining charges.

