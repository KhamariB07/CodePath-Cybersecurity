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

## Step 2: Create a New File to Monitor File Changes
- In the ~ directory, I ran the following command to create a new file:
- #### touch unit2_lab.txt
- I then followed up with the **ls** command to ensure the file was created:

<img width="574" height="110" alt="Screenshot 2026-09-28 at 8 43 33 AM" src="https://github.com/user-attachments/assets/b005e0df-14b2-4f99-b980-cd92cd3acecd" />

## Step 3: Used Vim text editor to Create Files
- To open the file I created, I ran **vi unit2_lab.txt** in the terminal:
<img width="566" height="32" alt="Screenshot 2026-09-28 at 8 57 02 AM" src="https://github.com/user-attachments/assets/e9493381-d392-49a7-972f-1677051e1338" />

- This later opened the file and allowed me to insert text by pressing **I** on my keyboard
<img width="560" height="370" alt="Screenshot 2026-09-28 at 8 54 49 AM" src="https://github.com/user-attachments/assets/6c75fada-904c-4d9b-b855-5edf98091ec5" />

- I inserted the following text into my file:
- **This is my CodePath lab 2 File!**
<img width="562" height="368" alt="Screenshot 2026-09-28 at 8 56 14 AM" src="https://github.com/user-attachments/assets/6388a922-b5bb-4369-8c1e-5c26073e2f2d" />

- Used the **:wq** command to exit and save the file

<img width="565" height="362" alt="Screenshot 2026-09-28 at 8 56 41 AM" src="https://github.com/user-attachments/assets/f042251d-70ea-494c-a4ff-8cbd85e13317" />




