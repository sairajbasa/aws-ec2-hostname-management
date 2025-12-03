# 🔄 Revert to Old Hostname on an AWS EC2 Linux Instance

This document provides clear steps to revert your EC2 instance hostname back to the previous value.

---

## 1️⃣ Step 1 — Set the Old Hostname Using `hostnamectl`

Replace `old-hostname` with your original hostname:

```bash
sudo hostnamectl set-hostname old-hostname
```

Verify:

```bash
hostnamectl
```

## 2️⃣ Step 2 — Update the /etc/hosts File
Open the hosts file:

```bash
sudo nano /etc/hosts
```
Find the new hostname (example: myserver) and replace it with your old hostname:

```bash
127.0.1.1   old-hostname
```

Save and exit:

Ctrl + O → Enter

Ctrl + X

## 3️⃣ Step 3 — Update the /etc/hostname File
Open the hostname file:

```bash
sudo nano /etc/hostname
```
Replace the current hostname with your old hostname:

```bash
old-hostname
```
Save and exit.

## 4️⃣ Step 4 — Apply the Changes Without Reboot
Restart the hostname service:

```bash
sudo systemctl restart systemd-hostnamed
```

## 5️⃣ Step 5 — Verify
Run the following commands:
```bash
hostname
hostnamectl
```
Your previous hostname should now be restored.
