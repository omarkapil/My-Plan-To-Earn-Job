# WEEK 3: LINUX HARDENING & SYSTEMS ADMINISTRATION

## The "Why" (Job Market Context)

**Hiring Demand:**
- 96% of infrastructure roles require Linux proficiency
- "Linux is the default in cloud" - 95% of AWS workloads run Linux
- System administration skills separate junior from mid-level engineers
- Salary premium: Linux expertise = +$15K/year vs. Windows-only

**Recruiter Perspective:**
- "Can they manage servers, not just launch them?"
- "Do they understand permissions, file systems, services?"
- "Can they diagnose system issues (disk space, CPU, memory)?"

**Role Relevance:**
- **Cloud Infrastructure Engineer:** 95% (EC2 instances are Linux)
- **IT Infrastructure Specialist:** 90% (hybrid environments)
- **Junior Security Engineer:** 95% (security starts with system hardening)

---

## Industry Context

**What Companies Care About:**
- Securing systems against attacks (hardening)
- Managing system resources (CPU, memory, disk)
- Automating system tasks (shell scripts, systemd)
- User access control (permissions, sudo, keys)
- Performance tuning and troubleshooting

**Real-World Scenarios:**
- "Disk is full, find what's consuming space and clean up"
- "This service crashed, check logs and restart"
- "User needs access to this directory; set up permissions"
- "We got hacked; audit user accounts and remove suspicious ones"

**Interview Gotchas:**
- "How would you secure a Linux server?"
- "Walk me through file permissions (rwx for user/group/other)"
- "You have a runaway process consuming all CPU; how do you find and kill it?"
- "Set up SSH key authentication and disable password login"

---

## Step-by-Step Learning Path (18 hours)

### Day 1-2: Linux File Systems & Permissions (4 hours)

**What You're Learning:**

1. **File System Structure (1 hour)**
   - `/bin`: Essential commands (ls, cat, cp)
   - `/etc`: Configuration files (ssh, sudoers, hostname)
   - `/home`: User home directories
   - `/root`: Root user home
   - `/var`: Variable data (logs, databases, caches)
   - `/tmp`: Temporary files
   - `/opt`: Optional software
   - **Why it matters:** Know where to find things, where to put configs

2. **File Permissions (2 hours)**
   - rwx permissions: Read (4), Write (2), Execute (1)
   - Three levels: Owner (user), Group, Others
   - Octal notation: 755 = rwxr-xr-x
   - Example scenarios:
     - `chmod 600 ~/.ssh/id_rsa` (only owner can read private key)
     - `chmod 755 /usr/bin/python` (everyone can execute)
     - `chmod 644 /etc/passwd` (everyone can read, only root can write)
   - **Why it matters:** Security depends on correct permissions

3. **Users & Groups (1 hour)**
   - Users: Individual identities with UIDs
   - Groups: Collections of users with GIDs
   - `sudo`: Execute commands as root (carefully!)
   - `/etc/sudoers`: Control who can use sudo
   - Example: `sudo useradd -m -s /bin/bash newuser` (create user)
   - **Why it matters:** User management is daily task

**YOUR REVISION ELEMENT:**
- You used Linux in ITI/NTI; now master administration, not just usage

---

### Day 3-4: Service Management & Troubleshooting (4 hours)

**What You're Learning:**

1. **Systemd Service Management (1.5 hours)**
   - `systemctl start/stop/restart/status` (manage services)
   - `systemctl enable/disable` (auto-start on reboot)
   - `systemctl list-units --type=service` (see all services)
   - **Common services:** ssh, httpd, nginx, mysql, docker
   - Real scenario: "Nginx isn't responding; restart it and check logs"

2. **System Performance Monitoring (1.5 hours)**
   - `top`: Real-time process monitoring
   - `ps aux`: See all running processes
   - `htop`: Better top (colorized, interactive)
   - `df -h`: Disk usage by filesystem
   - `du -sh *`: Disk usage by directory
   - `free -h`: Memory usage
   - Real scenario: "System is slow; check what's consuming CPU and memory"

3. **Log Analysis (1 hour)**
   - Log files in `/var/log/`: syslog, auth.log, apache2/access.log, etc.
   - `tail -f /var/log/syslog` (real-time log watching)
   - `grep` to find specific errors
   - **Security logs:** `/var/log/auth.log` shows login attempts (attacks?)
   - Real scenario: "Service failed; check logs to understand why"

---

## Hands-On Labs (14 hours total)

### Lab 3A: Secure Linux Server Hardening (5 hours)

