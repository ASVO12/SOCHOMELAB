# SOCHOMELAB - Detection and Response


Home lab simulating a small SOC environment for practicing alert triage and detection engineering.

## Environment
- **Domain Controller**: Windows Server 2022 (DC2) – `lab.local`
- **Workstation**: Windows 11 Enterprise (Workstation1) – domain joined
- **SIEM**: Wazuh 4.14 on Ubuntu
- **Endpoint Telemetry**: Sysmon (SwiftOnSecurity config)


## What I Did
1. Built a domain and joined a workstation.
2. Deployed Wazuh and enrolled both Windows agents.
3. Installed and configured Sysmon for process, network, and file telemetry.
4. Executed Atomic Red Team test **T1059.001** (PowerShell).
5. Confirmed the activity generated Sysmon Event ID 1 (Process Create) alerts visible in Wazuh.

## Detection Evidence
- Atomic test launched PowerShell processes.
- Sysmon captured the process creation events.
- Events appeared in Wazuh Discover under `sysmon AND agent.name:Workstation1`.

## MITRE ATT&CK
- **T1059.001** – Command and Scripting Interpreter: PowerShell

## Screenshots
<img width="1140" height="397" alt="5978374e93a16a63d86f0f2c2eca579c" src="https://github.com/user-attachments/assets/57fd2c41-33b5-49f5-a67b-20f1e7dccf72" />
<img width="1455" height="933" alt="222d52d8885f3130b371677ead69a2a9" src="https://github.com/user-attachments/assets/b42a9ea3-f868-40e8-8cb1-1c3c113cc0bb" />
<img width="1008" height="658" alt="cf9c816b5575d63bb0a67ed2e2c7bc41" src="https://github.com/user-attachments/assets/9b213cc0-f7b1-4149-bc06-f68a6d71903e" />
<img width="1917" height="1025" alt="af51ca047c49b9c387dc72628330a53e" src="https://github.com/user-attachments/assets/4253ae54-21ff-4800-99fd-c97ac8fc8db5" />

## Skills Demonstrated
- SIEM deployment and agent management
- Endpoint logging (Sysmon)
- Attack simulation with Atomic Red Team
- Basic alert triage and MITRE mapping




