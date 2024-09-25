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
4. Select the geographic region "East US 2" and availability zone "zone 3"

<p align="center">
<img src="https://i.imgur.com/fDIgQo0.png" height="80%" width="80%" alt="Nessus 107"/>
<br />
<br />
  
5. Select the image "Windows 10 Pro, version 22H2 - x64 Gen 2."

<p align="center">
<img src="https://i.imgur.com/2YwvcQT.png" height="80%" width="80%" alt="Nessus 108"/>
<br />
<br />
  
6. Create a username and password for the VM, remember these credentials, and check the box under "Licensing" that reads "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights" before clicking on "Next : Disk >" and "Next : Networking >"

<p align="center">
<img src="https://i.imgur.com/8ekpv7t.png" height="80%" width="80%" alt="Azure"/>
<br />
<br />
  
7. Under "Networking," navigate to the "NIC Network Security Group" and click Advanced

<p align="center">
<img src="https://i.imgur.com/MITIpHB.png" height="80%" width="80%" alt="Nessus 135"/>
<br />
<br />
  
8. Click on "Create new" under "Configure network security group
" and remove the default inbound security rule and create a new one with the following settings:
  - Source: Any
  - Source port ranges: *
  - Destination: Any
  - Service: Custom
  - Destination port ranges: *
  - Protocol: Any
  - Action: Allow
  - Priority: 100
  - Name: "DANGER_ANY_IN"

<p align="center">
<img src="https://i.imgur.com/zsSDKDL.png" height="80%" width="80%" alt="Nessus 136"/>
<br />
<br />
  
<p align="center">
<img src="https://i.imgur.com/BmeN3ap.png" height="80%" width="80%" alt="Nessus 137"/>
<br />
<br />
  
<p align="center">
<img src="https://i.imgur.com/TUJepoa.png" height="80%" width="80%" alt="Nessus 138"/>
<br />
<br />
    
<p align="center">
<img src="https://i.imgur.com/4lxO61N.png" height="80%" width="80%" alt="Nessus 139"/>
<br />
<br />
  
9. Review and create the virtual machine.
    
<p align="center">
<img src="https://i.imgur.com/oT9BVc5.png" height="80%" width="80%" alt="Nessus 110"/>
<br />
<br />
  

10. **Connect to the Virtual Machine**
   - Once the VM is deployed, go to the "Virtual Machines" section in the Azure Portal.
   - Select your VM and click on "Connect" to download the RDP file.

<p align="center">
<img src="https://i.imgur.com/rnCZwTX.png" height="80%" width="80%" alt="Nessus 112"/>
<br />
<br />
  
   - Open the RDP file and connect to your VM using the credentials you set up > Click "Yes" on the certificate windows
  
<p align="center">
<img src="https://i.imgur.com/198Pep3.png" height="80%" width="80%" alt="Nessus 113"/>
<br />
<br />
    
<p align="center">
<img src="https://i.imgur.com/2ZaPBsm.png" height="80%" width="80%" alt="Nessus 114"/>
<br />
<br />
    
<p align="center">
<img src="https://i.imgur.com/RGd7vhY.png" height="80%" width="80%" alt="Nessus 115"/>
<br />
<br />
    
<p align="center">
<img src="https://i.imgur.com/BXwwFxZ.png" height="80%" width="80%" alt="Nessus 116"/>
<br />
<br />
11. In the VM set up toggle "no" on all privacy settings, press "yes" for networks, and start Microsoft Edge without your data

<p align="center">
<img src="https://i.imgur.com/zeNA3i1.png" height="80%" width="80%" alt="Nessus 117"/>
<br />
<br />
  
<p align="center">
<img src="https://i.imgur.com/227nHv5.png" height="80%" width="80%" alt="Nessus 118"/>
<br />
<br />
  
<p align="center">
<img src="https://i.imgur.com/xmDjaMI.png" height="80%" width="80%" alt="Nessus 119"/>
<br />
<br />
  
12. Open the Windows Defender Firewall (wf.msc) in the VM > click Windows Defender Firewall Properties and turn off the firewall for all profiles (Domain, Private, and Public).
  
<p align="center">
<img src="https://i.imgur.com/NC1dObE.png" height="80%" width="80%" alt="Nessus 171"/>
<br />
<br />
    
<p align="center">
<img src="https://i.imgur.com/bJkJicN.png" height="80%" width="80%" alt="Nessus 112"/>
<br />
<br />
  
13. From your local machine, ping the virtual machine's IP address to ensure it is accepting ICMP echo requests.

