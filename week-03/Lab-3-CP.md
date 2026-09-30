# Lab 3:  "That's Snort of a Lot of Rules"
### Overview
In this lab, I ran an **Open-Source Snort NIDS (Network Intrusion Detection System)** against captured traffic, learned how a rule is built, and how to write my own rules to catch specific stages of an attack. 

## Objectives
- Explain what a signature-based NIDS is and how Snort matches traffic against rules
- Run Snort against a packet capture (pcap) and read its alerts
- Write Snort rules using content and flow to catch specific attack stages
- Tune a rule to cut false positives — catch the attack without flagging benign traffic
 
## Environment Overview
- **Sensor:** Snort 3
- **Deployment:** Disposable Docker Container
- **Tools:** Packet Captures (`.pcap`), Custom Rule Files
