# Lessons Learned

## Project Summary

Building this Splunk-Wazuh Home Lab provided practical experience in deploying, configuring, and troubleshooting enterprise security monitoring solutions.

---

# Technical Skills Gained

- Splunk Enterprise Installation
- Splunk Enterprise Security
- Wazuh Installation
- Windows Agent Configuration
- Splunk Universal Forwarder
- Windows Event Log Collection
- SIEM Monitoring
- Log Analysis
- SPL Query Writing
- Security Event Investigation

---

# Challenges Faced

## Challenge 1

Connecting the Windows 11 endpoint to Wazuh Manager.

**Solution**

Verified the manager IP address, restarted the Wazuh Agent service, and confirmed connectivity.

---

## Challenge 2

Logs were not initially appearing in Splunk.

**Solution**

Reviewed `inputs.conf` and `outputs.conf`, restarted the Universal Forwarder, and verified indexing.

---

## Challenge 3

Understanding differences between Splunk Enterprise Security and Wazuh.

**Solution**

Compared log collection, dashboards, alerting capabilities, and investigation workflows.

---

# Key Learnings

- SIEM platforms require proper configuration for successful log collection.
- Windows Event Logs provide valuable security information.
- Both Splunk and Wazuh can monitor the same endpoint but serve different security use cases.
- Proper troubleshooting involves checking services, configuration files, and network connectivity.

---

# Future Improvements

- Integrate Active Directory.
- Install Sysmon for enhanced endpoint visibility.
- Create custom SPL dashboards.
- Implement Sigma rules.
- Map detections to the MITRE ATT&CK Framework.
- Configure email alerting.
- Add Linux endpoint monitoring.

---

# Conclusion

This project strengthened my understanding of SOC operations, log management, threat detection, and incident investigation. It also provided hands-on experience with industry-standard SIEM technologies and improved my ability to deploy, configure, and troubleshoot enterprise security solutions.
