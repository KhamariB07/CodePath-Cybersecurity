# Lab 4: "Monkey in the Middle"
### Overview
In this lab, I analyzed HTTPS network traffic using Wireshark and then used mitmproxy to intercept and inspect the same type of traffic through a proxy. The lab demonstrated how HTTPS encrypts communication between a client and server and how a Man-in-the-Middle (MITM) attack can intercept that communication when certificate trust is established.

## Objectives
- **Analyze network traffic using Wireshark**
- **Install and configure mitmproxy on your virtual machine**
- **Analyze network traffic using mitmproxy**
- **Modify intercepted network requests**
- **Understand how HTTPS certificate trust enables — and limits — MITM interception**

## Environment Overview
Operating System: Ubuntu Linux
Virtual Machine: cyb102 Ubuntu VM
Deployment: Azure Labs / Virtual Machine
Network Analysis Tool: Wireshark
MITM Proxy: mitmproxy
Traffic: HTTP and HTTPS
Tools: Wireshark, mitmproxy, Browser, Terminal

## Step 1: Analyze Network Traffic with Wireshark
- Using my Azure Virtual machine, I ran **sudo wireshark** from the terminal of my graphical interface and selected eth0
- I then visited the encrypted website **https://www.codepath.org** to analyze network traffic

<img width="1129" height="451" alt="Screenshot 2026-10-08 at 1 11 00 PM" src="https://github.com/user-attachments/assets/52a27d4f-a265-4f42-b31e-929e36103c14" />

- **Results**
<img width="1710" height="1105" alt="Screenshot 2026-10-08 at 1 08 52 PM" src="https://github.com/user-attachments/assets/917c67af-f6d3-4569-be3c-e8ac2ccce3f7" />

## Step 2: Analyze Network Traffic with mitmproxy

