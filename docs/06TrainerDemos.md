---
layout: default
title: 'Trainer demonstrations'
nav_order: 6
has_children: false
---

# Trainer demonstrations
{: .no_toc }


## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

<br/>

---

<br/>

## Learning Path 1: Secure Windows Server on-premises and hybrid infrastructures (Windows Server security)

<!-- Demonstrations -->

- **Rearm Windows trial license + Add and set European Portuguese keyboard + Install the Server Core App Compatibility Feature**

    ```powershell
    #Rearm Windows trial license (can be rearmed 5 times).
    slmgr /rearm

    # European Portuguese keyboard.
    Set-WinSystemLocale en-US  
    Set-WinHomeLocation -GeoId 193
    Set-Culture -CultureInfo pt-PT
    Set-TimeZone -Name "GMT Standard Time" ; Get-TimeZone
    Set-WinUserLanguageList -LanguageList pt-PT, en-US -Force; 
    Get-WinUserLanguageList  


    # Server Core App Compatibility Feature.
    Set-Service wuauserv -StartupType Manual
    Start-Service wuauserv
    Add-WindowsCapability -Online -Name ServerCore.AppCompatibility~~~~0.0.1.0
    ```


- **Locate problematic accounts**

    ```powershell
    Import-Module activedirectory

    # Get users with passwords set to never expire
    Get-ADUser -Filter {Enabled -eq $true -and PasswordNeverExpires -eq $true}

    # Get last logon from enabled users
    Get-ADUser -Filter {Enabled -eq $true} -Properties LastLogon | Select Name, @{Name='LastLogon';Expression={[DateTime]::FromFileTime($_.LastLogon)}} 

    # Get users that have not signed in within the last 90 days
    Get-ADUser -Filter {enabled -eq $true} | Where-Object {$_.lastlogondate -lt (Get-Date).Adddays(-(90))} 
    ```


- **DNS server query resolution policies**

    ```powershell
    $s = New-PSSession –ComputerName SEA-DC1.contoso.com

    Enter-PSSession $s

    # Create subnets
    Add-DnsServerClientSubnet -Name "LondonSubnet" -IPv4Subnet "172.16.18.0/24"
    Add-DnsServerClientSubnet -Name "SeattleSubnet" -IPv4Subnet "172.16.10.0/24"

    # Create the DNS server zone scopes
    Add-DnsServerZoneScope -ZoneName "Contoso.com" -Name "LondonZoneScope"
    Add-DnsServerZoneScope -ZoneName "Contoso.com" -Name "SeattleZoneScope"

    # Add host records
    Add-DnsServerResourceRecord -ZoneName "Contoso.com" -A -Name "www" -IPv4Address "172.16.10.41" -ZoneScope "SeattleZoneScope"
    Add-DnsServerResourceRecord -ZoneName "Contoso.com" -A -Name "www" -IPv4Address "172.16.18.17" -ZoneScope "LondonZoneScope"

    # Create the DNS server query resolution policies
    Add-DnsServerQueryResolutionPolicy -Name "LondonPolicy" `
        -Action ALLOW -ClientSubnet "eq,LondonSubnet" -ZoneScope "LondonZoneScope,1" -ZoneName "Contoso.com"

    Add-DnsServerQueryResolutionPolicy -Name "SeattlePolicy" `
        -Action ALLOW -ClientSubnet "eq,SeattleSubnet" -ZoneScope "SeattleZoneScope,1" -ZoneName "Contoso.com"
    ```
<br/>

---

<br/>


## Learning Path 02: Secure Windows Server on-premises and Hybrid Infrastructures (Implementing Security Solutions in Hybrid Scenarios)

<!-- Demonstrations -->


<br/>

---

<br/>


## Learning Path 03: Implementing Windows Server high Availability

<!-- Demonstrations -->

