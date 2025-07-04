# Post-Reimage System Validation and Update Script

This PowerShell script automates essential system checks and updates after a computer has been reimaged. It’s tailored for enterprise environments and ensures that endpoint security, policy enforcement, application verification, and OEM-specific update processes are validated immediately post-deployment.

## 🔍 Features

- 📌 **System Information Collection**  
  - Manufacturer
  - Computer name
  - IP and MAC address
  - Windows Edition, Version, and Build

- ⚙️ **Group Policy Update Validation**
  - Executes `gpupdate /force` and validates success

- 🛡️ **Trellix (formerly McAfee) Agent Operations**
  - Checks agent status and enforces policies
  - Sends events to ePO
  - Executes virus definition update

- 📦 **Application Installation Check**
  - Verifies presence of essential software:
    - Trellix, Chrome, Edge, Office, Outlook, Citrix, Microsoft Teams
  - Logs installed versions or missing status

- 🧩 **MHS Genesis Validation**
  - Verifies the presence and version of Citrix SelfService (used for MHS Genesis)

- 🖥️ **OEM-Specific Checks and Updates**
  - **Dell**: Runs Dell Command Update (CLI) to scan and apply driver/BIOS updates with logging
  - **HP**: Extracts and displays BIOS version and release date

## 📁 Log Output

For Dell systems, scan and update logs are saved to a `DCUpdate` folder on the desktop:
- `scanlog.log`
- `dellcuoutput.log`

## 🧑‍💻 Use Case

Ideal for IT departments, help desk teams, and systems administrators who:
- Reimage systems regularly
- Need to validate endpoint compliance
- Require consistent post-deployment configuration

## 🚨 Requirements

- PowerShell 5.1+
- Admin privileges
- OEM-specific tools (e.g., Dell Command Update, Trellix Agent)
- Network access to Active Directory and McAfee ePO (if integrated)

## 🚀 Execution

Run in an elevated PowerShell session post-imaging:
```powershell
.\PostReimageValidation.ps1
