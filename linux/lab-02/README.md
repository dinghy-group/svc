# Lab 2 — SSH into Our Ubuntu Server

## Objective

Connect to an Ubuntu virtual machine remotely using SSH (Secure Shell) from your host machine.

---

## Prerequisites

- VirtualBox installed with an Ubuntu VM already set up
- The VM must be **powered off** before changing network settings

---

## Steps

### 1. Configure the VM Network

1. Open **VirtualBox** and make sure the VM is **powered off**.
2. Right-click the VM → **Settings** → **Network** tab.
3. Change the **Attached to** dropdown from `NAT` to `Bridged Adapter`, then click **OK**.

> **Why Bridged Adapter?**
> This creates a bridge between your PC's network and the VM's network, allowing both to share the same local network. The VM will receive its own IP address from your router, making it reachable from your host machine.

### 2. Start the VM

Boot up the VM and log in with your credentials.

### 3. Update Package Lists

```bash
sudo apt-get update
```

This command updates the local package index and pulls the latest metadata from the repositories, ensuring you install the most up-to-date versions of packages.

### 4. Install OpenSSH Server

```bash
sudo apt install openssh-server -y
```

This installs all the dependencies needed to allow remote SSH access to the machine.

| Flag / Argument      | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| `apt`                | The package manager used in Ubuntu for installing, updating, and removing software |
| `install`            | Tells `apt` that we want to install a package                               |
| `openssh-server`     | The package that enables SSH (Secure Shell) remote access                   |
| `-y`                 | Automatically approves the installation prompt — without it, `apt` will pause and ask you to confirm with `y` or `n` |

### 5. Find Your VM's Private IP Address

```bash
ip a
```

This command displays network interface information. Look for an interface like `enp0s3` or `enp0s8` — under it, you'll see a line starting with `inet`, which is your internal IP address.

**Example output:**

```
enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP>
    inet 172.20.10.2/28 brd 172.20.10.15 scope global enp0s8
```

> **Note:** Use only the IP address **without** the subnet mask. In the example above, use `172.20.10.2` (not `172.20.10.2/28`). Save this IP for the next step.

### 6. SSH from Your Host Machine

Open a terminal (**CMD** on Windows, **Terminal** on macOS/Linux) and run:

```bash
ssh <username>@<vm-ip>
```

**Example:**

```bash
ssh itay@172.20.10.2
```

### 7. Accept the Fingerprint and Authenticate

- On the first connection, you'll be asked to verify the server's fingerprint — type `yes` and press Enter.
- Enter your VM user's password when prompted.

### 8. Verify the Connection

If everything was set up correctly, you should now see the Ubuntu terminal prompt from your host machine. You are now connected remotely via SSH!

---

## Screenshot

> Paste a screenshot here showing your terminal successfully connected to the Ubuntu VM via SSH.

---

## Summary

| Step | Action                          | Command / Tool                     |
|------|---------------------------------|------------------------------------|
| 1    | Set VM to Bridged Adapter       | VirtualBox → Settings → Network    |
| 2    | Update packages                 | `sudo apt-get update`              |
| 3    | Install SSH server              | `sudo apt install openssh-server -y` |
| 4    | Find VM IP                      | `ip a`                             |
| 5    | Connect via SSH                 | `ssh user@ip`                      |
