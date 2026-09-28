# Project 2: "Lets wget This Bread"
### Overview
In this project, I am assigned to write Audit rules to monitor a set of protected files, then run three attack scripts that silently modify those files. My job is to use the audit logs to figure out which attack changed which file — the same attribution work analysts do after a real breach.

## Objectives
- Configure a set of Audit rules to monitor file changes in /protected_files.
- Launch three attacks on some unknown files, and use Audit to identify the altered files and which attacks made the changes.
- Understand how file-level audit trails support post-incident forensics and breach attribution.

## Environment Overview
- #### Operating System: Ubuntu Linux (Azure Virtual Machine)
- #### Text editor: Vim text editor
- #### Monitoring Tool: Linux Audit Daemon (auditd) & ausearch

## Step 1: Downloading and Setting Up the Starter Repo
- Downloaded the starter repository into the home directory

<img width="567" height="362" alt="Screenshot 2026-09-28 at 10 19 16 AM" src="https://github.com/user-attachments/assets/f6d502f2-5267-4d41-a880-556b837de7a2" />

- Unzipped the archive and navigated into the project directory

<img width="559" height="295" alt="Screenshot 2026-09-28 at 10 23 20 AM" src="https://github.com/user-attachments/assets/d42cfcab-d6b4-4515-a0d6-606cf3ab882d" />

- Granted permissions to the attack scripts:
<img width="567" height="20" alt="Screenshot 2026-09-28 at 10 24 00 AM" src="https://github.com/user-attachments/assets/d5e2d169-bdf9-4536-bdb2-7073a5035eff" />

## Step 2: Configuring Audit Rules for /protected_files
- Opened the audit ruled configuration file with elevated privileges:

<img width="559" height="15" alt="Screenshot 2026-09-28 at 10 25 42 AM" src="https://github.com/user-attachments/assets/5ea09d1b-fb43-48dd-b86e-3df77544f194" />

- **Original File**
<img width="560" height="366" alt="Screenshot 2026-09-28 at 10 27 01 AM" src="https://github.com/user-attachments/assets/684fe25f-81e6-47c3-bd28-78911210eb5e" />

- **Edited and modified the file to add 10 new rules**
<img width="561" height="363" alt="Screenshot 2026-09-28 at 10 37 33 AM" src="https://github.com/user-attachments/assets/821978b8-ab9c-42d9-8107-bd0b3611d0ee" />

- Ran **sudo systemctl restart auditd** to restart my audit daemon in the terminal
<img width="565" height="20" alt="Screenshot 2026-09-28 at 10 38 38 AM" src="https://github.com/user-attachments/assets/a247ba93-d95e-4d04-ba39-eb920bbee57b" />

## Step 3: Launching Attacks & Performing Forensics
- Ran the attack scripts to simulate silent file modifications:
<img width="557" height="261" alt="Screenshot 2026-09-28 at 10 43 45 AM" src="https://github.com/user-attachments/assets/88ca0503-085e-4485-8e19-6c4753b56151" />

- Queried the audit logs using ausearch and our unique filter keys to track down which process modified each file:
- Ran **sudo ausearch -ts today -k car_sales_change** in the terminal
<img width="565" height="174" alt="Screenshot 2026-09-28 at 10 47 23 AM" src="https://github.com/user-attachments/assets/1b59feff-cc92-430d-b672-40bd182cb9ad" />

- Ran **sudo ausearch -ts today -k car_sales_change -m PATH** to get a broader look at the events tied to the key:

- Ran **`sudo ausearch -ts today`** (or searched across the keys) to capture the forensic evidence of the file modifications:

<img width="486" height="19" alt="Screenshot 2026-09-28 at 10 52 03 AM" src="https://github.com/user-attachments/assets/ebaadefa-6286-45c3-af1f-ad7675aac6b7" />

- **Results**

<img width="559" height="328" alt="Screenshot 2026-09-28 at 10 52 34 AM" src="https://github.com/user-attachments/assets/c0f946c1-1af4-4d82-8f80-dc3890dab7d5" />


- **Forensic Findings & Attack Attribution:**
  - **Attack A (`attack-a`)**: Modified `/home/codepath/project2-main/protected_files/cloudia.txt` (Triggered key: `cloudia_change`)
  - **Attack B (`attack-b`)**: Modified `/home/codepath/project2-main/protected_files/oakley.txt` and `squeaky.txt` (Triggered keys: `oakley_change`, `squeaky_change`)
  - **Attack C (`attack-c`)**: Modified `/home/codepath/project2-main/protected_files/precipitation.csv` (Triggered key: `precipitation_change`)











