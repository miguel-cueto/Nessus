# Nessus Comprehensive Vulnerability Management

## Description
This project provides a step-by-step guide for setting up a Nessus vulnerability management environment, conducting vulnerability scans, and remediating identified vulnerabilities. The lab involves installing VMware Workstation Player, creating a Windows 10 virtual machine, installing deprecated software, and using Nessus Essentials to perform vulnerability scans.

## Language and Utilities
- VMware Workstation Player
- Windows 10 ISO
- Nessus Essentials

## Environments Used
- Host Operating System (Windows, macOS, or Linux)
- VMware Workstation Player
- Windows 10 Virtual Machine
- Nessus Essentials (Vulnerability Scanner)

## Program Walkthrough

### Step 1: Install VMware Workstation Player
1. Download VMware Workstation Player from the official website: [https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html](https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html)
2. Follow the installation instructions provided by VMware.

### Step 2: Download Windows 10 ISO
1. Visit the Microsoft Software Download website: [https://www.microsoft.com/en-us/software-download/windows10](https://www.microsoft.com/en-us/software-download/windows10)
2. Click on "Download tool now" under "Create Windows 10 installation media."
3. Run the downloaded tool and select "Create installation media (USB flash drive, DVD, or ISO file) for another PC."
4. Choose the appropriate language, edition, and architecture for Windows 10.
5. Select "ISO file" as the media option and specify a location to save the ISO file.

### Step 3: Create a Windows 10 Virtual Machine
1. Open VMware Workstation Player and click on "Create a New Virtual Machine."
2. Select "I will install the operating system later" and click "Next."
3. Choose the appropriate operating system (e.g., Microsoft Windows) and version (e.g., Windows 10 x64).
4. Specify a name and location for the virtual machine.
5. Configure the virtual machine settings as desired (e.g., allocated RAM, disk size).
6. Click "Finish" to create the virtual machine.
7. Power on the virtual machine and follow the on-screen instructions to install Windows 10 from the downloaded ISO file.

### Step 4: Install Deprecated Software
1. Download an old version of Firefox (e.g., Firefox 36.0.12) from a trusted source.
2. Install the old Firefox version on the Windows 10 virtual machine.

### Step 5: Download and Install Nessus Essentials
1. Visit the Nessus Essentials download page: [https://www.tenable.com/products/nessus/nessus-essentials](https https://www.tenable.com/products/nessus/nessus-essentials)
2. Fill out the registration form and submit it to receive an activation code via email.
3. Download the appropriate Nessus Essentials installer for your host operating system.
4. Install Nessus Essentials using the provided activation code.

### Step 6: Configure Nessus Essentials
1. Open the Nessus Essentials web interface (e.g., `https://localhost:8834/`).
2. Create a new scan by providing a name and the IP address of the Windows 10 virtual machine as the target.
3. Optionally, configure additional scan settings as desired.
4. Save the scan configuration.

### Step 7: Perform Vulnerability Scans
1. Launch the initial vulnerability scan without credentials.
2. Review the scan results and vulnerabilities identified.
3. Configure credential-based scanning by providing the username and password for the Windows 10 virtual machine.
4. Launch a new scan with credentials to discover additional vulnerabilities.
5. Compare the scan results with and without credentials.

### Step 8: Remediate Vulnerabilities
1. Uninstall the deprecated Firefox version from the Windows 10 virtual machine.
2. Run Windows Updates on the virtual machine to install available security patches and updates.
3. Perform another vulnerability scan to verify the remediation efforts.
4. Review the remaining vulnerabilities and consider additional remediation steps as necessary.