- **Create a Azure virtual machine scale set from PowerShell**
    ```powershell
    New-AzResourceGroup -ResourceGroupName "VMScaleSet-RG" -Location "EastUS"

    New-AzVmss `
    -ResourceGroupName "VMScaleSet-RG" `
    -Location "EastUS" `
    -VMScaleSetName "demoScaleSet" `
    -VirtualNetworkName "scaleSetVnet" `
    -SubnetName "scaleSetSubnet" `
    -PublicIpAddressName "scaleSetPIP" `
    -LoadBalancerName "scaleSetLoadBalancer" `
    -UpgradePolicyMode "Automatic"

    # RunPowerShellScript 
    Add-WindowsFeature Web-Server
    Set-Content -Path "C:\inetpub\wwwroot\Default.htm" -Value "Hello world from host $($env:computername) !"

    # Get Public IP Address
    Get-AzPublicIpAddress -ResourceGroupName "VMScaleSet-RG"  | Select IpAddress
    ```
        
    <br/>

    [Back to top](#top) | [Back to all demos](./README.md)

    <br/>

    ---

    <a id="task2" />

    <br/>

    **Task 2: Delete VMScaleSet-RG**

    ```powershell
    Remove-AzResourceGroup -Name "VMScaleSet-RG" -Force -AsJob
    ```
    ```


- **Implement Storage Replica by using Windows PowerShell**

    ```powershell
    # Add the cluster Scale-Out File Server (SOF) role to the cluster SEA-CLU12.
    Get-Cluster -Name SEA-SLU12 | Add-ClusterScaleOutFileServerRole -Name SOFS01

    # Create SMB Share named VMStorage in SEA-SVR1
    Invoke-Command -ComputerName SEA-SVR1 -ScriptBlock{New-Item -ItemType Directory -Path "C:\ClusterStorage\Volume1\Shares\VMStorage"}

    Invoke-Command -ComputerName SEA-SVR1 -ScriptBlock{New-SMBShare -Name VMStorage -Path "C:\ClusterStorage\Volume1\Shares\VMStorage"}


    # Add additional cluster resource of an IP address to the Scale-Out File Server.
    Get-Cluster -Name SEA-SLU12 | Add-ClusterResource -Name 'SOFS01 IP address' -ResourceType 'IP address' -Group 'SOFS01'

    Get-Cluster -Name SEA-SLU12 | Get-ClusterResource -Name 'SOFS01 IP address' | Set-ClusterParameter `
        -Multiple @{"Address"="172.22.246.205";"SubnetMask"="255.255.240.0";"Network"="Cluster Network 1";"OverrideAddressMatch"=1;"EnableDhcp"=0}


    # Bring the IP address online 
    Get-Cluster -Name SEA-SLU12 | Get-ClusterResource -Name 'SOFS01 IP address' | Start-ClusterResource 
    ```

<br/>

---

<br/>

## Learning Path 04:Implement Disaster Recovery in Windows Server on-premises and Hybrid Environments (Disaster Recovery in Windows Server)


<!-- Demonstrations -->


<br/>

---

<br/>

## Learning Path 05: Implement Disaster Recovery in Windows Server on-premises and Hybrid Environments (Implementing Disaster Recovery Services in Hybrid Scenarios)

<!-- Demonstrations -->


<br/>

---

<br/>


## Learning Path 06: Migrate Servers and Workloads in on-premises and Hybrid Environments (Upgrade and migrate in Windows Server)

<!-- Demonstrations -->


<br/>

---

<br/>


## Learning Path 07: Migrate Servers and Workloads in on-premises and Hybrid Environments (Implementing migration in hybrid scenarios)

<!-- Demonstrations -->


- **Azure Migrate App Containerization**

    [![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Frramoscabral%2FAZ-801---Training---Configuring-Windows-Server-Hybrid-Advanced-Services%2Fmain%2Flabs%2Faspnet_containerization%2Ftemplate.json)



<br/>

---

<br/>

## Learning Path 08: Monitor and Troubleshoot Windows Server Environment (Server and performance monitoring in Windows Server)


<!-- Demonstrations -->


<br/>

---

<br/>



## Learning Path 09: Monitor and troubleshoot Windows Server environment (Implementing operational monitoring in hybrid scenarios)


<!-- Demonstrations -->


- **Create VM in Azure Cloud Shell Bash**

    ```bash
    az group create --name monitor-rg --location westeurope

    az vm create \
        --resource-group monitor-rg\
        --name demoVM \
        --image Win2022AzureEditionCore \
        --size Standard_B2s \
        --public-ip-sku Basic \
        --admin-username microsoft \
        --admin-password Pa55w.rd1234


    az vm run-command invoke -g monitor-rg -n demoVM --command-id RunPowerShellScript --scripts "Install-WindowsFeature -name Web-Server -IncludeManagementTools"

    az vm open-port --port 80 -g monitor-rg --name demoVM
    ```


<br/>

---

<br/>