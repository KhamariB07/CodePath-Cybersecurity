# Lab 4: "DoS DoS DoS DoS DoS DoS DoS DoS DoS DoS DoS"
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
- Verified that **nginx** is running in **VM** using **sudo systemctl status nginx**
- Verified that Slowloris is executable by running **which slowloris-run**

- **Result:** Confirmed nginx.service is active (running) with PID 1070.
- **Result:** Located executable at /usr/local/bin/slowloris-run.
<img width="1907" height="1129" alt="Screenshot 2026-10-09 111436" src="https://github.com/user-attachments/assets/48f12405-b41b-4eb3-a918-cc909c17da43" />


## Step 2: Run Attack 1 (Unprotected)
- Opened the Netdata real-time monitoring dashboard at **(http://127.0.0.1:19999)** in **Firefox**, focusing on **Network > IPv4 > Sockets > TCP.**
<img width="1552" height="375" alt="Screenshot 2026-10-09 113746" src="https://github.com/user-attachments/assets/074c7e44-4026-4739-8fb9-5a57444b9c23" />

- Ran the **Unprotected** Slowloris Attack in the terminal using **slowloris-run 127.0.0.1 -s 500**
<img width="640" height="24" alt="Screenshot 2026-10-09 114002" src="https://github.com/user-attachments/assets/acdb6f34-a4ff-4199-b945-3763bd55dbe5" />

- **Results:** Network traffic protocols spiked dramatically up toward 1,000 active TCP sockets because Nginx held open all incomplete HTTP requests, exhausting connection resources.
<img width="1532" height="346" alt="Screenshot 2026-10-09 114231" src="https://github.com/user-attachments/assets/7b7fedc2-8875-4fc0-8174-a92b6fad9ca3" />

## Step 3: Configure Nginx Mitigation
- ran sudo
<img width="544" height="22" alt="Screenshot 2026-10-09 115219" src="https://github.com/user-attachments/assets/87ed4466-cb77-4d31-a42d-0f0bd89a6024" />
- **Edited /etc/nginx/nginx.conf to add four critical timeout directives within the http { ... } block:
**http {**
   ** ...**
    # DoS Mitigation Timeouts
    **client_body_timeout 5s;**
    **client_header_timeout 5s;**
    **keepalive_timeout 15s;**
    **send_timeout 10s;**
    ...
}**
<img width="1901" height="1118" alt="Screenshot 2026-10-09 115847" src="https://github.com/user-attachments/assets/16846582-6933-4736-9c8c-7cfce40e80c4" />
- tested and reloaded
<img width="690" height="71" alt="Screenshot 2026-10-09 121214" src="https://github.com/user-attachments/assets/369c6aeb-7656-49fb-8613-2e632e8ce3bd" />

## Step 4: Run Attack 2 (Protected)
- ran ___ in terminal
<img width="603" height="259" alt="Screenshot 2026-10-09 121602" src="https://github.com/user-attachments/assets/88979228-af10-4ee5-867c-975b7f0400d2" />
- result
<img width="1540" height="351" alt="Screenshot 2026-10-09 121446" src="https://github.com/user-attachments/assets/bf03611b-9c10-4855-933d-4f2de2e2dc11" />









