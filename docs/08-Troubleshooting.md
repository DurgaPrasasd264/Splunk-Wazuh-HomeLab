# Troubleshooting

## Overview

This document lists common issues encountered while building the Splunk-Wazuh Home Lab and the steps taken to resolve them.

---

# 1. Wazuh Agent Offline

## Problem

The Windows 11 agent was not visible in the Wazuh Dashboard.

### Possible Causes

- Incorrect Manager IP address
- Wazuh Agent service stopped
- Firewall blocking port **1514/TCP**
- Incorrect registration

### Verification

Open PowerShell:

```powershell
Get-Service WazuhSvc
```

Check the configuration:

```powershell
Get-Content "C:\Program Files (x86)\ossec-agent\ossec.conf"
```

On Ubuntu:

```bash
sudo systemctl status wazuh-manager
```

### Solution

- Verify the Manager IP address.
- Restart the Wazuh Agent service.
- Restart the Wazuh Manager.
- Confirm network connectivity between the Windows endpoint and Ubuntu server.

---

# 2. Splunk Not Receiving Logs

## Problem

Windows Event Logs were not appearing in Splunk Search.

### Verification

Check the Universal Forwarder service:

```powershell
Get-Service SplunkForwarder
```

View the configuration:

```powershell
Get-Content "C:\Program Files\SplunkUniversalForwarder\etc\system\local\inputs.conf"
```

```powershell
Get-Content "C:\Program Files\SplunkUniversalForwarder\etc\system\local\outputs.conf"
```

Search in Splunk:

```spl
index=windows
```

### Solution

- Verify `inputs.conf`.
- Verify `outputs.conf`.
- Restart the Splunk Universal Forwarder.
- Confirm that port **9997** is open.

---

# 3. Splunk Web Interface Not Accessible

## Verification

```bash
sudo /opt/splunk/bin/splunk status
```

Restart Splunk:

```bash
sudo /opt/splunk/bin/splunk restart
```

### Solution

- Ensure Splunk is running.
- Verify port **8000** is accessible.
- Check firewall settings.

---

# 4. Wazuh Dashboard Not Accessible

## Verification

```bash
sudo systemctl status wazuh-dashboard
```

```bash
sudo systemctl status wazuh-indexer
```

### Solution

- Restart dashboard service.
- Restart indexer.
- Verify HTTPS access.

---

# 5. Windows Event Logs Missing

## Verification

Open Event Viewer:

```
Windows Logs
```

Search in Splunk:

```spl
index=windows
```

### Solution

- Confirm Event Logs exist.
- Verify Universal Forwarder configuration.
- Restart the forwarder.

---

# Lessons from Troubleshooting

- Always verify service status first.
- Check configuration files before reinstalling software.
- Validate network connectivity.
- Use logs for troubleshooting instead of guessing.
