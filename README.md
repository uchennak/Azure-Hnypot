# Azure-Hnypot

<img width="700" height="430" alt="image" src="https://github.com/user-attachments/assets/78c6b7cd-0c4a-4961-9928-73955f5c666a" />



## Introduction
In this project, a honeypot was created in Azure in order to capture and analyze logs from multiple sources into a Log Analytics Workspace using Microsoft Sentinel to build attack maps, trigger alerts, and create incidents. Security metrics were measured in the exposed environment for 24hrs, security controls were implemented to harden the environment, then measured again. The metrics involved are:

* SecurityEvent (Windows Event Logs) - derived from the Windows Virtual Machine and the installed MSSQL Server.
* Syslog (Linux Event Logs) - derived from the Linux Virtual Machine
* SecurityAlert (Log Analytics Alerts Triggered)
* SecurityIncident (Incidents created by Sentinel)
* AzureNetworkAnalytics_CL (Malicious Flows allowed into the honeynet due to configured NSG rules)

The honeynet architecture consists of:
* Virtual Network (VNet)
* Network Security Group (NSG)
* Virtual Machines (2 windows, 1 linux)
* Log Analytics Workspace
* Azure Key Vault
* Azure Storage Account
* Microsoft Sentinel

Initially, all resources were exposed to the internet, the security groups, and vm firewalls were set to allow all traffic. Afterwards, the all public traffic was blocked with the exception of my personal computer.

## Attack Maps before hardening:
<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/d36d37e1-51ea-4b17-95d6-e1b6bc706526" />
<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/bd2ee774-f481-462f-8d4e-ef9df47cb650" />
<img width="800" height="500" alt="mssql pre hardening" src="https://github.com/user-attachments/assets/a1949b0b-a5ac-48e3-8869-a35751f98b26" />
<img width="800" height="500" alt="linux ssh pre hardening" src="https://github.com/user-attachments/assets/1ea8ab0e-83a3-4d77-be32-1e86302da88c" />

## After hardening no more malicious activity found:
<img width="850" height="550" alt="rdp post hardening" src="https://github.com/user-attachments/assets/0a58e5b7-0aea-4de3-a280-452e40c3d86a" />
<img width="850" height="550" alt="nsg malicious post hardening" src="https://github.com/user-attachments/assets/6d951b8e-c204-4fd0-824e-a63ee7a048e7" />
<img width="850" height="550" alt="mssql post hardening" src="https://github.com/user-attachments/assets/b8b075f5-fa43-470c-91b6-6c0b9ceda4a1" />
<img width="850" height="550" alt="linux ssh post hardening" src="https://github.com/user-attachments/assets/13945803-80e7-431c-a4fc-e52f3ac2385a" />





