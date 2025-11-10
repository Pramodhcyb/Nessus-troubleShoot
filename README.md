# Nessus Credentialed Scan Troubleshoot Automation

This repository contains a PowerShell script to help troubleshoot credentialed scan failures for Nessus on Windows VMs (e.g., in Azure).  
Based on the article by Pramodh Cyb: [How I Solved Nessus Credentialed Scan Failures on Azure VMs Using PowerShell Automation](https://medium.com/@pramodh.cyb/how-i-solved-nessus-credentialed-scan-failures-on-azure-vms-using-powershell-automation-306ce8dffb58)  

## Script: `scripts/check-nessus-windows.ps1`

This script (run as Administrator on the target VM) performs the following checks:
- Required services (`RemoteRegistry`, `WinRM`, `WMI`)
- WinRM connectivity (`Test-WsMan`)
- Local Administrator rights
- WMI query access
- Hotfix enumeration (`Get-HotFix`)
- PowerShell Execution Policy

## Usage

1. Copy the script to the target Windows VM.  
2. Launch PowerShell **as Administrator**.  
3. Run: `.\check-nessus-windows.ps1`  
4. Review the output.  
5. Remediate any items flagged in red or yellow.

## Important Notes

- Intended for lab or authorised environments.  
- Changing services, execution policy or permissions may have security implications.  
- For production usage, ensure proper governance and least-privilege model.



