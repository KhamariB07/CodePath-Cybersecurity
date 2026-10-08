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
