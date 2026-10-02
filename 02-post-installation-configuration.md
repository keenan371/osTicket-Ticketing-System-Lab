# Walkthrough 2: Configure osTicket After Installation

[Back to project overview](README.md)

## Objective

Configure departments, SLAs, agents, and access roles for a fictional banking support team.

## Environment and technologies

osTicket 1.15.8 Admin Panel and Agent Panel on the Azure Windows VM.

## Demonstration

### 1. Enter the Admin Panel

1. Browse to `http://localhost/osTicket/scp` and sign in as the administrator.
2. Switch from the Agent Panel to the Admin Panel.

### 2. Configure departments

1. Open **Staff > Departments**.
2. Delete the unused Maintenance department.
3. Create **Online Banking** and **SysAdmins** as top-level departments.
4. Keep **Support** as the default intake department.

### 3. Configure SLA plans

1. Open **Manage > SLA Plans**.
2. Create `Sev-A`: one-hour grace period, 24/7 schedule.
3. Create `Sev-B`: four-hour grace period, 24/7 schedule.
4. Keep the Default SLA at 18 hours.

### 4. Create and route agents

1. Open **Staff > Agents** and add Hank Hippo (`hhippo`).
2. Set Support as his primary department and grant extended Online Banking access.
3. Add Ruby Bunny (`rbunny`) and set Online Banking as her primary department.
4. Confirm both agents have active roles. Passwords were entered privately.

The evidence below shows the configured agents, departments, SLAs, and first submitted ticket.

![Configured help desk and first ticket](evidence/05_agents_depts_sla_ticket1_created.png)

### 5. Add restricted SysAdmins access

1. In **Staff > Agents**, edit the administrator and open **Access**.
2. Add extended SysAdmins access with the **View only** role.
3. Save and return to the Agent Panel.

![View-only SysAdmins access granted](evidence/19_admin_granted_SysAdmins_view_only_access.png)

The escalated ticket then appeared in the queue.

![Escalated ticket visible](evidence/20_admin_now_sees_escalated_T1_in_queue.png)

Opening it confirmed there were no reply, edit, assignment, or transfer controls.

![View-only ticket controls](evidence/21_admin_view_only_T1_no_edit_controls.png)

## Result

The help desk had Support, Online Banking, and SysAdmins departments; Default, Sev-A, and Sev-B SLAs; and agents whose visibility and actions changed according to department membership and role.