**Objective:** Secure an EC2 instance following industry best practices

**Detailed Steps:**

1. **User & Access Management (1.5 hours)**
   ```bash
   # Create admin user (not root)
   sudo useradd -m -s /bin/bash admin
   sudo usermod -aG sudo admin
   sudo passwd admin
   
   # Disable root login
   sudo usermod -L root
   
   # Set up SSH key authentication
   sudo mkdir -p /home/admin/.ssh
   sudo cp ~/.ssh/authorized_keys /home/admin/.ssh/
   sudo chown -R admin:admin /home/admin/.ssh
   sudo chmod 700 /home/admin/.ssh
   sudo chmod 600 /home/admin/.ssh/authorized_keys
   
   # Disable password authentication
   sudo sed -i 's/PasswordAuthentication yes/PasswordAuthentication no/' /etc/ssh/sshd_config
   sudo systemctl restart ssh
   ```

2. **File System & Permission Hardening (1 hour)**
   ```bash
   # Set restrictive permissions on sensitive files
   sudo chmod 644 /etc/passwd
   sudo chmod 640 /etc/shadow
   sudo chmod 644 /etc/group
   
   # Set umask for new files (restrictive)
   echo "umask 0077" | sudo tee -a /etc/profile
   ```

3. **Firewall Configuration (1 hour)**
   ```bash
   # Enable UFW (Uncomplicated Firewall)
   sudo apt-get install -y ufw
   sudo ufw allow 22/tcp  # SSH
   sudo ufw allow 80/tcp  # HTTP
   sudo ufw allow 443/tcp # HTTPS
   sudo ufw enable
   ```

4. **Update System & Security Patches (0.5 hours)**
   ```bash
   sudo apt-get update
   sudo apt-get upgrade -y
   sudo apt-get install -y fail2ban  # Prevent brute force
   ```

5. **Audit & Verify (1 hour)**
   - Check running services (remove unnecessary ones)
   - Verify logs show no errors
   - Test SSH with keys (password should fail)
   - Document all changes

**Deliverable:** GitHub documentation
- Hardening checklist with commands
- Before/after security settings
- Explanation: Why each hardening step matters

**Success Criteria:**
- ✅ SSH key authentication works, passwords disabled
- ✅ Root login disabled
- ✅ Unnecessary services removed
- ✅ Firewall configured
- ✅ System updated

---

### Lab 3B: Process Management & Performance Tuning (4 hours)

**Objective:** Monitor system resources and troubleshoot performance issues

**Tasks:**

1. **Monitor Running Processes (1 hour)**
   - Use `top` to identify resource hogs
   - Use `ps aux | grep process-name` to find specific processes
   - Record current baseline (CPU, memory usage)

2. **Create Performance Stress Scenario (1 hour)**
   ```bash
   # Install stress tool
   sudo apt-get install -y stress
   
   # Create high CPU load
   stress --cpu 2 --timeout 300s
   
   # Observe with top - see CPU spike
   # In another terminal: top, sort by CPU (%CPU column)
   ```

3. **Troubleshoot the Issue (1 hour)**
   - Identify stress process consuming CPU
   - Find process ID (PID)
   - Kill process: `kill -9 <PID>`
   - Verify CPU returns to normal

4. **Disk Space Management (1 hour)**
   - Find large directories: `du -sh /* | sort -h`
   - Identify logs consuming space: `du -sh /var/log/*`
   - Clean up: `sudo truncate -s 0 /var/log/syslog`
   - Set log rotation in `/etc/logrotate.d/`

**Deliverable:** GitHub documentation
- Performance baseline data (top output)
- Stress test results
- Troubleshooting steps taken
- Resolution and prevention

---

### Lab 3C: Shell Scripting for Automation (3 hours)

**Objective:** Write scripts to automate common system administration tasks

**Task 1: System Health Check Script (1 hour)**
```bash
#!/bin/bash
# system-health.sh - Check system health and alert if issues

echo "=== System Health Report ==="
echo "Hostname: $(hostname)"
echo "Uptime: $(uptime)"
echo ""

# Check disk usage
echo "Disk Usage:"
df -h | grep -E '^/dev'

# Check memory usage
echo ""
echo "Memory Usage:"
free -h

# Check critical services
echo ""
echo "Critical Services Status:"
systemctl is-active ssh && echo "SSH: OK" || echo "SSH: FAILED"
systemctl is-active syslog && echo "Syslog: OK" || echo "Syslog: FAILED"

# Check failed logins (security)
echo ""
echo "Failed Login Attempts (Last 24 hours):"
grep "Failed password" /var/log/auth.log | grep "$(date +%b\ %d)" | wc -l
```

