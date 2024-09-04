---
layout: default
title: 'Trainer References'
nav_order: 7
has_children: false
---

# Trainer References
{: .no_toc }


## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

<br/>

---

<br/>

## Learning Path 1: Secure Windows Server on-premises and hybrid infrastructures (Windows Server security)


| Lessons | Notes |
| --- | ---
| Secure Windows Server user accounts | - [Credential Guard overview](https://learn.microsoft.com/en-us/windows/security/identity-protection/credential-guard/) | 
| Hardening Windows Server | - [Windows LAPS overview](https://learn.microsoft.com/en-us/windows-server/identity/laps/laps-overview) <br> - [New tool: Policy Analyzer](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/new-tool-policy-analyzer/ba-p/701049) <br> - [Microsoft Security Compliance Toolkit - How to use](https://learn.microsoft.com/en-us/windows/security/operating-system-security/device-management/windows-security-configuration-framework/security-compliance-toolkit-10) <br> - [Download Microsoft Security Compliance Toolkit 1.0](https://www.microsoft.com/en-us/download/details.aspx?id=55319) |
| Secure Windows Server DNS | - [DNNSEC](https://www.pt.pt/en/security/dnssec/) <br> - [BIND DNSSEC Guide + Scripts + Tools + RFCs from DNS.pt](hhttps://www.pt.pt/en/dnssec/tools/) <br> - [Webcheck: Check the security of your domaino](https://webcheck.pt/en/) |



<br/>

## Learning Path 2: Secure Windows Server on-premises and Hybrid Infrastructures (Implementing Security Solutions in Hybrid Scenarios)


| Lessons | Notes |
| --- | --- |
| Implement Windows Server IaaS VM network security | - [Azure network security groups overview](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview) <br> - [What is Azure Firewall?](https://learn.microsoft.com/en-us/azure/firewall/overview) <br> - [Microsoft Network Monitor 3.4 (archive)](https://www.microsoft.com/en-us/download/details.aspx?id=4865) |
| Manage Azure VM updates | - [Azure Update Manager overview](https://learn.microsoft.com/en-us/azure/update-manager/overview) |
| Create and implement application allowlists with adaptive application control | - [Understand adaptive application controls](https://learn.microsoft.com/en-us/azure/defender-for-cloud/adaptive-application-controls) |
| Audit the security of Windows Server IaaS virtual machines | - [What is Microsoft Sentinel?](https://learn.microsoft.com/en-us/azure/sentinel/overview?tabs=azure-portal) <br> - [MITRE ATT&CK](https://attack.mitre.org/) |
| Configure BitLocker disk encryption for Windows IaaS Virtual Machines | - [BitLocker overview](https://learn.microsoft.com/en-us/windows/security/operating-system-security/data-protection/bitlocker/) <br> - [Overview of managed disk encryption options](https://learn.microsoft.com/en-us/azure/virtual-machines/disk-encryption-overview) <br> - [Find your BitLocker recovery key for home users](https://support.microsoft.com/en-us/windows/find-your-bitlocker-recovery-key-6b71ad27-0b89-ea08-f143-056f5ab347d6) |
| Implement change tracking and file integrity monitoring for Windows IaaS VMs | - [Announcing public preview: Azure Change Tracking & Inventory using Azure Monitor agent (AMA)](https://techcommunity.microsoft.com/t5/azure-governance-and-management/announcing-public-preview-azure-change-tracking-amp-inventory/ba-p/3713308) <br> - [Azure Monitor Agent overview](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-overview) |

<br>

| Lab| Resource |
| --- | --- |
| Lab 02: Implementing Security Solutions in Hybrid Scenarios | - Log Analytics Windows Agent (64 bit): ``https://go.microsoft.com/fwlink/?LinkId=828603`` <br> - Log Analytics Windows Agent (32 bit): ``https://go.microsoft.com/fwlink/?LinkId=828604`` <br> - Log Analytics Linux Agent: ``https://go.microsoft.com/fwlink/?LinkId=692028`` <br> - Download and onboard agent for Linux: ``wget https://raw.githubusercontent.com/Microsoft/OMS-Agent-for-Linux/master/installer/scripts/onboard_agent.sh && sh onboard_agent.sh -w 3bd6999e-7f72-476b-9c42-73b11d8081b9 -s e/89OyCsoJm1Ox756oailfMDvQCjTzvu5Dx2Jaf39hR1CSMFznqNn7ouh2f65m0dVBlrhrfl5hDZOTif25pjTg== -d opinsights.azure.com`` |


> Note: The legacy **Log Analytics agent  will be deprecated by August 2024**. After this date, Microsoft will no longer provide any support for the Log Analytics agent. Migrate to **Azure Monitor agent** before August 2024 to continue ingesting data.


<br/>

## Learning Path 3: Implementing Windows Server high Availability


| Lessons | Notes |
| --- | --- |
| Introduction to Cluster Shared Volumes | [Cluster Shared Volumes (CSV): Disk Ownership](https://techcommunity.microsoft.com/t5/failover-clustering/cluster-shared-volumes-csv-disk-ownership/ba-p/371352)


<br/>


## Learning Path 4: Implement Disaster Recovery in Windows Server on-premises and Hybrid Environments (Disaster Recovery in Windows Server)

| Lessons | Notes |
| --- | ---
| Implement Hyper-V Replica | [Resilient File System (ReFS) overview](https://learn.microsoft.com/en-us/windows-server/storage/refs/refs-overview) |
| Protect your on-premises infrastructure from disasters with Azure Site Recovery | 


<br/>

## Learning Path 5: Implement Disaster Recovery in Windows Server on-premises and Hybrid Environments (Implementing Disaster Recovery Services in Hybrid Scenarios)


| Lessons | Notes |
| --- | ---
| Protect your Azure infrastructure with Azure Site Recovery | - [About networking in Azure VM disaster recovery](https://learn.microsoft.com/en-us/azure/site-recovery/azure-to-azure-about-networking) | 
| Protect your virtual machines by using Azure Backup | - [Tutorial: Cable and connect to your Azure Data Box](https://learn.microsoft.com/en-us/azure/databox/data-box-deploy-set-up) - <br>  [Tutorial: Cable and connect to your Azure Data Box Heavy](https://learn.microsoft.com/en-us/azure/databox/data-box-heavy-deploy-set-up) |
| Protect your virtual machines by using Azure Backup | - [Azure subscription and service limits, quotas, and constraints](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/azure-subscription-service-limits) | 



<br/>

## Learning Path 6: Migrate Servers and Workloads in on-premises and Hybrid Environments (Upgrade and migrate in Windows Server)



| Lessons | Notes |
| --- | ---
| Active Directory Domain Services migration | - [Upgrade domain controllers to a newer version of Windows Server](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/deploy/upgrade-domain-controllers) <br> - [Support policy and known issues for Active Directory Migration Tool](https://learn.microsoft.com/en-us/troubleshoot/windows-server/active-directory/support-policy-and-known-issues-for-admt) |



<br/>

## Learning Path 7: Migrate Servers and Workloads in on-premises and Hybrid Environments (Implementing migration in hybrid scenarios)


| Lessons | Notes |
| --- | ---
| Migrate on-premises Windows Server Instances to Azure IaaS Virtual Machines| - [Azure Data Box](https://azure.microsoft.com/en-us/products/databox) |


<br/>

## Learning Path 8: Monitor and Troubleshoot Windows Server Environment (Server and performance monitoring in Windows Server)


| Lessons | Notes |
| --- | ---
| Monitor Windows Server performance  | [Snap-ins](./071snap_ins.md) |




<br/>

## Learning Path 9: Monitor and troubleshoot Windows Server environment (Implementing operational monitoring in hybrid scenarios)


| Lessons | Notes |
| --- | ---
| Monitor your Azure virtual machines with Azure Monitor | - [Kusto Query Language (KQL) overview](https://learn.microsoft.com/en-us/kusto/query/) <br> - [Azure Data Explorer Samples](https://dataexplorer.azure.com/clusters/help/databases/Samples) |



<br/>
