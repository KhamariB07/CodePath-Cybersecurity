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
- Deployment: Azure Labs / Virtual Machine
- Network Analysis Tool: Wireshark
- MITM Proxy: mitmproxy
- Traffic: HTTP and HTTPS
- Tools: Wireshark, mitmproxy, Browser, Terminal

## Step 1: Analyze Network Traffic with Wireshark
- Using my Azure Virtual machine, I ran **sudo wireshark** from the terminal of my graphical interface and selected eth0
- I then visited the encrypted website **https://www.codepath.org** to analyze network traffic

<img width="1129" height="451" alt="Screenshot 2026-10-08 at 1 11 00 PM" src="https://github.com/user-attachments/assets/52a27d4f-a265-4f42-b31e-929e36103c14" />

- **Results**
<img width="1710" height="1105" alt="Screenshot 2026-10-08 at 1 08 52 PM" src="https://github.com/user-attachments/assets/917c67af-f6d3-4569-be3c-e8ac2ccce3f7" />

## Step 2: Analyze Network Traffic with mitmproxy
- Installed docker on my VM through the terminal using **sudo apt install docker.io**
- With docker I installed **mitmproxy** to analyze network traffic
<img width="946" height="548" alt="step2mitm" src="https://github.com/user-attachments/assets/581b107a-d324-4fa9-9601-70b38e9f4566" />
- **Results**
<img width="959" height="548" alt="mitmstep2" src="https://github.com/user-attachments/assets/7bef135e-57a3-4021-9a35-a8dce8b068ab" />