**Task 2: User Account Audit Script (1 hour)**
```bash
#!/bin/bash
# audit-users.sh - Find and report suspicious user accounts

echo "=== User Account Audit ==="
echo ""
echo "Users with sudo access:"
getent group sudo | cut -d: -f4
echo ""

echo "Users with shell access (not just system accounts):"
grep -E :/bin/bash$ /etc/passwd | cut -d: -f1

echo ""
echo "Accounts with empty passwords (SECURITY RISK):"
awk -F: '($2 == "" ) {print $1}' /etc/shadow
```

**Task 3: Log Rotation & Cleanup Script (1 hour)**
```bash
#!/bin/bash
# cleanup-old-logs.sh - Remove logs older than 30 days

echo "Removing logs older than 30 days..."
find /var/log -type f -mtime +30 -delete

echo "Current log sizes:"
du -sh /var/log/*
```

**Deliverable:** GitHub repository with all scripts
- Each script documented with explanations
- Example output showing script in action
- Use case for each script

---

### Lab 3D: SSH Hardening & Key Management (2 hours)

**Objective:** Secure SSH (most commonly attacked service)

**Tasks:**

1. **Generate SSH Keys (15 min)**
   ```bash
   ssh-keygen -t ed25519 -C "admin@server" -f ~/.ssh/server_key
   # Don't use password for automated access (trade-off: convenience vs. security)
   ```

2. **Disable Dangerous SSH Features (30 min)**
   - Edit `/etc/ssh/sshd_config`
   - `PermitRootLogin no` (disable root SSH)
   - `PasswordAuthentication no` (keys only)
   - `PermitEmptyPasswords no` (emergency safeguard)
   - `X11Forwarding no` (disable X11, unnecessary)
   - `MaxAuthTries 3` (fail faster after 3 wrong passwords)
   - Restart SSH: `sudo systemctl restart ssh`

3. **Test SSH Hardening (45 min)**
   - Verify SSH with keys works
   - Verify password login fails
   - Verify root login fails
   - Document findings

**Deliverable:** GitHub documentation
- Before/after SSH configs
- Commands to apply hardening
- Security rationale for each setting

---

## Assessment Checkpoint (Friday)

### Weekly Quiz (45 min)

**Instructions:** Answer the following 12 questions. Target: 10/12 (83%+)

1. **What do the letters 'rwx' in file permissions stand for?**
   - A) Read, Write, Execute
   - B) Run, Write, Exchange
   - C) Replace, Work, Execute
   - Answer: A

2. **What is the octal value for 'rwx' permissions?**
   - A) 5
   - B) 7
   - C) 3
   - Answer: B

3. **To change permissions on a file to 644, what command do you use?**
   - A) chmod 644 filename
   - B) chown 644 filename
   - C) chgrp 644 filename
   - Answer: A

4. **What command shows all running processes?**
   - A) ps aux
   - B) ls -la
   - C) df -h
   - Answer: A

5. **If a process is consuming 95% CPU, what command would you use to kill it by ID?**
   - A) kill -9 <PID>
   - B) stop <PID>
   - C) remove <PID>
   - Answer: A

6. **The 'sudo' command allows:**
   - A) Any user to execute any command
   - B) Specific users to execute commands as root
   - C) Root to execute commands as user
   - Answer: B

7. **Where are system logs typically stored?**
   - A) /home/logs
   - B) /var/log
   - C) /etc/logs
   - Answer: B

8. **What command would you use to see real-time system resource usage?**
   - A) ps
   - B) df
   - C) top
   - Answer: C

9. **To disable SSH password authentication, you would edit:**
   - A) /etc/ssh/authorized_keys
   - B) /etc/ssh/sshd_config
   - C) /etc/passwd
   - Answer: B

10. **Which of these is the most secure SSH key type?**
    - A) RSA 1024-bit
    - B) DSA
    - C) Ed25519
    - Answer: C

11. **To add a user to the sudo group, you would use:**
    - A) usermod -aG sudo username
    - B) addgroup username sudo
    - C) Either A or B
    - Answer: C

12. **The /tmp directory is used for:**
    - A) Permanent system files
    - B) Temporary files (often deleted on reboot)
    - C) User home directories
    - Answer: B

---

## Interview Preparation

### Technical Interview Questions

**Question 1:** "Walk me through securing a Linux server from scratch"
- Cover: User management, SSH hardening, firewall, updates, monitoring
- Time: 7-10 minutes

