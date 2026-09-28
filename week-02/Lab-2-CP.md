# Lab 2:  "Oops!...I Audit Again"
### Overview
In this lab, I was tasked to Practice using a Host Intrusion Detection System (or HIDS) Linux Audit daemon that uses preconfigured and custom rules to log potential security events to /var/log. The Linux Audit daemon can monitor system calls, watch file accesses, and record user commands, with a more comprehensive list of auditable events available here.

## Objectives
- Install Audit on your VM
- Gain familiarity with Vim text editor
- Write audit.rules to alert on file modifications
- Sort through the /var/log events for audit findings
- Understand what a HIDS can detect that network-level monitoring cannot
 
## Environment Overview
- #### Networking: Azure Virtual Machine
- #### Vim text editor

## Step 1: Setting Up Audit on My VM
- Using my Azure VM, I installed Auditd using the following command: 
- #### sudo apt-get install auditd
<img width="553" height="220" alt="Screenshot 2026-09-28 at 8 33 59 AM" src="https://github.com/user-attachments/assets/6ebb11d8-c2eb-4157-b0b2-8a8cd82405c6" />

- #### sudo systemctl status auditd
(to confirm it successfully ran)

<img width="561" height="339" alt="Screenshot 2026-09-28 at 8 36 38 AM" src="https://github.com/user-attachments/assets/806e4a35-8cae-43b3-ad53-f2ea2271f9c9" />
