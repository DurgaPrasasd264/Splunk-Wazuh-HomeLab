# Splunk Universal Forwarder Configuration

## Objective

Configure the Splunk Universal Forwarder on Windows 11 to collect Windows Event Logs and forward them to Splunk Enterprise.

---

## Lab Environment

| Component | Version |
|----------|---------|
| Windows 11 | Client |
| Splunk Universal Forwarder | 9.x |
| Splunk Enterprise | Ubuntu 22.04 |

---

# Step 1: Install Splunk Universal Forwarder

1. Download the Universal Forwarder.
2. Run the installer as Administrator.
3. Enter the Splunk server IP address.
4. Complete the installation.

---

# Step 2: Configure inputs.conf

Location

```
C:\Program Files\SplunkUniversalForwarder\etc\system\local\inputs.conf
```

Configuration

```ini
[WinEventLog://Security]
disabled = 0
index = windows

[WinEventLog://System]
disabled = 0
index = windows

[WinEventLog://Application]
disabled = 0
index = windows
```

---

# Step 3: Configure outputs.conf

Location

```
C:\Program Files\SplunkUniversalForwarder\etc\system\local\outputs.conf
```

Configuration

```ini
[tcpout]
defaultGroup = default-autolb-group

[tcpout:default-autolb-group]
server = <SPLUNK_SERVER_IP>:9997

[tcpout-server://<SPLUNK_SERVER_IP>:9997]
```

---

# Step 4: Restart Splunk Forwarder

Open PowerShell as Administrator.

```powershell
Restart-Service SplunkForwarder
```

---

# Step 5: Verify Service

```powershell
Get-Service SplunkForwarder
```

Expected Output

```
Status   Name
------   ----
Running  SplunkForwarder
```

---

# Step 6: Verify Configuration

Display inputs.conf

```powershell
Get-Content "C:\Program Files\SplunkUniversalForwarder\etc\system\local\inputs.conf"
```

Display outputs.conf

```powershell
Get-Content "C:\Program Files\SplunkUniversalForwarder\etc\system\local\outputs.conf"
```

---

# Step 7: Verify Log Collection

Open Splunk Search & Reporting.

Run:

```spl
index=windows
```

Verify that Windows Security, System, and Application logs are being indexed.

---

# Screenshots

- Universal Forwarder Installation
- inputs.conf
- outputs.conf
- Splunk Search
- Indexed Windows Logs

---

# Outcome

Successfully configured the Splunk Universal Forwarder to collect Windows Event Logs and forward them to Splunk Enterprise for analysis.