**Question 2:** "A server is running slow. Walk me through your diagnostic process"
- Use `top` to check CPU/memory
- Use `df -h` to check disk
- Use logs to find errors
- Time: 5-7 minutes

**Question 3:** "Explain Linux file permissions (rwx) and show examples"
- Explain octal notation
- Examples: 644 (rw-r--r--), 755 (rwxr-xr-x), 600 (rw-------)
- Time: 3-5 minutes

---

## Soft Skills: Technical Blog Post

**Topic:** "Securing a Linux Server: Essential Hardening Steps"
**Length:** 500-700 words
**Publish:** LinkedIn or Medium by Sunday

---

## Week 3 Checklist

- [ ] Lab 3A: Linux hardening (5 hours)
- [ ] Lab 3B: Process management (4 hours)
- [ ] Lab 3C: Shell scripts (3 hours)
- [ ] Lab 3D: SSH hardening (2 hours)
- [ ] All labs documented on GitHub
- [ ] Assessment quiz completed
- [ ] Blog post published

---

---

# WEEK 4: ADVANCED AWS ARCHITECTURE & FIRST PORTFOLIO CAPSTONE

## The "Why" (Job Market Context)

**Hiring Demand:**
- 100% of Cloud Infrastructure roles require architecture skills
- "Design a scalable infrastructure for 1M users" - Standard interview question
- Architecture thinking separates senior engineers from juniors
- Salary: Architecture expertise = $20K+ premium

---

## Industry Context

**Real-World Architecture Decisions:**
- Multi-AZ for high availability (prevents entire region outage)
- Load balancers for horizontal scaling (not vertical)
- Database replicas for read scaling
- Auto-scaling groups for elasticity
- CloudFront CDN for global users

**Interview Gotchas:**
- "Design for cost" (not just performance)
- "How would you handle 10x traffic spike?"
- "Disaster recovery plan for database failure"

---

## Step-by-Step Learning Path (20 hours)

### Day 1-3: Advanced AWS Services (8 hours)

**What You're Learning:**

1. **Elastic Load Balancer (ELB) - 2 hours**
   - Application Load Balancer (ALB): Layer 7, path/hostname routing
   - Network Load Balancer (NLB): Layer 4, extreme performance
   - Classic Load Balancer (CLB): Legacy
   - Health checks: Route traffic only to healthy instances
   - Real scenario: 3 web servers behind ALB, distribute traffic evenly

2. **Auto Scaling - 2 hours**
   - Launch template: Config for instances to launch
   - Auto Scaling Group: Auto-scales instances 1-10 based on demand
   - Scaling policies: Scale up if CPU > 70%, scale down if < 30%
   - Real scenario: Black Friday spike, automatically scale from 5 → 100 servers

3. **CloudFormation Deep-Dive - 2 hours**
   - Infrastructure as Code: Define all resources in JSON/YAML
   - Advantages: Reproducible, version-controlled, fast deployments
   - Stacks: Group of resources created from template
   - Parameters: Make templates reusable
   - Real scenario: Deploy complete app in 5 minutes vs. 2 hours manually

4. **RDS & Database Strategy - 2 hours**
   - Multi-AZ deployment: Synchronous replica for failover
   - Read replicas: Async replicas for scale-out reads
   - Backups: Automated daily, point-in-time recovery
   - Real scenario: Database failed, automatic failover to replica, zero downtime

---

### Day 4-7: Architecture Patterns & Design Thinking (12 hours)

**What You're Learning:**

1. **Three-Tier Architecture Pattern (3 hours)**
```
     Internet
        ↓
   CloudFront (CDN)
        ↓
   Application Load Balancer (ALB)
        ↓
   Web Tier (Auto Scaling Group of EC2)
        ↓
   App Tier (Private, Auto Scaling Group of EC2)
        ↓
   Database Tier (RDS Multi-AZ)
```
- **Benefits:** Scalable, secure, highly available
- **Each tier:** Can scale independently
- **Real companies:** All major apps use this pattern

2. **High Availability Principles (2 hours)**
   - Multi-AZ: Spread across availability zones
   - Health checks: Route around failing instances
   - Auto-scaling: Replace failed instances automatically
   - Target: 99.9% uptime (8.76 hours downtime/year)

3. **Cost Optimization Patterns (3 hours)**
   - Spot instances: 90% discount but can terminate anytime
   - Reserved instances: 70% discount for 1-3 year commitment
   - Right-sizing: Use smallest instance type that meets demand
   - Auto-scaling: Pay for compute only when needed
   - S3 storage classes: Glacier for archival (cheaper)

