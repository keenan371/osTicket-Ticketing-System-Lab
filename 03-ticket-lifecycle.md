# Walkthrough 3: Complete osTicket Ticket Lifecycle

[Back to project overview](README.md)

## Objective

Demonstrate intake, business-impact assessment, SLA selection, routing, communication, resolution, closure, and restricted escalation.

## Environment and technologies

osTicket end-user portal, Agent Panel, Admin Panel, SLA plans, departments, queues, threaded replies, and role-based access.

## Scenario 1: Online banking outage

### 1. Submit and inspect

Using `/osTicket/open.php`, fictional user Bo Banker submitted **URGENT: entire mobile and online banking system is down**. It entered Support as Normal priority, Default SLA (18 hours), and Unassigned. This proved that an agent must assess the business impact.

![Outage before triage](evidence/06_T1_as_hhippo_defaults_before_edit.png)

### 2. Prioritize and route

Hank assessed the organization-wide outage and changed the SLA to Sev-A (one hour, 24/7).

![Sev-A applied](evidence/07_T1_sla_changed_to_SevA.png)

He transferred it from Support to Online Banking.

![Transferred to Online Banking](evidence/08_T1_transferred_to_Online_Banking.png)

The one-hour deadline had passed, so osTicket marked it overdue. Hank retained access through his extended department assignment.

![Sev-A ticket marked overdue](evidence/09_T1_online_banking_SevA_overdue_hhippo_still_has_access.png)

### 3. Communicate, resolve, and close

Ruby opened the Online Banking queue, posted a customer-facing reply, and changed the ticket to Resolved.

![Resolved by Ruby Bunny](evidence/14_T1_resolved_by_rbunny_queue_empty.png)

The thread retained Hank's triage and transfer, the overdue event, Ruby's response, and closure.

![Complete ticket history](evidence/15_T1_full_history_hhippo_to_rbunny_resolved.png)

### 4. Escalate and verify access

Ruby transferred the resolved ticket to SysAdmins without maintaining referral access. The transfer reopened the ticket and restarted its Sev-A clock.

![Transferred out of Ruby's queue](evidence/16_T1_transferred_to_SysAdmins_rbunny_lost_access.png)

The direct link then showed only a restricted view.

![Restricted SysAdmins view](evidence/17_T1_in_SysAdmins_rbunny_restricted_view_reopened.png)

Even the administrator could not see it before explicit department access was added.

![Admin queue before access](evidence/18_admin_cannot_see_SysAdmins_ticket.png)

## Scenario 2: Adobe upgrade

An end user submitted **Accounting department needs Adobe upgrade, it is broken**. Hank kept it in Support, applied Sev-B (four hours), posted the resolution, and closed it.

![Adobe ticket with Sev-B](evidence/10_T2_sla_SevB_support.png)

![Adobe ticket resolved](evidence/11_T2_resolved_reply_posted_by_hhippo.png)

## Scenario 3: CFO laptop

An end user submitted **CFO laptop will no longer turn on**. Because it affected one device rather than the entire company, Hank used Sev-B in Support, documented the work, and resolved it.

![CFO laptop with Sev-B](evidence/12_T3_sla_SevB_support.png)

![CFO laptop resolved](evidence/13_T3_resolved_reply_posted_by_hhippo.png)

## Intake and notification notes

Production tickets can arrive by portal, email, phone, chat, or in person. Every request should be recorded for ownership, communication history, SLA measurement, and reporting. osTicket can notify users and agents about creation, replies, assignments, transfers, overdue status, and closure. This isolated VM had no outbound mail service, so email delivery was not claimed as tested.

## Result

All three tickets were assessed, assigned an SLA, routed, documented, and resolved. The outage also demonstrated multi-agent history, an overdue SLA, department transfer, reopening, and least-privilege escalation.

