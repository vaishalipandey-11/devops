# Day 08 – Cloud Server Setup: Docker, Nginx & Web Deployment

## Goal
Deploy a real web server on a cloud instance and practice basic DevOps tasks like server setup, service deployment, and log extraction.

---

# Part 1 – Launch Cloud Instance & SSH Access

| Step | Action | Command / Process | Purpose |
|-----|--------|------------------|--------|
| 1 | Create Cloud Instance | Launch EC2 (AWS) or instance on Utho | Provision a virtual server in the cloud |
| 2 | Choose OS | Ubuntu 22.04 LTS (recommended) | Stable Linux environment |
| 3 | Create Key Pair | `your-key.pem` | Used for secure SSH login |
| 4 | Allow SSH Access | Security Group → Allow **port 22** | Enables remote SSH connection |
| 5 | Connect via SSH | `ssh -i your-key.pem ubuntu@<your-instance-ip>` | Connect to the remote server |

---

# Part 2 – Install Docker & Nginx

| Step | Command | Purpose |
|-----|--------|--------|
| Update system | `sudo apt update && sudo apt upgrade -y` | Updates package lists and installs latest updates |
| Install Docker | `sudo apt install docker.io -y` | Installs Docker container engine |
| Start Docker | `sudo systemctl start docker` | Starts Docker service |
| Enable Docker at boot | `sudo systemctl enable docker` | Ensures Docker starts after reboot |
| Install Nginx | `sudo apt install nginx -y` | Installs Nginx web server |
| Check Nginx status | `sudo systemctl status nginx` | Verify that Nginx service is running |

---

# Part 3 – Security Group Configuration

| Step | Configuration | Purpose |
|-----|---------------|--------|
| Open Port 80 | Security Group → Add rule **HTTP (Port 80)** | Allows public web traffic |
| Allow Source | `0.0.0.0/0` | Allows access from anywhere |
| Save Rule | Apply security group changes | Activates web access |

---

# Test Web Access

| Step | Action | Expected Result |
|-----|--------|----------------|
| Open browser | `http://<your-instance-ip>` | Access server from internet |
| Check page | Nginx Welcome Page | Confirms Nginx is working |

---

# Part 4 – Extract Nginx Logs

| Step | Command | Purpose |
|-----|--------|--------|
| View logs | `sudo cat /var/log/nginx/access.log` | Display Nginx access logs |
| View error logs | `sudo cat /var/log/nginx/error.log` | Display error logs |
| Save logs to file | `sudo cp /var/log/nginx/access.log ~/nginx-logs.txt` | Copy logs into a file |
| Verify log file | `cat ~/nginx-logs.txt` | Confirm logs were saved |

---

# Download Logs to Local Machine

| Platform | Command | Purpose |
|---------|--------|--------|
| AWS | `scp -i your-key.pem ubuntu@<your-instance-ip>:~/nginx-logs.txt .` | Copy log file from server to local machine |
| Utho | `scp root@<your-instance-ip>:~/nginx-logs.txt .` | Download logs locally |

---

# Commands Used

| Command | Purpose |
|-------|--------|
| `ssh -i key.pem ubuntu@ip` | Connect to cloud server |
| `sudo apt update` | Update package lists |
| `sudo apt install nginx` | Install Nginx web server |
| `sudo systemctl status nginx` | Check service status |
| `sudo cat /var/log/nginx/access.log` | View web access logs |
| `scp` | Transfer files between server and local system |

---

# Challenges Faced

| Issue | Cause | Solution |
|-----|------|---------|
| Cannot connect via SSH | Port 22 not open | Add SSH rule in security group |
| Website not loading | Port 80 blocked | Allow HTTP traffic in security group |
| Nginx not running | Service not started | Run `sudo systemctl start nginx` |
| Permission denied during SCP | Incorrect key or user | Use correct `.pem` file and username |

---

# What I Learned

| Learning | Explanation |
|--------|-------------|
| Cloud server provisioning | How to launch and configure a cloud VM |
| SSH remote management | Securely connecting to remote servers |
| Web server deployment | Installing and running Nginx |
| Security configuration | Opening required ports in firewall/security groups |
| Log analysis | Accessing and saving server logs |

---

# DevOps Takeaway

| DevOps Skill | Importance |
|--------------|-----------|
| Infrastructure provisioning | Creating servers on demand |
| Remote server management | Using SSH for administration |
| Web deployment | Hosting web applications |
| Log monitoring | Troubleshooting server issues |
| Security configuration | Managing firewall and access rules |