4. **Disaster Recovery Strategy (2 hours)**
   - RTO (Recovery Time Objective): How fast to recover?
   - RPO (Recovery Point Objective): How much data loss acceptable?
   - Backup strategy: Daily snapshots, store in another region
   - Real scenario: Region fails, restore from backup in different region

5. **Security Architecture (2 hours)**
   - Network segmentation: Public/private subnets
   - Security groups: Principle of least privilege
   - Data encryption: In-transit (HTTPS) and at-rest (KMS)
   - IAM: Roles for services, not hardcoded credentials

---

## Portfolio Capstone Project: Week 4 (MAJOR DELIVERABLE)

### Project: Three-Tier Web Application Architecture on AWS

**Objective:** Design and deploy a production-ready, scalable, secure 3-tier application

**Requirements:**

1. **Architecture Design (2 hours)**
   - Create architecture diagram (draw.io, Lucidchart)
   - Show: VPC, subnets (public/private), ALB, EC2 fleet, RDS, S3
   - Include: Security groups, routing, data flow
   - Explain: Why each component, cost considerations

2. **Infrastructure as Code (4 hours)**
   - Write CloudFormation template (JSON or YAML) that creates:
     - VPC with 2 public subnets (AZ-A, AZ-B)
     - 2 private subnets (for app/DB)
     - Internet Gateway, NAT Gateway
     - RDS instance (MySQL)
     - Launch template for web servers
     - Auto Scaling Group (min 2, max 4 instances)
     - Application Load Balancer
     - Security groups for each tier
   - Ensure: Fully automated, repeatable deployment

3. **Testing & Verification (2 hours)**
   - Deploy stack via CloudFormation
   - Verify all resources created correctly
   - Test load balancer (distribute traffic to multiple servers)
   - Test RDS connection from EC2
   - Test security groups (correct traffic allowed/blocked)
   - Delete stack and verify cleanup (cost control)

4. **Documentation (2 hours)**
   - Architecture diagram (professional quality)
   - CloudFormation template with comments explaining each resource
   - Deployment guide: Step-by-step to deploy
   - Cost analysis: Estimate monthly cost, optimization suggestions
   - Disaster recovery plan: How to recover from region failure

5. **Security Review (1 hour)**
   - Checklist: Encryption enabled, least privilege access, no hardcoded credentials
   - Test: Try accessing database from internet (should fail)
   - Verify: EC2 instances can't SSH to each other (unless needed)

---

## Hands-On Labs (15 hours)

### Lab 4A: Load Balancing & Auto Scaling (5 hours)

**Objective:** Set up load-balanced, auto-scaled infrastructure

**Steps:**

1. **Create Launch Template (1 hour)**
   - Define EC2 instance configuration (AMI, instance type, security groups)
   - User data script: Install web server, display server ID
   ```bash
   #!/bin/bash
   yum install -y httpd
   systemctl start httpd
   echo "Response from $(hostname -f)" > /var/www/html/index.html
   ```

2. **Create Auto Scaling Group (1.5 hours)**
   - Min: 2 instances, Max: 4 instances
   - Desired: 2 instances
   - Availability zones: us-east-1a, us-east-1b
   - Set scaling policies: Scale up if CPU > 70%, scale down if < 30%

3. **Create Application Load Balancer (1.5 hours)**
   - Create ALB in VPC
   - Create target group: Point to ASG
   - Create listener: Port 80 → forward to target group
   - Configure health checks: Check /index.html every 30 seconds

4. **Testing (1 hour)**
   - Get ALB DNS name
   - Refresh browser multiple times → Notice different server responses
   - Monitor CloudWatch: See CPU, requests per server
   - Simulate spike: Generate load, watch ASG scale up
   - Watch scale down: Wait for load to drop, ASG shrinks

**Deliverable:** GitHub documentation + screenshots

---

### Lab 4B: CloudFormation Template Creation (5 hours)

**Objective:** Write reusable CloudFormation template for 3-tier architecture

**Template Structure:**
```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: 'Three-tier web application architecture'

Parameters:
  InstanceType:
    Type: String
    Default: t2.micro
    AllowedValues: [t2.micro, t2.small, t2.medium]

Resources:
  # VPC
  VPC:
    Type: AWS::EC2::VPC
    Properties:
      CidrBlock: 10.0.0.0/16
  
  # Subnets, IGW, NAT, RDS, ALB, ASG, Security Groups
  # ... (detailed template)

Outputs:
  LoadBalancerDNS:
    Value: !GetAtt LoadBalancer.DNSName
    Description: 'URL to access the application'
```

