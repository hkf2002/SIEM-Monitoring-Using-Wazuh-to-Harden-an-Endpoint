# SIEM Monitoring | Using Wazuh to Threat Hunt and identify System Vulnerabilities
In this repository I will be going over examples of using Wazuh to harden a system using Logs and Graphs to identify Vulnerabilities. As well as, Threat Hunting.

# VM and Agent Environment

| Type | Specifications | 
| ---- | ------------- |
|  OS  | Ubuntu Host  |
| Memory  | 8192 MB  |
| Storage  | 75 GB  |
| Network |  Bridged  |

| Type | Specifications |
| ---- | ------------- |
|  OS  | Windows 11 Pro Agent |
| Memory  | 32 GB  |
| Storage  | 2 TB  |
| Network |  Ethernet  |

| Type | Specifications |
| ---- | ------------- |
|  OS  | Kali Linux |
| Memory  | 16 GB  |
| Storage  | 256 GB |
| Network |  Wi-Fi |

# Vulnerability Chart

<img width="2459" height="959" alt="Screenshot 2026-09-20 224606" src="https://github.com/user-attachments/assets/10fe7e39-db3e-4f2e-821d-f038c1dac47f" />

In the Wazuh Dashboard there are Two Pie Charts and a Total Alerts Count.

We're interested in the Vulnerability Severity Chart.

<img width="332" height="656" alt="Screenshot 2026-09-20 225236" src="https://github.com/user-attachments/assets/bcae4305-bc45-4fde-a2e8-3767a86a527b" />

If we click on the three bars on the top left to expand menu. We can open the explore tab and click on Discover.

<img width="550" height="478" alt="Screenshot 2026-09-20 225406" src="https://github.com/user-attachments/assets/f97a2d17-7c63-4c7c-9f33-3a7545d40cae" />

Once we are in the menu we can filter Index Patterns to ***wazuh-states-vulnerabilities***. 

I have also filtered the logs to ***vulnerability.severity:exists*** and ***vulnerability.severity:is one of High***.

This allows me to target High severity vulnerabilities.

<img width="1947" height="972" alt="Screenshot 2026-09-20 230612" src="https://github.com/user-attachments/assets/bbbfee71-7b6d-4abf-84d3-e112e4dd9991" />

If we expand the long we can find identify the vulnerability description. This description tells us the issue with our Agent. 

<img width="1838" height="725" alt="Screenshot 2026-09-20 232438" src="https://github.com/user-attachments/assets/e04d45cc-ab0f-40c0-b396-fb029b764646" />

This specific issue affects the 7-Zip file archiver version 9.21 through  26.00. The Agent has version 22.01. 

In order to resolve this issue we can update 7-Zip
