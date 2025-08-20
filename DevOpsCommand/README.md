# 🚀 Ubuntu/Debian DevOps Command Cheat Sheet


---

## 📌 System Basics

```bash
uname -a         # Show system info (kernel, architecture)
hostnamectl      # Show hostname & OS details
uptime           # Show how long the system is running
whoami           # Show current logged-in user
id               # Show user ID and group info
pwd              # Print current working directory
```

---

## 📌 User & Permissions

```bash
adduser john     # Add new user
usermod -aG sudo john   # Give user sudo access
passwd john      # Change user password
su - john        # Switch to another user
chmod 755 file   # Change file permission (rwxr-xr-x)
chown user:group file   # Change file owner and group
```

---

## 📌 Package Management (APT)

```bash
apt update            # Update package list
apt upgrade           # Upgrade installed packages
apt install nginx     # Install package (e.g., nginx)
apt remove nginx      # Remove package
apt autoremove        # Remove unused dependencies
apt search apache     # Search for package
```

---

## 📌 Process Management

```bash
ps aux                # Show all running processes
htop                  # Interactive process viewer (install: apt install htop)
top                   # Show processes in real-time
kill -9 1234          # Kill process by PID
systemctl status nginx    # Check service status
systemctl restart nginx   # Restart service
```

---

## 📌 Networking

```bash
ip a                  # Show IP addresses
ping google.com       # Test network connectivity
curl ifconfig.me      # Show public IP address
netstat -tulnp        # Show listening ports (install: apt install net-tools)
ss -tuln              # Show open ports (modern alternative)
traceroute google.com # Show network path (install: apt install traceroute)
```

---

## 📌 File & Directory Management

```bash
ls -l                 # List files with details
cd /path/to/dir       # Change directory
cp file1 file2        # Copy file
mv old new            # Rename/Move file
rm file               # Remove file
rm -rf dir            # Remove directory (force)
touch file.txt        # Create empty file
mkdir newfolder       # Create directory
```

---

## 📌 Disk Management

```bash
df -h                 # Show disk usage
lsblk                 # List block devices
du -sh folder/        # Show folder size
mount /dev/sdb1 /mnt  # Mount disk
umount /mnt           # Unmount disk
```

---

## 📌 Logs & Monitoring

```bash
dmesg | less          # Kernel logs
journalctl -xe        # Show detailed logs
journalctl -u nginx   # Show logs for nginx service
tail -f /var/log/syslog   # Live view system logs
tail -f /var/log/nginx/error.log   # Nginx error log
```

---

## 📌 SSH & Remote Access

```bash
ssh user@server-ip          # Connect to remote server
ssh -i key.pem user@ip      # Connect using key
scp file user@ip:/path/     # Copy file to remote server
rsync -avz file user@ip:/path/   # Sync file/dir to remote server
```

---

## 📌 Firewall (UFW)

```bash
ufw enable             # Enable firewall
ufw disable            # Disable firewall
ufw status             # Show firewall rules
ufw allow 22           # Allow SSH port
ufw allow 80/tcp       # Allow HTTP
ufw allow 443/tcp      # Allow HTTPS
ufw deny 23            # Deny telnet port
```

---

## 📌 Systemctl (Service Management)

```bash
systemctl start nginx      # Start service
systemctl stop nginx       # Stop service
systemctl restart nginx    # Restart service
systemctl enable nginx     # Start service on boot
systemctl disable nginx    # Disable auto start
systemctl status nginx     # Check service status
```

---

## 📌 Docker (Essentials)

```bash
docker ps                 # List running containers
docker ps -a              # List all containers
docker images             # List images
docker run -it ubuntu bash   # Run container in interactive mode
docker stop <id>          # Stop container
docker rm <id>            # Remove container
docker rmi <id>           # Remove image
```

---

## 📌 Git Basics

```bash
git init                 # Initialize repository
git clone URL            # Clone repo
git status               # Show repo status
git add file             # Stage file
git commit -m "msg"      # Commit changes
git push origin main     # Push changes
git pull origin main     # Pull changes
```

---

## 📌 Nmap (Security/Network Scan)

```bash
nmap ip-address         # Scan open ports
nmap -sV ip-address     # Detect service versions
nmap -A ip-address      # Aggressive scan (OS, services, scripts)
nmap -p 80,443 ip       # Scan specific ports
nmap -T4 ip             # Faster scan (timing option)
```

---

## 📌 Bonus: Useful Shortcuts

```bash
history | grep keyword   # Search past commands
!!                       # Run last command again
!123                     # Run command number 123 from history
alias ll='ls -lah'       # Create shortcut (ll → ls -lah)
```

