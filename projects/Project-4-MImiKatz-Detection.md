
Project 4: Mimikatz / LSASS Dump Detection using Sysmon
​Overview
The purpose of this project is to understand how attackers perform credential dumping (specifically from lsass.exe) in a Windows environment, and how we as Blue Team / SOC Analysts detect this malicious activity using endpoint telemetry (Sysmon).

Lab Environment
Virtualization: Oracle VirtualBox
Operating System: Windows 10 Virtual Machine
Telemetry Tool: Microsoft Sysmon (System Monitor) v15.22
Implementation Steps
​Step 1: Sysmon Installation & Verification
​Installing Microsoft Sysmon on a Windows 10 virtual machine with default/custom configuration via PowerShell (Administrator mode):

​Sysmon service has started successfully and started monitoring background processes.
​Verified via Event Viewer that Sysmon Operational logs (Microsoft-Windows-Sysmon/Operational) are being generated properly.
​Step 2: Credential Dumping Simulation (Attack Emulation)
​Safe simulations were performed in the lab to target LSASS memory like real-world attackers:

Opened Windows Task Manager and right-clicked on the lsass.exe process in the Details tab.
The "Create dump file" option was selected, causing Windows to generate an lsass.dmp file in the target directory. This action emulated the exact same memory access pattern that tools like Mimikatz use.
​Step 3: Telemetry & Detection Analysis
​Sysmon captured the process memory read/access activity.
Sysmon Event ID 10 (ProcessAccess) records which process (source) attempted to access or dump the memory of a sensitive system process (lsass.exe).
Key Learnings & SOC Value
Endpoint Visibility: These details are not available in standard Windows event logs, but visibility of deep-level process interactions (such as ProcessAccess) is available through Sysmon.
Credential Theft Awareness: Understood how attackers target LSASS memory and how SOC analysts should set up SIEM alerts (such as Wazuh / Splunk rules) against it.
