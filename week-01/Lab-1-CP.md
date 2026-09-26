# Lab 1:  "It Wasn't Me"
### Overview
In this lab, I was tasked to carry out the following scenario: "You’ve been hired to the Security Operations Center of the company Boring Office to help track down the employee behind some nefarious activity. On April 19th, 2023 at 12:50PM an employee at Boring Office sent their deepest darkest secrets to everyone within the company. Or did they? This employee claims that someone else at the company is impersonating them, and your job is to hunt for who this rogue user is."

## Objectives
- Analyze a .pcap file to find a user's IP address
- Use DHCP logs to correlate an IP address to a host device
- Identify which user was logged in to a host device using account security logs
- Understand how packet captures, DHCP logs, and system security logs chain together to attribute network activity to a specific user
 
## Environment Overview
- #### Networking: Wireshark

## Step 1: Find the IP Address
- Opened given .pcap file in Wireshark
- Used the Display filter to filter out packets
  
<img width="1709" height="1077" alt="Screenshot 2026-09-25 at 11 18 28 PM" src="https://github.com/user-attachments/assets/fc67d600-c498-410b-b42f-59de116bba6f" />

- Used the Display filter to keep remaining Simple Mail Transfer Protocol (SMTP) packets
- Filtered out the IP address of the malicious email sender
  
<img width="1710" height="1107" alt="Screenshot 2026-09-25 at 11 20 14 PM" src="https://github.com/user-attachments/assets/c0c1f204-9926-40cb-8feb-718d22bc9a21" />

## Step 2: Correlate the IP address to the Host Computer
- Opened the DHCP log through a text editor
- Identified six events that occurred before 12:50PM
- Located the event at 12:11:27pm, matched the IP address
- Identified the host device as USER2
  
<img width="640" height="408" alt="Screenshot 2026-09-25 at 11 30 21 PM" src="https://github.com/user-attachments/assets/b9109e73-d062-454a-9f59-dae9a65f8b32" />

## Step 3: Analyze the security Log
- Analyzed the security logs and found the corresponding user from step 2
  
<img width="653" height="702" alt="Screenshot 2026-09-25 at 11 32 50 PM" src="https://github.com/user-attachments/assets/9d08aada-8b59-4a26-98da-44829966a5f1" />

## Key Takeaways
- Learned how to utilize and analyze packets through Wireshark.
- Learned commands such as "smtp" and 'smtp contains "from"'.
- Understood how to correlate a host computer and IP address.
- Demonstrated understanding of security logs.






