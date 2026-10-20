
# SSH Server Installation Guide

## 1. Project
Secured Network Service Configuration with SCP, SFTP, and SSH.

## 2. Environment
- Server OS: Ubuntu Server 24.04 LTS
- SSH Server: OpenSSH
- Default SSH port: TCP 22
- Client: Windows PowerShell or Ubuntu Linux

## 3. Install OpenSSH Server

```bash
sudo apt update
sudo apt install openssh-server openssh-client -y
```

## 4. Start and Enable SSH

```bash
sudo systemctl enable --now ssh
systemctl status ssh --no-pager
```

## 5. Verify SSH Port

```bash
sudo ss -tlnp | grep ':22'
```

## 6. Client Connection Test

For NAT with port forwarding:

```powershell
Test-NetConnection 127.0.0.1 -Port 2222
ssh -p 2222 adminlab@127.0.0.1
```

Replace `adminlab` with the actual Ubuntu username.

## 7. Security Notes
- Use SSH key authentication.
- Disable root login when appropriate.
- Disable password authentication only after testing key-based login.
- Never commit private keys or passwords.