**Tasks:**
1. Write template creating all resources
2. Deploy using CloudFormation console
3. Test that application works
4. Delete stack and verify cleanup

**Deliverable:** CloudFormation template on GitHub with comments

---

### Lab 4C: Cost Analysis & Optimization (3 hours)

**Objective:** Understand AWS costs and optimize

**Tasks:**

1. **Calculate Monthly Cost (1 hour)**
   - 2 t2.micro EC2: $0.0116/hour × 730 hours/month = ~$17/month (free tier)
   - RDS MySQL t2.micro: $0.015/hour = ~$11/month (free tier)
   - ALB: $0.0225/hour = ~$16/month
   - Data transfer: ~$0.09/GB
   - Total: ~$50-100/month for this architecture

2. **Optimization Suggestions (1 hour)**
   - Use Reserved Instances: Save 70% on compute
   - Use Spot Instances: Save 90% but app must tolerate interruptions
   - Use RDS storage optimization: Tiered storage for logs
   - Use CloudFront: Cache static content, reduce ALB load

3. **AWS Cost Calculator (1 hour)**
   - Use AWS pricing calculator to estimate costs
   - Compare: On-demand vs. Reserved vs. Spot
   - Document findings

**Deliverable:** Cost analysis document

---

### Lab 4D: RDS Multi-AZ & Backup Strategy (2 hours)

**Objective:** Set up database for high availability and disaster recovery

**Tasks:**

1. **Enable Multi-AZ (30 min)**
   - Create RDS instance
   - Enable Multi-AZ: Creates synchronous replica in different AZ
   - Automatic failover if primary fails

2. **Test Failover (45 min)**
   - Connect to primary database
   - Reboot with failover: Forces failover to replica
   - Verify: Connection still works (automatic)
   - Monitor: CloudWatch shows failover event

3. **Backup Strategy (45 min)**
   - Enable automated backups: 7-day retention
   - Create manual snapshot for archival
   - Test restore: Verify snapshot can restore

**Deliverable:** Screenshots and documentation

---

## Assessment Checkpoint (Friday)

### Weekly Quiz (45 min)

**Instructions:** 12 questions. Target: 10/12 (83%+)

1. **What does ALB stand for?**
   - Answer: Application Load Balancer

2. **At which OSI layer does ALB operate?**
   - A) Layer 3
   - B) Layer 4
   - C) Layer 7
   - Answer: C

3. **Auto Scaling Group with min=2, max=4, desired=2 means:**
   - A) Always 2 instances
   - B) Always 4 instances
   - C) Ranges from 2-4 based on demand
   - Answer: C

4. **CloudFormation provides what benefit?**
   - A) Infrastructure as Code (repeatable)
   - B) Cost prediction
   - C) Both
   - Answer: C

5. **Multi-AZ RDS provides:**
   - A) Backup only
   - B) Automatic failover
   - C) Both
   - Answer: C

6. **Disaster recovery RTO means:**
   - A) Recovery Time Objective (how fast)
   - B) Recovery Type Objective
   - C) Neither
   - Answer: A

7. **To save 70% on EC2 costs:**
   - A) Use Spot instances
   - B) Use Reserved instances
   - C) Use On-demand
   - Answer: B

8. **In a 3-tier architecture, the database tier should be:**
   - A) In public subnet
   - B) In private subnet
   - C) No preference
   - Answer: B

9. **Health checks in ALB prevent:**
   - A) Traffic from reaching failed instances
   - B) Scaling up
   - C) Cost increases
   - Answer: A

10. **CloudFormation parameters allow:**
    - A) Hard-coded values
    - B) User input for variables
    - C) AWS to decide values
    - Answer: B

11. **S3 Glacier storage class is used for:**
    - A) Frequently accessed data
    - B) Long-term archival
    - C) Streaming data
    - Answer: B

12. **To make RDS accessible only from EC2 instances:**
    - A) Use IP-based security groups
    - B) Use security group referencing
    - C) Neither
    - Answer: B

---

## Interview Preparation

### Architecture Design Question

**Question:** "Design a scalable infrastructure for an e-commerce site expecting 1M users during Black Friday"

