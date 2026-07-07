# Install Wazuh

```bash
curl -sO https://packages.wazuh.com/4.x/wazuh-install.sh
```

```bash
sudo bash wazuh-install.sh -a
```

---

# Check Services

```bash
sudo systemctl status wazuh-manager
```

```bash
sudo systemctl status wazuh-indexer
```

```bash
sudo systemctl status wazuh-dashboard
```

---

# Verify

```bash
sudo netstat -tulnp
```

or

```bash
ss -tulnp
```
