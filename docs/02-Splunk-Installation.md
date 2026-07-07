# Splunk Enterprise Installation

## Objective

Install Splunk Enterprise and Splunk Enterprise Security on Ubuntu Server.

---

## Lab Environment

| Component | Version |
|----------|---------|
| Ubuntu | 22.04 LTS |
| Splunk Enterprise | 9.x |
| Splunk Enterprise Security | Latest |
| RAM | 8 GB |
| CPU | 4 Cores |

---

# Step 1: Update Ubuntu

```bash
sudo apt update
sudo apt upgrade -y
```

---

# Step 2: Download Splunk Enterprise

```bash
wget -O splunk.deb "YOUR_SPLUNK_DOWNLOAD_LINK"
```

Or download manually from Splunk.

---

# Step 3: Install Splunk

```bash
sudo dpkg -i splunk.deb
```

---

# Step 4: Start Splunk

```bash
sudo /opt/splunk/bin/splunk start --accept-license
```

---

# Step 5: Enable Splunk at Boot

```bash
sudo /opt/splunk/bin/splunk enable boot-start
```

---

# Step 6: Verify Splunk Status

```bash
sudo /opt/splunk/bin/splunk status
```

Expected Output

```
splunkd is running
```

---

# Step 7: Access Splunk

```
https://<Splunk-IP>:8000
```

Login using your administrator account.

---

# Step 8: Install Enterprise Security

1. Download Enterprise Security.
2. Go to **Apps → Manage Apps**.
3. Click **Install app from file**.
4. Upload the ES package.
5. Restart Splunk.

---

## Verification

- Splunk service running
- Web interface accessible
- Enterprise Security dashboard available

---

## Screenshots

(Add screenshots here)

---

## Outcome

Successfully installed Splunk Enterprise and Enterprise Security.