### Step 2: Download and Install Nessus Essentials
1. **Visit the Nessus Essentials Download Page**
   - Go to Nessus Essentials. (https://www.tenable.com/products/nessus/nessus-essentials)  

<p align="center">
<img src="https://i.imgur.com/hXiP7Qu.png" height="80%" width="80%" alt="Nessus 121"/>
<br />
<br />
    
   - Fill out the registration form to receive an activation code via email.

<p align="center">
<img src="https://i.imgur.com/24AyvoV.png" height="80%" width="80%" alt="Nessus 122"/>
<br />
<br />
  
2. **Download and Install Nessus Essentials**
   - Click "View Downloads" for "Tenable Nessus" then click on "Download"  

<p align="center">
<img src="https://i.imgur.com/oIiy8Ju.png" height="80%" width="80%" alt="Nessus 124"/>
<br />
<br />
    
<p align="center">
<img src="https://i.imgur.com/pK41IKA.png" height="80%" width="80%" alt="Nessus 125"/>
<br />
<br />
    
   - Install Nessus Essentials by clicking on "Connect via SSL" > continue to localhost (unsafe) > Continue > click on "Register for Nessus Essentials" then continue > skip and apply your activation code.
    
<p align="center">
<img src="https://i.imgur.com/RPQhNuI.png" height="80%" width="80%" alt="Nessus 126"/>
<br />
<br />
        
<p align="center">
<img src="https://i.imgur.com/nNJ0sPd.png" height="80%" width="80%" alt="Nessus 127"/>
<br />
<br />
        
<p align="center">
<img src="https://i.imgur.com/KGbhgmQ.png" height="80%" width="80%" alt="Nessus 128"/>
<br />
<br />
        
<p align="center">
<img src="https://i.imgur.com/kL5KqCd.png" height="80%" width="80%" alt="Nessus 129"/>
<br />
<br />
          
<p align="center">
<img src="https://i.imgur.com/bIFjH0M.png" height="80%" width="80%" alt="Nessus 130"/>
<br />
<br />
      
### Step 3: Configure Nessus Essentials
1. **Open the Nessus Essentials Web Interface**
   - Open a web browser on your Azure VM and go to `https://localhost:8834/`.
          
<p align="center">
<img src="https://i.imgur.com/F5cNqxq.png" height="80%" width="80%" alt="Nessus 131"/>
<br />
<br />
      
2. **Create a New Scan**
   - Provide a name "Windows 10 Single Host" for the scan.          

<p align="center">
<img src="https://i.imgur.com/3sQdY94.png" height="80%" width="80%" alt="Nessus 132"/>
<br />
<br />

   - In the Azure search tool search "Virtual Machine" > click on "nessuslab-vm" > copy the public IP address and paste it on "Targets" section of Nessus Essentials.                

<p align="center">
<img src="https://i.imgur.com/aDuXqtA.png" height="80%" width="80%" alt="Nessus 134"/>
<br />
<br />
                      
<p align="center">
<img src="https://i.imgur.com/0pVYBqe.png" height="80%" width="80%" alt="Nessus 144"/>
<br />
<br />
                         
<p align="center">
<img src="https://i.imgur.com/eoT9Tf1.png" height="80%" width="80%" alt="Nessus 145"/>
<br />
<br />
         
   - Save the scan configuration.
    
### Step 4: Perform Vulnerability Scans
1. **Launch the Initial Vulnerability Scan**
   - Run the scan without credentials by clicking the play button (launch) on "Windows 10 Single Host"                           
                           
<p align="center">
<img src="https://i.imgur.com/kW7Qn3M.png" height="80%" width="80%" alt="Nessus 146"/>
<br />
<br />
       
   - Review the scan results and identify vulnerabilities.

<p align="center">
<img src="https://i.imgur.com/9zFCHdV.png" height="80%" width="80%" alt="Nessus 147"/>
<br />
<br />
                                      
<p align="center">
<img src="https://i.imgur.com/ihrlUfY.png" height="80%" width="80%" alt="Nessus 148"/>
<br />
<br />
           
2. **Configure Credential-Based Scanning**
   - Provide the username and password for the Windows 10 virtual machine.                                      

<p align="center">
<img src="https://i.imgur.com/BvEeEnu.png" height="80%" width="80%" alt="Nessus 149"/>
<br />
<br />
                                                
<p align="center">
<img src="https://i.imgur.com/6RJksGP.png" height="80%" width="80%" alt="Nessus 150"/>
<br />
<br />
                                                
<p align="center">
<img src="https://i.imgur.com/WxjZJY6.png" height="80%" width="80%" alt="Nessus 151"/>
<br />
<br />
                                                
<p align="center">
<img src="https://i.imgur.com/lVbL7cH.png" height="80%" width="80%" alt="Nessus 152"/>
<br />
<br />
          
   - Launch a new scan with credentials to discover additional vulnerabilities.                                      

<p align="center">
<img src="https://i.imgur.com/3R8fMA0.png" height="80%" width="80%" alt="Nessus 153"/>
<br />
<br />
          
   - Compare the scan results with and without credentials.                                      

<p align="center">
<img src="https://i.imgur.com/ns2Kn6T.png" height="80%" width="80%" alt="Nessus 193"/>
<br />
<br />
                                                
<p align="center">
<img src="https://i.imgur.com/ihrlUfY.png" height="80%" width="80%" alt="Nessus 148"/>
<br />
<br />
          

### Step 5: Remediate Vulnerabilities
1. **Run Windows Updates**
   - Install available security patches and updates on the virtual machine.

<p align="center">
<img src="https://i.imgur.com/h3kt9fO.png" height="80%" width="80%" alt="Nessus 190"/>
<br />
<br />
                                                
<p align="center">
<img src="https://i.imgur.com/D3HvY37.png" height="80%" width="80%" alt="Nessus 191"/>
<br />
<br />
          
<p align="center">
<img src="https://i.imgur.com/MaFDuZr.png" height="80%" width="80%" alt="Nessus 192"/>
<br />
<br />
    
2. **Perform Another Vulnerability Scan**
   - Verify the remediation efforts by running another scan.          

<p align="center">
<img src="https://i.imgur.com/KL1wvma.png" height="80%" width="80%" alt="Nessus 154"/>
<br />
<br />
    
   - Review the remaining vulnerabilities and take additional remediation steps as necessary.
