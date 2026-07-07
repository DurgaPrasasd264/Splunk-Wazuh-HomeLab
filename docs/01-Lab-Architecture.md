# Lab Architecture

## Overview

This project demonstrates a SOC Home Lab built using Splunk Enterprise Security and Wazuh for centralized log collection, monitoring, and security analysis.

The environment consists of one Ubuntu virtual machine hosting Splunk Enterprise Security and Wazuh Manager, and one Windows 11 machine acting as the endpoint.

---

## Components

| Component | Purpose |
|----------|---------|
| Ubuntu 22.04 | Hosts Splunk Enterprise Security and Wazuh Manager |
| Windows 11 | Endpoint generating Windows Event Logs |
| Splunk Universal Forwarder | Sends Windows logs to Splunk |
| Wazuh Agent | Sends security events to Wazuh |
| Splunk Enterprise Security | Log analysis and security monitoring |
| Wazuh Manager | Endpoint monitoring and threat detection |

---

## Architecture Diagram

> Add `architecture.png` here after creating the diagram.

---

## Log Flow

1. Windows 11 generates Security, System, and Application logs.
2. Splunk Universal Forwarder sends logs to Splunk Enterprise.
3. Wazuh Agent sends security events to Wazuh Manager.
4. Splunk indexes the collected logs.
5. Wazuh analyzes logs using decoders and rules.
6. Both platforms provide dashboards for monitoring and investigation.

---

## Skills Demonstrated

- SIEM Deployment
- Windows Log Collection
- Splunk Configuration
- Wazuh Configuration
- Endpoint Monitoring
- Security Event Investigation
- Log Analysis

---

## Outcome

Successfully deployed a SOC Home Lab capable of collecting and monitoring Windows Event Logs using both Splunk Enterprise Security and Wazuh.
