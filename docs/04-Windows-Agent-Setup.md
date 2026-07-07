# Windows Agent Setup

## Objective

Configure a Windows 11 endpoint to send security logs to both Splunk Enterprise Security and Wazuh Manager.

---

## Lab Environment

| Component | Version |
|----------|---------|
| Operating System | Windows 11 |
| Wazuh Agent | 4.x |
| Splunk Universal Forwarder | 9.x |

---

# Architecture

```
Windows 11
│
├── Wazuh Agent ------------------------> Wazuh Manager
│
└── Splunk Universal Forwarder ---------> Splunk Enterprise
```

---

# Step 1: Install Wazuh Agent

1. Download the Wazuh Agent for Windows.
2. Run the installer as Administrator.
3. Enter the Wazuh Manager IP address.
4. Complete the installation.

---

# Step 2: Verify Wazuh Service

Open **PowerShell** as Administrator.

```powershell
Get-Service WazuhSvc
```

Expected Output

```
Status   Name        DisplayName
------   ----        -----------
Running  WazuhSvc    Wazuh Agent
```

---

# Step 3: Verify Wazuh Configuration

```powershell
Get-Content "C:\Program Files (x86)\ossec-agent\ossec.conf"
```

Important Configuration

```xml
<server>
    <address><WAZUH_MANAGER_IP></address>
    <port>1514</port>
    <protocol>tcp</protocol>
</server>
```

---

# Step 4: Verify Agent Connection

Open the Wazuh Dashboard.

Navigate to:

```
Endpoints → Agents
```

Confirm:

- Agent Status: Active
- Operating System: Windows 11
- Last Keep Alive: Recent

---

# Screenshots

- Windows Agent Installation
- Wazuh Agent Service
- Wazuh Dashboard
- Connected Agent

---

# Outcome

Successfully connected the Windows 11 endpoint to the Wazuh Manager for centralized log collection and security monitoring.
