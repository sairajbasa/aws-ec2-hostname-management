# Change Hostname on an AWS EC2 Linux Instance (Step-by-Step)

Follow these steps to permanently change your EC2 instance hostname without rebooting.

---

## 1️⃣ Step 1 — Set New Hostname Using hostnamectl

```bash
sudo hostnamectl set-hostname myserver
```

## Verify:

```bash
hostnamectl
```

## 2️⃣ Step 2 — Update the /etc/hosts File

Open the hosts file:

```bash
sudo nano /etc/hosts
```


Find the line containing your old hostname and replace it with the new one:

```bash
127.0.1.1   myserver
```

Save and exit:

Ctrl + O → Enter

Ctrl + X

## 3️⃣ Step 3 — Update the /etc/hostname File

Open the hostname file:
```bash
sudo nano /etc/hostname
```

Replace the old hostname with:
```bash
myserver
```

Save and exit.

## 4️⃣ Step 4 — Apply Changes Without Reboot

Restart the hostname service:

```bash
sudo systemctl restart systemd-hostnamed
```

## 5️⃣ Step 5 — Verify Final Hostname

Run:
```bash
hostname
hostnamectl
```


You should now see the updated hostname applied successfully.