**Expected Answer Framework:**
```
1. Front-end layer:
   - CloudFront CDN for static assets
   - ALB to distribute traffic
   
2. App layer:
   - Auto Scaling Group of EC2 instances
   - ASG scales to handle 10x normal traffic
   - Health checks ensure traffic only to healthy servers
   
3. Database layer:
   - RDS Multi-AZ for high availability
   - Read replicas for read-heavy queries
   - Backups for disaster recovery
   
4. Cost optimization:
   - Spot instances for non-critical workloads
   - Reserved instances for baseline capacity
   - Auto-scaling prevents overprovisioning
   
5. Security:
   - VPC with public/private subnets
   - Security groups with least privilege
   - Encryption in-transit (HTTPS) and at-rest
   
6. Monitoring:
   - CloudWatch alarms for metrics
   - Auto Scaling based on demand
   - Quick incident response
```

**Time:** 10-15 minutes

---

## Soft Skills: Architecture Documentation

**Capstone Project Deliverable:**
- Architecture diagram (professional)
- CloudFormation template (production-ready)
- Deployment guide (step-by-step)
- Cost analysis
- Disaster recovery plan

**Publish:** GitHub + LinkedIn case study

---

## Week 4 Checklist

- [ ] Complete 4A: Load Balancing & Auto Scaling
- [ ] Complete 4B: CloudFormation template
- [ ] Complete 4C: Cost analysis
- [ ] Complete 4D: RDS Multi-AZ
- [ ] **CAPSTONE PROJECT:** Week 4 Portfolio Deliverable (MAJOR)
  - [ ] Architecture diagram
  - [ ] CloudFormation template
  - [ ] Deployment guide
  - [ ] Cost analysis
  - [ ] All on GitHub + documented
- [ ] Assessment quiz completed
- [ ] Informational interview #1 completed (document learnings)
- [ ] Started job posting analysis (track required skills)

### Learning Outcome

**By end of Week 4, you should be able to:**
- ✅ Design scalable, highly available architectures
- ✅ Write CloudFormation templates (Infrastructure as Code)
- ✅ Understand cost optimization strategies
- ✅ Explain disaster recovery planning
- ✅ Discuss load balancing and auto-scaling
- ✅ Answer architecture design interview questions

---

---

# WEEKS 5-6: CERTIFICATION SPRINT #1 & ADVANCED SECURITY

## Week 5: CompTIA Network+ Exam Preparation & Security Fundamentals

### The "Why"
- Network+ certification: Industry-recognized, no prerequisites
- Prerequisite to other certifications (CompTIA+ requires A+)
- Exam Week 5 Friday: Network+ exam scheduled
- Focus: 2 weeks of intensive prep from weeks 1-5

### Exam Details
- **Exam Name:** CompTIA Network+ (N10-008)
- **Cost:** ~$330
- **Pass Score:** 720/900
- **Duration:** 90 minutes
- **Questions:** 80 questions
- **Format:** Multiple choice + drag-and-drop scenarios

### Study Strategy (Week 5)

**Days 1-3: Review Weak Areas**
- Retake TutorialDojo practice exams from weeks 1-4
- Focus on topics scoring < 80%
- Study: Professor Messer covering weak areas

**Days 4-5: Full Practice Exams**
- CompTIA official practice test (1 hour)
- Target: 75%+ pass rate
- Review any failures

**Days 6-7: Final Review + Exam Day**
- Review flashcards (ports, protocols, OSI layers)
- Get good sleep before exam
- Exam day: Arrive 15 minutes early, bring ID

### Network+ Topics on Exam
- OSI Model & Network Protocols (20%)
- Network Implementation & Security (25%)
- Network Operations & Troubleshooting (30%)
- Network Security (25%)

### Important Exam Tips
- Flag questions you're unsure about, review at end
- Manage time: 1 minute per question average
- Scenario questions: Read carefully, understand what they're asking
- If unsure: Eliminate obviously wrong answers, guess between remaining

---

## Week 6: AWS Solutions Architect Associate Preparation

### The "Why"
- Most sought-after AWS certification
- High salary correlation: +$25K/year premium
- Required for Cloud Infrastructure Engineer roles
- Your capstone project aligns with exam content

### Exam Details
- **Exam Name:** AWS Certified Solutions Architect - Associate
- **Cost:** ~$150
- **Pass Score:** 720/1000
- **Duration:** 130 minutes
- **Questions:** 65 questions
- **Format:** Multiple choice + scenario-based

### Key Exam Topics
- EC2 & Auto Scaling (20%)
- VPC & Networking (15%)
- RDS & Databases (15%)
- S3 & Storage (15%)
- IAM & Security (15%)
- Advanced Architecture (20%)

