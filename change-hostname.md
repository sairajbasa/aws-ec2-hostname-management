# Change Hostname on an AWS EC2 Linux Instance (Step-by-Step)

Follow these steps to permanently change your EC2 instance hostname without rebooting.

---

## 1️⃣ Step 1 — Set New Hostname Using hostnamectl

```bash
sudo hostnamectl set-hostname myserver

hostnamectl
