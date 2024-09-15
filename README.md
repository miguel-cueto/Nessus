# Nessus Comprehensive Vulnerability Management on Microsoft Azure

## Description
This project provides a step-by-step guide for setting up a Nessus vulnerability management environment, conducting vulnerability scans, and remediating identified vulnerabilities using Microsoft Azure.

## Language and Utilities
- Microsoft Azure
- Windows 10
- Nessus Essentials

## Environments Used
- Host Operating System (Windows)
- Microsoft Azure Virtual Machine
- Nessus Essentials (Vulnerability Scanner)

## Program Walkthrough

### Step 1: Set Up Azure Virtual Machines
### Step 1: Create an Azure Subscription
1. Go to Azure (https://azure.microsoft.com/en-us/free/) and create a new Azure subscription. You will receive $200 worth of free credits for the first month.

<p align="center">
<img src="https://i.imgur.com/1JxWLpJ.png" height="80%" width="80%" alt="Azure"/>
<br />
<br />
  
### Step 2: Create a Virtual Machine
1. In the Azure portal (portal.azure.com), go to the search engine on the top navigate to "Virtual Machines" and click "Create" > click "Azure virtual machine."

<p align="center">
<img src="https://i.imgur.com/X2VZKTV.png" height="80%" width="80%" alt="Azure"/>
<br />
<br />
  
2. Create a new resource group named "Nessuslab"
3. Name the virtual machine "nessus-vm."
4. Select the geographic region "West US 2" and availability zone "zone 3"

<p align="center">
<img src="https://i.imgur.com/UKcpGJA.png" height="80%" width="80%" alt="Nessus 107"/>
<br />
<br />
  
5. Select the image "Windows 10 Pro, version 22H2 - x64 Gen 2."

<p align="center">
<img src="https://i.imgur.com/TtI8Z8A.png" height="80%" width="80%" alt="Nessus 108"/>
<br />
<br />
  
6. Create a username and password for the VM, remember these credentials, and check the box under "Licensing" that reads "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights" before clicking on "Next : Disk >" and "Next : Networking >"

<p align="center">
<img src="https://i.imgur.com/8ekpv7t.png" height="80%" width="80%" alt="Azure"/>
<br />
<br />
  
7. Under "Networking," navigate to the "NIC Network Security Group" and click Advanced

<p align="center">
<img src="https://i.imgur.com/SHIqtV3.png" height="80%" width="80%" alt="Azure"/>
<br />
<br />
  
8. Click on "Create new" under "Configure network security group
" and remove the default inbound security rule and create a new one with the following settings:
  - Source: Any
  - Source port ranges: *
  - Destination: Any
  - Destination port ranges: *
  - Protocol: Any
  - Action: Allow
  - Priority: 100
  - Name: "DANGER_ANY_IN"

<p align="center">
<img src="https://i.imgur.com/fzmFOx1.png" height="80%" width="80%" alt="Azure"/>
<br />
<br />
  
<p align="center">
<img src="https://i.imgur.com/FeXE8ps.png" height="80%" width="80%" alt="Azure"/>
<br />
<br />
    
<p align="center">
<img src="https://i.imgur.com/eVzMkVf.png" height="80%" width="80%" alt="Azure"/>
<br />
<br />
    
<p align="center">
<img src="https://i.imgur.com/DIydrmv.png" height="80%" width="80%" alt="Azure"/>
<br />
<br />

9. Review and create the virtual machine.
    
<p align="center">
<img src="https://i.imgur.com/oT9BVc5.png" height="80%" width="80%" alt="Azure"/>
<br />
<br />
  

3. **Connect to the Virtual Machine**
   - Once the VM is deployed, go to the "Virtual Machines" section in the Azure Portal.
   - Select your VM and click on "Connect" to download the RDP file.
   - Open the RDP file and connect to your VM using the credentials you set up.

### Step 2: Install Deprecated Software
1. **Download and Install Deprecated Software**
   - Connect to your Azure VM using RDP.
   - Download an old version of Firefox (e.g., Firefox 36.0.12) from a trusted source.
   - Install the old Firefox version on the Windows 10 virtual machine.

### Step 3: Download and Install Nessus Essentials
1. **Visit the Nessus Essentials Download Page**
   - Go to Nessus Essentials.
   - Fill out the registration form to receive an activation code via email.

2. **Download and Install Nessus Essentials**
   - Download the appropriate Nessus Essentials installer for Windows.
   - Install Nessus Essentials on your Azure VM using the activation code.

### Step 4: Configure Nessus Essentials
1. **Open the Nessus Essentials Web Interface**
   - Open a web browser on your Azure VM and go to `https://localhost:8834/`.

2. **Create a New Scan**
   - Provide a name for the scan.
   - Enter the IP address of the Windows 10 virtual machine as the target.
   - Optionally, configure additional scan settings.
   - Save the scan configuration.

### Step 5: Perform Vulnerability Scans
1. **Launch the Initial Vulnerability Scan**
   - Run the scan without credentials.
   - Review the scan results and identify vulnerabilities.

2. **Configure Credential-Based Scanning**
   - Provide the username and password for the Windows 10 virtual machine.
   - Launch a new scan with credentials to discover additional vulnerabilities.
   - Compare the scan results with and without credentials.

### Step 6: Remediate Vulnerabilities
1. **Uninstall Deprecated Software**
   - Remove the old version of Firefox from the Windows 10 virtual machine.

2. **Run Windows Updates**
   - Install available security patches and updates on the virtual machine.

3. **Perform Another Vulnerability Scan**
   - Verify the remediation efforts by running another scan.
   - Review the remaining vulnerabilities and take additional remediation steps as necessary.