### Study Strategy (Weeks 4-6)

**Week 4:** Build hands-on foundation (capstone project)
**Week 5:** Strengthen weak areas with focused study
**Week 6:** Intensive exam preparation, practice tests

### Practice Exam Strategy
- Complete: AWS official practice exam (130 min)
- Target: 70%+ pass rate before actual exam
- Review each failed question: Understand why you got it wrong

### Important Exam Tips
- Many trick questions about "cost optimization" or "high availability"
- Read entire question and all answers before deciding
- Multi-select questions clearly marked (usually 2-3 correct answers)
- Scenario questions: Focus on what's being asked, not just what's mentioned

---

## Weeks 5-6 Labs & Activities

### Lab 5A: Network+ Exam Practice (8 hours)
- Complete: 200+ practice questions
- Tools: ExamTopics, TutorialDojo, Professor Messer quizzes
- Pass rate tracker: Aim for 80%+ consistently

### Lab 6A: AWS Solutions Architect Practice Exams (8 hours)
- Complete: Official AWS practice exam (2x)
- Review: Every question you get wrong
- Use: A Cloud Guru practice exams (additional 4-5 practice sets)

### Lab 6B: Architecture Design Scenarios (5 hours)
- Scenario-based labs matching exam content
- Example: "Design multi-region architecture for disaster recovery"
- Practice: Answering within exam time limits

---

## Portfolio Update: Weeks 5-6

### Certifications Earned
- [ ] CompTIA Network+ (Week 5)
- [ ] AWS Solutions Architect Associate (Week 7-8, scheduled)

### LinkedIn Profile Update
- Add Network+ certification badge
- Add "Network+ Certified" to headline
- Update skills: "CompTIA Network+ Certified"

### Networking Progress
- [ ] Informational interviews completed: 2+
- [ ] LinkedIn connections: 100+
- [ ] Job posting analysis: Track 50+ postings for required skills
- [ ] Blog posts published: 2 (tech content)

---

## Week 5 Checklist

- [ ] CompTIA Network+ practice exam: 80%+ pass rate
- [ ] Complete Network+ exam (scheduled Friday Week 5)
- [ ] Professor Messer weak topic review (10 hours)
- [ ] TutorialDojo exam questions: 80+ completed
- [ ] Add Network+ to LinkedIn profile
- [ ] Continue informational interviews

---

## Week 6 Checklist

- [ ] AWS Solutions Architect practice exam #1: 70%+ pass rate
- [ ] AWS Solutions Architect practice exam #2: 75%+ pass rate
- [ ] Complete Lab 6A & 6B (architecture practice)
- [ ] Review capstone project and CloudFormation (applies to exam)
- [ ] Schedule AWS Solutions Architect exam (Week 7-8)
- [ ] Job application preparation: Start tracking target companies

---

---

# SUMMARY: WEEKS 1-6 PROGRESS TRACKING

## Certifications Status
- ✅ Week 5: CompTIA Network+ Certified
- 🔄 Week 7-8: AWS Solutions Architect Associate (in progress)
- 🔄 Week 9: ISC2 Certified Cloud Security Professional (upcoming)

## Portfolio Status
- ✅ Week 1-3: Weekly lab artifacts (9+ documented labs)
- ✅ Week 4: First capstone project (3-tier architecture, CloudFormation)
- 🔄 Week 8: Second capstone project (upcoming)
- 🔄 Week 12: Third capstone project (upcoming)

## Networking Status
- ✅ LinkedIn: 100+ connections
- ✅ Blog posts: 3-4 technical posts published
- ✅ Informational interviews: 2-3 completed
- 🔄 Job applications: Preparing to start (Week 9-10)

## Skills Development
- ✅ AWS fundamentals (Weeks 1-4)
- ✅ Network fundamentals (Weeks 2-3)
- ✅ Linux administration (Week 3)
- ✅ Advanced AWS architecture (Week 4)
- ✅ Certification preparation (Weeks 5-6)
- 🔄 Security deep-dive (Week 7-9 upcoming)

## Key Metrics
- **Labs Completed:** 12+
- **GitHub Portfolio:** Fully documented with 50+ commits
- **LinkedIn Engagement:** 200+ profile views, 50+ connection requests
- **Study Hours:** 180+ hours completed
- **Certifications:** 1 earned, 2 in progress

---

*End of Part 2 - Weeks 1-6 Complete*
*Next: Part 3 - Weeks 7-12 (Security Deep-Dive, Final Certifications, Job Search Sprint)*
