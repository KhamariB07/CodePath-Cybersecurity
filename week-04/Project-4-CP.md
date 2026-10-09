# Lab 4: "DoS DoS DoS DoS DoS DoS DoS DoS DoS DoS DoS DoS "
### Overview
For this project, I'll be running a type of DoS attack named **Slowloris** against the local server on my **Azure VM** and design rules in **nginx** to mitigate the attack.

## Objectives
- **Use nginx and Slowloris**
- **Configure DoS mitigation rules**
- **Analyze .pcap files to determine which server is vulnerable/prepared to mitigate DoS attacks**
- **Understand why application-layer DoS attacks require different mitigations than volumetric flood attacks**

## Environment Overview
- Operating System: Ubuntu Linux Virtual Machine (hosted on Azure Remote Desktop / CodePath CYB102 environment)
- Remote Access Protocol: xrdp (XFCE Desktop Environment via Remote Desktop)
- Web Browser: Mozilla Firefox

## Step 1: Setup & Verification
- Check for veri
<img width="1907" height="1129" alt="Screenshot 2026-10-09 111436" src="https://github.com/user-attachments/assets/48f12405-b41b-4eb3-a918-cc909c17da43" />
- used to check
<img width="1586" height="26" alt="Screenshot 2026-10-09 112628" src="https://github.com/user-attachments/assets/88321c44-f13e-468a-b3a9-f26729ade116" />
- opened firewall to
<img width="1904" height="1125" alt="Screenshot 2026-10-09 113042" src="https://github.com/user-attachments/assets/092da48a-cff2-4fc4-a068-bc9e3573686f" />
- metrics
<img width="1907" height="1123" alt="Screenshot 2026-10-09 113316" src="https://github.com/user-attachments/assets/8a9afe2e-9a90-470a-ae0f-b0112abc9e0c" />

## Step 2: Run Attack 1 (Unprotected)
- using search
<img width="1552" height="375" alt="Screenshot 2026-10-09 113746" src="https://github.com/user-attachments/assets/074c7e44-4026-4739-8fb9-5a57444b9c23" />
- ran slowloris attack
<img width="640" height="24" alt="Screenshot 2026-10-09 114002" src="https://github.com/user-attachments/assets/acdb6f34-a4ff-4199-b945-3763bd55dbe5" />
- results
<img width="1532" height="346" alt="Screenshot 2026-10-09 114231" src="https://github.com/user-attachments/assets/7b7fedc2-8875-4fc0-8174-a92b6fad9ca3" />

## Step 3: Configure Nginx Mitigation
- ran sudo
<img width="544" height="22" alt="Screenshot 2026-10-09 115219" src="https://github.com/user-attachments/assets/87ed4466-cb77-4d31-a42d-0f0bd89a6024" />
- added and saved and exited
<img width="1901" height="1118" alt="Screenshot 2026-10-09 115847" src="https://github.com/user-attachments/assets/16846582-6933-4736-9c8c-7cfce40e80c4" />









