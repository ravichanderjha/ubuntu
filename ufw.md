### 📄 `ufw.md` — UFW (Uncomplicated Firewall) Cheat Sheet

````markdown
# 🔒 UFW (Uncomplicated Firewall) Cheat Sheet

## 📌 Basic Commands

### Enable/Disable UFW
```bash
sudo ufw enable
sudo ufw disable
````

### Check Status

```bash
sudo ufw status verbose
```

## 🔥 Rules Management

### Default Policies

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

### Allow Specific Port or Service

```bash
sudo ufw allow 22           # Allow SSH
sudo ufw allow 80/tcp       # Allow HTTP
sudo ufw allow 443          # Allow HTTPS
```

### Deny Specific Port

```bash
sudo ufw deny 25            # Deny SMTP
```

### Delete Rule

```bash
sudo ufw delete allow 22
```

### Allow Specific IP

```bash
sudo ufw allow from 192.168.1.100
```

---

## 📄 Enable Logging (Incoming Traffic Only)

### Enable Logging

```bash
sudo ufw logging low
```

* `low`: Logs blocked **incoming** packets only
* `medium`, `high`, `full`: Logs incoming + outgoing (more verbose)

### Check Logging Status

```bash
sudo ufw status verbose
```

Should show:

```
Logging: on (low)
```

---

## 📂 View Logs

### UFW Log File

```bash
sudo tail -f /var/log/ufw.log
```

### Journal Logs (Live)

```bash
sudo journalctl -f | grep UFW
```

### Filter Only Incoming Blocked

```bash
grep "UFW BLOCK.*IN=" /var/log/ufw.log
```

---

## 🔁 Restart Services (if needed)

```bash
sudo systemctl restart ufw
sudo systemctl restart rsyslog
```

---

## 📎 Notes

* Use `low` logging level to log only **incoming blocked** traffic.
* By default, UFW denies all **unsolicited incoming** if set to:

  ```bash
  sudo ufw default deny incoming
  ```

---

## 📚 Resources

* [https://wiki.ubuntu.com/UncomplicatedFirewall](https://wiki.ubuntu.com/UncomplicatedFirewall)
* man ufw

```

---

Let me know if you want a version in another format like `.sh` for automation, or `.pdf` for documentation handouts.
```
