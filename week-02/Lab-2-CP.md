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
- #### Text editor: Vim text editor

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

## Step 4: Writing a Rule for Audit
- Starting out I ran the **sudo auditctl -l** command to confirm that Audit Currently has no rules set up

<img width="563" height="42" alt="Screenshot 2026-09-28 at 9 09 24 AM" src="https://github.com/user-attachments/assets/dc002515-b5f0-4da3-8c6f-fdbce48d02e8" />

- Now, I have started editing the file: I ran **vi /etc/audit/rules.d/audit.rules**

<img width="563" height="20" alt="Screenshot 2026-09-28 at 9 26 20 AM" src="https://github.com/user-attachments/assets/08421fd1-63a2-4269-8187-0399487e99c5" />

- This led me to a blank file with [Permission Denied}

<img width="564" height="342" alt="Screenshot 2026-09-28 at 9 24 51 AM" src="https://github.com/user-attachments/assets/0af6be1c-1f03-48fb-9de0-1c91539e868f" />

- To get around this I used the **sudo** command
- **sudo vi /etc/audit/rules.d/audit.rules**

<img width="556" height="18" alt="Screenshot 2026-09-28 at 9 28 56 AM" src="https://github.com/user-attachments/assets/e54022e1-2a9b-4dde-a8df-dd2e63e8539b" />

- Here I added the rule **-w /home/codepath/unit2_lab.txt -p w -k unit2_lab_changes**
- **Results**
<img width="561" height="365" alt="Screenshot 2026-09-28 at 9 29 38 AM" src="https://github.com/user-attachments/assets/2e006fb0-eddd-48ce-b9f6-d4f3dfe42916" />

- Ran **:wq** o exit and save the file

<img width="559" height="337" alt="Screenshot 2026-09-28 at 9 34 52 AM" 
src="https://github.com/user-attachments/assets/f60a479d-3db9-4838-a1f0-0e869cb2ab61" />

- Ran the **sudo systemctl restart auditd** command to restart Audit so that my file changes are taken into action
<img width="560" height="29" alt="Screenshot 2026-09-28 at 9 39 06 AM" src="https://github.com/user-attachments/assets/dbe89411-192a-4f96-a3a8-e9e3ef42e239" />

## Step 5: Viewing the Event Logs
(Now that I have established a rule in place, I should log an event every time **unit2_lab.txt** is modified)
- Ran **sudo vi /home/codepath/unit2_lab.txt** to test this:
<img width="565" height="17" alt="Screenshot 2026-09-28 at 9 46 11 AM" src="https://github.com/user-attachments/assets/3212d466-986b-4350-b88b-65ec343afaec" />

- Made a small change to my file
<img width="566" height="361" alt="Screenshot 2026-09-28 at 9 47 02 AM" src="https://github.com/user-attachments/assets/49942ab9-5ca3-4913-931d-f208e306eb9c" />

- **:wq** to save and establish my changes
<img width="565" height="363" alt="Screenshot 2026-09-28 at 9 49 18 AM" src="https://github.com/user-attachments/assets/01cc06ab-1872-41da-b1a0-0c9cbfa43041" />

- Ran the **sudo ausearch -ts today -k unit2_lab_changes** command to filter the logs with my Key Filter
<img width="566" height="17" alt="Screenshot 2026-09-28 at 9 51 34 AM" src="https://github.com/user-attachments/assets/614848c0-cc96-4932-90c9-5e7ad40d3755" />
- **Successfully filtered the logs using unit2_lab_changes to reveal the exact tool (vim.basic) used to modify the file.**
<img width="562" height="341" alt="Screenshot 2026-09-28 at 9 52 35 AM" src="https://github.com/user-attachments/assets/e365510a-7b15-42b6-ba51-d13eba8ec4e8" />










