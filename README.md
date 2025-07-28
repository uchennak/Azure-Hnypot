# Azure-Hnypot

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/e91f03c7-28fc-4c99-981c-e6b15bd409e2" />

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
